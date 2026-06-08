---
title: "Age-Aware Adapter Tuning for Children's Speech Recognition"
type: source
source_type: arxiv-preprint
date_published: 2026-06-03
date_ingested: 2026-06-08
authors: [Jialu Li]
identifier: arXiv:2606.05440
url: https://arxiv.org/abs/2606.05440
venue: arXiv (eess.AS)
tags: [children-speech, asr, adapter-tuning, parameter-efficient-fine-tuning, age-conditioned, film-conditioning, cross-lifespan, pediatric]
---

# Age-Aware Adapter Tuning for Children's Speech Recognition

## Bibliographic
- **Author:** Jialu Li
- **Posted:** 3 June 2026
- **arXiv:** 2606.05440 (eess.AS)
- **URL:** https://arxiv.org/abs/2606.05440

## Problem
Children's speech recognition is a long-standing pain point for ASR: the acoustic and linguistic distribution drifts rapidly across the 3–12+ age band (F0, formants, phonological inventory, vocabulary, prosody). A single adult-pre-trained ASR model handles the population poorly, but training a dedicated model per child age is wasteful and won't fit downstream on-device budgets.

## Contribution
**Age-aware adapter modules.** Narrow, parameter-efficient adapter layers are trained per child age group on top of a shared backbone. At inference time a router (ground-truth age or predicted age) selects the appropriate adapter. A FiLM (feature-wise linear modulation) variant conditions a single backbone on continuous age instead of hard routing.

## Key Results
- **Ground-truth age routing:** overall WER 12.6% → 12.3%; macro WER 18.4% → 17.6%.
- **Predicted age routing:** tracks ground-truth routing closely — practical even without exact age metadata at inference.
- **Hard routing > FiLM:** uniform FiLM conditioning produces smaller gains than discrete age-specialized adapters; the discrete age-band structure encodes more signal than a continuous scalar.
- Age groups: 3 to 12+, evaluated across child speech datasets (not specified in abstract).

## Why It Matters for Hearing AI
- **Cross-lifespan generalization gap.** Reinforces the May 2026 USC cross-lifespan diarization result (Xu, Feng & Narayanan, arXiv:2604.05201): foundation-model speech representations fail at the lifespan edges. Age-aware adapters are the parameter-efficient hook the field has been missing for closing that gap.
- **Pediatric hearing aids.** Oticon Play SI (April 2026) and the broader pediatric platform refresh sit on top of adult-trained acoustic front-ends. An age-aware adapter sitting in the companion-phone or HA-local DNN stack is a tractable retrofit.
- **Embedded budget.** Hearing aids ship with on-chip weights budgeted in MB. Per-age full retraining is impossible; per-age adapter swap-in is feasible.
- **Lifespan-stratified data moat.** OEMs whose customer acquisition includes both pediatric (Phonak Sky, Oticon Play SI) and adult lines can assemble lifespan-stratified training corpora that consumer-audio companies cannot.

## Open Questions / Limitations
- Affiliations and backbone model not provided in abstract.
- Children's speech datasets used are not specified; generalization to hearing-impaired pediatric corpora is unknown.
- The downstream HA tasks (SE, scene classification, target-speaker extraction) are not evaluated — only ASR.
- "Age" is an ordinal proxy; the real conditioning variable (developmental stage, language exposure) is unknown.

## Used In
- [[wiki/concepts/cross-lifespan-speech-models.md]] — new source; age-aware adapter is the parameter-efficient hook the prior framing pointed at
- [[wiki/concepts/continual-learning-hearing-ai.md]] — adapter-tuning is a representation-efficient continual-learning surface
- [[wiki/concepts/on-device-ml-hearing-aids.md]] — embedded-weight budget for swap-in adapters
