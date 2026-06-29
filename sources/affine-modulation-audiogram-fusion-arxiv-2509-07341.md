---
title: "Affine Modulation-based Audiogram Fusion Network for Joint Noise Reduction and Hearing Loss Compensation"
type: source
source_type: arxiv-preprint
date_published: 2025-09-09
date_ingested: 2026-06-29
authors: [unknown-resurfaced-in-2026-coverage]
identifier: arXiv:2509.07341
url: https://arxiv.org/abs/2509.07341
venue: arXiv eess.AS
tags: [audiogram-conditioning, affine-modulation, joint-noise-reduction, hearing-loss-compensation, single-stage-pipeline, dnn-hearing-aids, mamba, fusion]
---

# Affine Modulation-based Audiogram Fusion Network for Joint Noise Reduction and Hearing Loss Compensation

## Bibliographic
- **arXiv ID:** 2509.07341 (eess.AS, Sep 2025)
- **Resurfaced via:** Jun 2026 hearing-aid arXiv aggregation; included in the 29 Jun 2026 daily digest as a representative of the audiogram-conditioned single-stage architecture trend.
- **URL:** https://arxiv.org/abs/2509.07341

## Headline Claim
A single deep network performs both noise reduction and prescriptive hearing-loss compensation in one pass, conditioned on the user's audiogram via feature-wise affine modulation (FiLM-style) layers. Collapses what has traditionally been a two-stage cascade (SE front-end → prescriptive amplification back-end) into one model.

## Why This Matters
1. **Two stages → one stage.** Classical pipeline: (a) noise reduction with a generic SE model that has no audiogram awareness, then (b) prescriptive amplification via NAL-NL2 / DSL targets. Errors compound across the cascade. Joint modelling lets gradient information from the audiogram-aware compensation step flow back into the SE step.
2. **Audiogram as conditioning signal.** Affine modulation lets the same backbone produce different outputs per audiogram without per-user retraining — useful for fitting and for cloud-trained-once / personalised-at-fit deployment models.
3. **Architecture trend.** Sits alongside CleanUMamba (arXiv:2410.11062) in the broader Mamba/SSM-based low-latency speech-enhancement push that is replacing transformers in hearables, where every mW and ms counts.

## Cross-References Inside This Wiki
- `wiki/concepts/dnn-in-hearing-aids.md` — single-stage audiogram-conditioned pipelines are the architectural counterpoint to cascade pipelines.
- `wiki/concepts/dnn-architectures-hearing-aids.md` — Mamba/SSM-style backbones and audiogram-conditioned heads are joint architectural trends.
- `wiki/concepts/hearing-aid-prescription-formulas.md` — joint models learn an implicit prescription target end-to-end; this challenges the role of explicit NAL-NL2 / DSL targets as fixed teachers.
- `wiki/concepts/foundation-model-fusion-speech.md` — same fusion-of-modalities pattern (signal + audiogram).
