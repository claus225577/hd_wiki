---
title: "Decoding while Adapting: Zero-Shot Online Speaker Adaptation via Audio-Textual Prompts for Elderly Speech Recognition"
type: source
source_type: arxiv-paper
arxiv_id: 2606.16539
authors: [Chengxi Deng, Xurong Xie, Shujie Hu, Mengzhe Geng, Tianzi Wang, Youjun Chen, Huimeng Wang, Haoning Xu, Jiajun Deng, Xunying Liu]
affiliations: [The Chinese University of Hong Kong (CUHK), Xunying Liu group]
date_published: 2026-06-15
ingested: 2026-06-16
url: https://arxiv.org/abs/2606.16539
venue: arXiv (eess.AS), accepted INTERSPEECH 2026
tags: [elderly-asr, dysarthric-speech, speaker-adaptation, zero-shot, audio-textual-prompts, cross-modal-fusion, online-adaptation, dementiabank-pitt, jccocc-moca, cantonese, english, real-time-asr, cross-lifespan, cuhk]
---

# Decoding while Adapting — Zero-Shot Online Speaker Adaptation for Elderly ASR (Deng et al., June 15 2026)

## Bibliographic
- **Authors:** Chengxi Deng, Xurong Xie, Shujie Hu, Mengzhe Geng, Tianzi Wang, Youjun Chen, Huimeng Wang, Haoning Xu, Jiajun Deng, Xunying Liu
- **Affiliation:** The Chinese University of Hong Kong — Xunying Liu speech group (long-running CUHK speech-and-language research line)
- **Posted:** 15 June 2026 (arXiv:2606.16539)
- **Venue:** Accepted INTERSPEECH 2026
- **URL:** https://arxiv.org/abs/2606.16539

## Problem
Elderly speech is a worst-case domain for ASR: dysarthric articulation, slower speaking rate, prosodic flattening, and frequent cognitive-impairment-associated disfluencies systematically violate the assumptions of adult-skewed foundation-model pre-training. Classical speaker-adaptive training requires per-speaker enrollment audio, which is unavailable in real elderly-care deployment, and offline batch adaptation has too much latency to run inside an interactive hearing-care or clinical-screening pipeline.

The paper targets the gap directly: **zero-shot, online (streaming) speaker adaptation**, with no enrollment data and no offline batch.

## Contribution
**Cross-utterance audio-textual prompts.** The method extracts speech embeddings and text embeddings from the current utterance plus a few preceding utterances of the same speaker, then **fuses them cross-modally** into a compact speaker prompt that conditions the ASR decoder. Because the prompt is built from utterances already in the rolling decoding buffer, no enrollment phase is required.

The cross-modal fusion is the explicit upgrade over classical speaker-embedding pipelines:

| Speaker-conditioning approach | Modality | Online-friendly | Reported in this paper |
|---|---|---|---|
| i-vector | audio only | yes | weaker than audio-textual prompts |
| x-vector | audio only | yes | weaker than audio-textual prompts |
| ECAPA-TDNN | audio only | yes | weaker than audio-textual prompts |
| Audio-textual prompts (this work) | audio + text | yes | strongest reported |

The paper argues that the **text channel stabilizes** the speaker representation: speech embeddings on dysarthric audio are noisy, but text features from prior utterances of the same speaker are linguistically consistent across utterances and act as a robust anchor.

## Headline Numbers
- **DementiaBank Pitt (English):** **−0.61% absolute WER** vs the speaker-independent (SI) baseline.
- **JCCOCC MoCA (Cantonese):** **−1.22% absolute CER** vs the SI baseline.
- **9.83× real-time-factor (RTF) speedup** vs offline batch speaker adaptation — the headline systems-side claim.
- Gains are reported as **statistically significant**.

## Why It Matters for Hearing AI

### 1. Hearing-aid wearer demographics are exactly the failure mode
The customer base for hearing aids is over-65-weighted; the customer base for cochlear-implant programs in elderly cohorts and for dementia-screening pipelines (see [[hearing-loss-dementia-link]]) is older still. The ASR substrate that hearing-care companion-phone pipelines depend on ([[companion-phone-speech-pipeline]]) is exactly the substrate the elderly-ASR literature is trying to fix.

### 2. Brackets the lifespan with pediatric work on the other end
Reads naturally against **Jialu Li's age-aware adapter for children's ASR** (arXiv:2606.05440, 3 Jun 2026). Pediatric and elderly are the two failure modes of adult-skewed foundation models. The two papers, posted twelve days apart, frame the lifespan generalization problem as a **two-sided closure** rather than a single-side adaptation question.

### 3. Online cross-modal fusion is a transferable primitive
The "audio + text from prior utterances in the buffer" prompt is not specific to elderly ASR. It is a general primitive for real-time speaker conditioning on streaming audio — applicable to dyad-aware hearing-aid pipelines ([[care-partner-dyad-models]]) and to multi-speaker UX where the companion phone is doing target-speaker extraction.

### 4. RTF win matters for hearing care
A 9.83× RTF speedup vs offline adaptation is the difference between "run on the phone alongside live ASR" and "run as an overnight batch job." For interactive clinical use — hearing-aid fitting interview, dementia screening, teleaudiology session — the online regime is the deployable one.

## Datasets
- **DementiaBank Pitt corpus** — English-language clinical interviews including the canonical "Cookie Theft" picture description task; widely used reference set for elderly / dementia speech, first time appearing in this wiki.
- **JCCOCC MoCA** — Cantonese-language corpus of Montreal Cognitive Assessment recordings (CUHK-built). First time appearing in this wiki. The Cantonese channel is significant because it provides a tonal-language, non-Indo-European elderly-speech benchmark — most elderly-ASR literature is English-only.

## Open Questions
- Does the audio-textual prompt design retain its advantage when prior utterances are very short or only contain interjections? The paper does not report length-stratified results.
- Generalization to elderly speakers without a measurable dementia diagnosis — DementiaBank Pitt and JCCOCC MoCA are clinical / cognitive-screening corpora, not general-population elderly speech. The "elderly" label here is entangled with cognitive impairment.
- Hearing-impaired elderly speech (presbyphonia + hearing loss) adds another distribution shift not measured by either dataset.
- No on-device measurement of the prompt-extraction cost vs the ASR decoder cost — the systems-side claim is RTF only.

## Related Wiki Pages
- [[../wiki/concepts/cross-lifespan-speech-models.md]] — primary concept; this paper is the elderly-edge counterpart to Jialu Li's pediatric-edge adapter
- [[../wiki/concepts/elderly-speech-recognition.md]] — dedicated concept page (new)
- [[../wiki/entities/dementiabank-pitt-dataset.md]] — dataset entity (new)
- [[../wiki/entities/jccocc-moca-dataset.md]] — dataset entity (new)
- [[../wiki/entities/xunying-liu-cuhk-speech-group.md]] — author group (new)
- [[../wiki/concepts/companion-phone-speech-pipeline.md]] — deployment substrate
- [[../wiki/concepts/digital-phenotyping-cognitive-decline.md]] — adjacent clinical-screening pipeline
- [[../wiki/concepts/hearing-loss-dementia-link.md]] — cohort overlap

## Related Sources
- [arxiv-2606-16546-elderly-asr-pseudo-labeling.md](arxiv-2606-16546-elderly-asr-pseudo-labeling.md) — Companion paper from the same group, posted the same day, on the semi-supervised-data side of the same problem.
- [arxiv-2606-05440-age-aware-adapter-children-asr-jun-2026.md](arxiv-2606-05440-age-aware-adapter-children-asr-jun-2026.md) — Pediatric-edge counterpart, Jialu Li.
- [cross-lifespan-diarization-usc-may-2026.md](cross-lifespan-diarization-usc-may-2026.md) — USC framing of the cross-lifespan failure mode.
- [arxiv-2606-11429-gumbel-beard-layer-selection-jun-2026.md](arxiv-2606-11429-gumbel-beard-layer-selection-jun-2026.md) — Layer-routing inside a frozen foundation model; same "learnable router over frozen FM" pattern, different routing axis.
