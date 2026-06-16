---
title: "Confidence Score Guided Incremental and Speaker Adaptive Pseudo-Labeling for Semi-Supervised Elderly Speech Recognition"
type: source
source_type: arxiv-paper
arxiv_id: 2606.16546
authors: [Chengxi Deng, Xurong Xie, Shujie Hu, Jiajun Deng, Mengzhe Geng, Youjun Chen, Huimeng Wang, Haoning Xu, Guinan Li, Xunying Liu]
affiliations: [The Chinese University of Hong Kong (CUHK), Xunying Liu group]
date_published: 2026-06-15
ingested: 2026-06-16
url: https://arxiv.org/abs/2606.16546
venue: arXiv (eess.AS), accepted INTERSPEECH 2026
tags: [elderly-asr, dysarthric-speech, semi-supervised-learning, pseudo-labeling, confidence-estimation, curriculum-learning, speaker-adaptive-training, learnable-prompts, dementiabank-pitt, jccocc-moca, cantonese, english, cross-lifespan, cuhk]
---

# Confidence-Score-Guided Incremental Speaker-Adaptive Pseudo-Labeling for Elderly ASR (Deng et al., June 15 2026)

## Bibliographic
- **Authors:** Chengxi Deng, Xurong Xie, Shujie Hu, Jiajun Deng, Mengzhe Geng, Youjun Chen, Huimeng Wang, Haoning Xu, Guinan Li, Xunying Liu
- **Affiliation:** The Chinese University of Hong Kong — Xunying Liu speech group
- **Posted:** 15 June 2026 (arXiv:2606.16546)
- **Venue:** Accepted INTERSPEECH 2026
- **URL:** https://arxiv.org/abs/2606.16546

## Problem
Labeled elderly speech is scarce, slow to collect, and ethics-encumbered (IRB, consent, cognitive-impairment-related capacity questions). Semi-supervised pseudo-labeling is the obvious lever — train on a small labeled set, generate pseudo-labels for a much larger unlabeled set, re-train. But naive pseudo-labeling on elderly speech amplifies its own errors: the same dysarthric patterns that hurt the ASR baseline cause low-confidence pseudo-labels to be added as noisy supervision, and per-speaker variance is enormous, so a single-speaker bad batch can dominate the gradient.

## Contribution
Two coupled mechanisms:

1. **Confidence-score-ranked curriculum.** Unlabeled utterances are scored by a confidence estimator; the system trains on high-confidence pseudo-labels first, then lower-confidence ones — a **high-to-low confidence curriculum** that prevents the early gradient from being dominated by noisy supervision. This is the "incremental" half of the title.
2. **Speaker-adaptive training with learnable prompts.** Per-speaker (or per-cohort) prompts are learned as part of the model, so the noisy supervision is decomposed into speaker-specific vs general components. This is the "speaker adaptive" half. Learnable prompts replace the static speaker-embedding approach (i-vector / x-vector / ECAPA-TDNN) that prior semi-supervised elderly ASR pipelines used.

The two mechanisms are designed to work jointly — confidence curriculum protects the early training, learnable prompts absorb the speaker-specific noise that remains.

## Headline Numbers
On the same DementiaBank Pitt + JCCOCC MoCA evaluation as the companion online-adaptation paper:

- **−1.45% absolute WER (English, DementiaBank Pitt)** vs the baseline semi-supervised method — **6.21% relative reduction**.
- **−2.27% absolute CER (Cantonese, JCCOCC MoCA)** vs the baseline semi-supervised method — **6.98% relative reduction**.

## Why It Matters for Hearing AI

### 1. Data-side counterpart to the online-adaptation paper
This paper and arXiv:2606.16539 (Deng et al., same group, same day) form a deliberate **inference-time × training-time pair** on the elderly-ASR problem:
- **2606.16539** ("Decoding while Adapting") tackles the **inference-time** speaker-adaptation problem with audio-textual prompts.
- **2606.16546** (this paper) tackles the **training-time** data-scarcity problem with confidence-ranked pseudo-labeling and learnable speaker prompts.

Together they give the field a recipe for both halves of the elderly-ASR pipeline.

### 2. The "learnable prompt" is the same primitive as the age-aware adapter
Both this paper (learnable per-speaker prompts) and **Jialu Li's age-aware adapter** for children's ASR (arXiv:2606.05440) use a **small learnable conditioning block over a frozen / mostly-frozen foundation backbone**, routed by a clinical / demographic variable. The two papers, bracketing the lifespan, converge on the same architectural primitive — a low-parameter conditioning hook layered on top of a shared FM substrate.

This is now a clear pattern across at least four June-2026 papers (the others being Gumbel-BEARD's layer router and Khanagha-Gerkmann's RIR-conditioned diffusion SE): **the next round of gains comes from learnable routers / conditioning hooks over frozen foundation-model substrate**, not from training new foundation models.

### 3. Curriculum-by-confidence is the right shape for hearing-aid telemetry
Hearing-aid telemetry will collect orders of magnitude more pseudo-labelable audio than the OEMs can ever transcribe. A confidence-ranked curriculum is the natural ingestion policy. The paper's specific contribution — that the curriculum needs to be paired with speaker-adaptive conditioning to avoid speaker collapse — transfers directly to any OEM closed-loop data flywheel ([[closed-loop-data-flywheel]]).

### 4. The 6–7% relative gain comes from cheap mechanisms
Neither component requires a new foundation model, a new architecture, or new labeled data. Both are training-policy changes layered on existing pipelines. This is the kind of "low-CapEx, real-gain" lever that hearing-care OEMs — who are not LLM-foundation-model builders — should be looking for.

## Datasets
Same as the companion paper:
- **DementiaBank Pitt** (English clinical interviews; first wiki appearance).
- **JCCOCC MoCA** (Cantonese MoCA recordings, CUHK-built; first wiki appearance).

## Open Questions
- How is the confidence estimator trained? The summary does not specify whether it is the ASR model's own posterior, a separate confidence head, or an external scorer. Each choice has different deployment implications.
- Confidence scores on dysarthric speech are themselves under-calibrated — does the paper measure calibration of the scores it uses to rank?
- How well does the curriculum policy generalize to non-medical elderly speech (general-population telemetry) where the linguistic content is open-vocabulary rather than picture-description / MoCA?
- The "speaker-adaptive learnable prompts" assume a speaker-identity signal at training time. In OEM telemetry the speaker-identity may need to be inferred from the same speech the model is being adapted on — circular.

## Related Wiki Pages
- [[../wiki/concepts/cross-lifespan-speech-models.md]] — primary concept; second June-2026 elderly-ASR ingest after the companion paper
- [[../wiki/concepts/elderly-speech-recognition.md]] — dedicated concept page (new)
- [[../wiki/entities/dementiabank-pitt-dataset.md]] — dataset entity (new)
- [[../wiki/entities/jccocc-moca-dataset.md]] — dataset entity (new)
- [[../wiki/entities/xunying-liu-cuhk-speech-group.md]] — author group (new)
- [[../wiki/concepts/closed-loop-data-flywheel.md]] — pseudo-labeling is the OEM-telemetry data lever
- [[../wiki/concepts/continual-learning-hearing-ai.md]] — learnable-prompt conditioning as a continual-learning surface
- [[../wiki/concepts/synthetic-data-for-hearing-ai.md]] — pseudo-labeled data as a synthetic-supervision channel

## Related Sources
- [arxiv-2606-16539-elderly-asr-online-adaptation.md](arxiv-2606-16539-elderly-asr-online-adaptation.md) — Inference-time twin from the same group, same day.
- [arxiv-2606-05440-age-aware-adapter-children-asr-jun-2026.md](arxiv-2606-05440-age-aware-adapter-children-asr-jun-2026.md) — Pediatric-edge learnable-prompt / adapter pattern.
- [arxiv-2606-11429-gumbel-beard-layer-selection-jun-2026.md](arxiv-2606-11429-gumbel-beard-layer-selection-jun-2026.md) — Same "learnable router over frozen FM" pattern, layer axis.
- [cross-lifespan-diarization-usc-may-2026.md](cross-lifespan-diarization-usc-may-2026.md) — USC seed paper for the cross-lifespan failure mode.
