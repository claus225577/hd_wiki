---
title: Elderly Speech Recognition
type: concept
created: 2026-06-16
updated: 2026-06-17
sources: [arxiv-2606-16539-elderly-asr-online-adaptation.md, arxiv-2606-16546-elderly-asr-pseudo-labeling.md, cross-lifespan-diarization-usc-may-2026.md, arxiv-2606-18054-cognitive-linguistic-features-dementia-jun-2026.md, arxiv-2606-18019-llm-dementia-depression-clinical-interviews-jun-2026.md, arxiv-2606-17254-cross-lingual-alzheimer-detection-jun-2026.md]
related: [cross-lifespan-speech-models.md, companion-phone-speech-pipeline.md, digital-phenotyping-cognitive-decline.md, hearing-loss-dementia-link.md, closed-loop-data-flywheel.md, continual-learning-hearing-ai.md, ../entities/dementiabank-pitt-dataset.md, ../entities/jccocc-moca-dataset.md, ../entities/xunying-liu-cuhk-speech-group.md, ../syntheses/speech-as-passive-cognition-biomarker-pipeline-june-2026.md]
tags: [elderly-asr, dysarthric-speech, speaker-adaptation, pseudo-labeling, audio-textual-prompts, learnable-prompts, dementiabank, jccocc-moca, cantonese, english, cross-lifespan, hearing-aids, dementia-screening]
---

# Elderly Speech Recognition

## Frame
Elderly speech is the **older-edge failure mode** of the cross-lifespan generalization problem ([[cross-lifespan-speech-models]]). Adult-skewed foundation models — Whisper, Voxtral, Qwen3-ASR — degrade systematically on speakers over ~65, and degrade further on speakers with dementia-associated dysarthria, prosodic flattening, disfluencies, and slowed speaking rate. This is the demographic the hearing-aid industry actually sells to. The substrate that hearing-care companion-phone pipelines ([[companion-phone-speech-pipeline]]) depend on is exactly the substrate the elderly-ASR literature is trying to fix.

## Why This Is a Hearing-AI Problem, Not Just an ASR Problem
- **Customer base.** The hearing-aid wearer base is over-65-weighted by construction. The ASR substrate that companion-phone hearing-care pipelines depend on inherits the failure mode at its largest in exactly the wearer demographic.
- **Dementia overlap.** The hearing-loss × dementia comorbidity ([[hearing-loss-dementia-link]]) means the elderly subset that hearing-aid OEMs see disproportionately includes the cognitive-impairment cohort whose speech is hardest to transcribe.
- **Clinical-screening pipeline.** Speech-based dementia screening ([[digital-phenotyping-cognitive-decline]]) shares the same audio substrate. ASR errors are not just UX failures — they bias downstream linguistic features (lexical-density, semantic-fluency, pause distribution) on which the screening algorithm depends.
- **Telemetry-side data flywheel.** Hearing-aid telemetry will produce orders of magnitude more elderly-speech audio than any clinical corpus. The pseudo-labeling work below ([[#training-time-confidence-curriculum--learnable-prompts]]) is the natural template for ingesting it.

## Two Coupled Mechanisms — June 2026 CUHK Pair

The Xunying Liu group at CUHK posted two papers on the same day, 15 June 2026, that together cover the inference-time and training-time halves of the elderly-ASR pipeline. See [[../entities/xunying-liu-cuhk-speech-group]].

### Inference-time: cross-utterance audio-textual prompts
**Deng et al., arXiv:2606.16539** — "Decoding while Adapting." Zero-shot online speaker adaptation: speech embeddings and text embeddings are extracted from the current utterance plus a few preceding utterances, fused cross-modally into a compact speaker prompt that conditions the decoder. No enrollment data needed.

Headline:
- −0.61% absolute WER on DementiaBank Pitt (English).
- −1.22% absolute CER on JCCOCC MoCA (Cantonese).
- **9.83× RTF speedup** vs offline batch speaker adaptation.

The text channel is the key upgrade over classical i-vector / x-vector / ECAPA-TDNN: text features from prior utterances of the same speaker are linguistically consistent across utterances and act as a robust anchor when speech embeddings on dysarthric audio are noisy.

### Training-time: confidence curriculum + learnable prompts
**Deng et al., arXiv:2606.16546** — "Confidence Score Guided Incremental and Speaker Adaptive Pseudo-Labeling." Two coupled mechanisms:
1. **High-to-low confidence curriculum** on pseudo-labeled unlabeled speech, so the early gradient is not dominated by noisy supervision.
2. **Speaker-adaptive learnable prompts** that absorb speaker-specific noise that survives the curriculum.

Headline:
- −1.45% absolute WER / 6.21% relative on DementiaBank Pitt (English) vs baseline semi-supervised methods.
- −2.27% absolute CER / 6.98% relative on JCCOCC MoCA (Cantonese).

## The Cross-Lifespan Bracket
The CUHK elderly papers are the **older-edge bracket** of the cross-lifespan ASR problem. The pediatric-edge bracket is **Jialu Li, arXiv:2606.05440** (3 June 2026), which uses a near-identical primitive — a learnable per-age-band adapter routed by an age estimator over a frozen backbone. Twelve days apart, the two ends of the lifespan converge on the same architectural pattern:

> **Small learnable conditioning hook (adapter / prompt / router) over a mostly-frozen foundation backbone, conditioned on a demographic / clinical variable.**

This pattern now spans:
- **Age band** (Jialu Li — pediatric adapter routed by age estimator).
- **Speaker identity** (Deng et al. 2606.16539 — audio-textual prompt) and (Deng et al. 2606.16546 — learnable per-speaker prompt).
- **Layer choice** (Gumbel-BEARD, UCLA SPAPL — learnable router over frozen Whisper layers; see [[brain-aligned-speech-foundation-models]]).
- **Room acoustics** (Khanagha-Gerkmann — implicit RIR encoding inside the dereverb U-Net; see [[room-aware-dereverberation]]).

For hearing-AI specifically, the unifying point is that **OEMs do not need to train new foundation models** to capture lifespan-conditioned, speaker-conditioned, or room-conditioned gains. They need to ship a small learnable hook routed by a variable they already have.

## Datasets — First Appearance In This Wiki
- **DementiaBank Pitt** — English clinical interviews including the canonical Cookie Theft picture description. The reference dataset for English elderly + dementia speech. See [[../entities/dementiabank-pitt-dataset]].
- **JCCOCC MoCA** — Cantonese-language MoCA recordings built at CUHK. The Cantonese channel matters because it provides a tonal, non-Indo-European benchmark; almost all elderly-ASR literature is English-only. See [[../entities/jccocc-moca-dataset]].

## Open Questions
- Are DementiaBank Pitt and JCCOCC MoCA representative of **general-population** elderly speech, or are gains here entangled with the **cognitive-impairment cohort** the datasets oversample?
- Hearing-impaired elderly speech (presbyphonia + hearing loss) adds another distribution shift not measured by either dataset. What is the gain on hearing-impaired-elderly speech specifically?
- The learnable-prompt and audio-textual-prompt mechanisms both assume usable speaker-identity signal. In OEM telemetry, speaker identity often needs to be inferred from the same speech being adapted on — a circularity that hasn't been measured.
- Where in the stack should the elderly-conditioning live — at the foundation-model fine-tune, at the adapter, at the scene-classifier, at the companion-app prompt? All four are tractable; latency / update / regulatory profiles differ.

## Related Pages
- [[cross-lifespan-speech-models]] — parent concept; this page covers the older-edge bracket
- [[companion-phone-speech-pipeline]] — deployment substrate
- [[digital-phenotyping-cognitive-decline]] — adjacent clinical-screening pipeline that consumes the same audio
- [[hearing-loss-dementia-link]] — cohort overlap
- [[closed-loop-data-flywheel]] — pseudo-labeling as the OEM-telemetry ingestion policy
- [[continual-learning-hearing-ai]] — learnable-prompt conditioning as a continual-learning surface
- [[brain-aligned-speech-foundation-models]] — adjacent "learnable router over frozen FM" pattern (layer axis)
- [[../entities/xunying-liu-cuhk-speech-group]] — author group
- [[../entities/dementiabank-pitt-dataset]] — English dataset
- [[../entities/jccocc-moca-dataset]] — Cantonese dataset

## Sources
- [Decoding while Adapting (Deng et al., Jun 15 2026)](../../sources/arxiv-2606-16539-elderly-asr-online-adaptation.md) — inference-time zero-shot online speaker adaptation via audio-textual prompts
- [Confidence-Guided Pseudo-Labeling (Deng et al., Jun 15 2026)](../../sources/arxiv-2606-16546-elderly-asr-pseudo-labeling.md) — training-time confidence curriculum + learnable speaker prompts
- [Cross-Lifespan Speaker Diarization (Xu, Feng & Narayanan, May 2026)](../../sources/cross-lifespan-diarization-usc-may-2026.md) — frames the older-edge failure mode
- [Xu et al. — Cognitive-linguistic Construct Rubric for Dementia (Jun 16 2026)](../../sources/arxiv-2606-18054-cognitive-linguistic-features-dementia-jun-2026.md) — downstream LLM scoring layer that consumes the elderly-ASR transcript
- [Braun et al. — German Clinical Interview LLM Scoring (Jun 16 2026)](../../sources/arxiv-2606-18019-llm-dementia-depression-clinical-interviews-jun-2026.md) — downstream open-weights LLM scoring; pause-enriched transcripts close most of the human-transcription gap
- [Girish et al. — Zero-Shot Cross-Lingual Alzheimer Detection (Jun 16 2026)](../../sources/arxiv-2606-17254-cross-lingual-alzheimer-detection-jun-2026.md) — downstream cross-lingual scoring layer
