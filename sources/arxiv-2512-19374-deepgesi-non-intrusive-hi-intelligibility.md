---
title: "DeepGESI: A Non-Intrusive Objective Evaluation Model for Predicting Speech Intelligibility in Hearing-Impaired Listeners"
type: source
source_type: arxiv-preprint
date_published: 2025-12
date_ingested: 2026-06-13
authors: [unspecified]
identifier: arXiv:2512.19374
url: https://arxiv.org/abs/2512.19374
venue: arXiv (eess.AS)
tags: [speech-intelligibility, non-intrusive-metric, hearing-impaired, evaluation, hearing-aid-dsp, training-objective]
---

# DeepGESI: Non-Intrusive Objective Evaluation Model for Predicting Speech Intelligibility in Hearing-Impaired Listeners

## Bibliographic
- **Identifier:** arXiv:2512.19374
- **Venue:** arXiv (eess.AS)
- **URL:** https://arxiv.org/abs/2512.19374

## Problem
Conventional speech intelligibility metrics (STOI, ESTOI, HASPI, classical GESI) require a clean reference signal. Hearing-aid pipelines that operate continuously in real environments have no clean reference, so these metrics cannot be used as a training objective or as a runtime QA proxy. Existing non-intrusive predictors are mostly tuned for normal-hearing listeners and degrade for hearing-impaired (HI) ones.

## Contribution
DeepGESI is a non-intrusive (reference-free) speech-intelligibility prediction model targeted at HI listeners. It builds on prior non-intrusive speech-quality predictors and extends them with HI-specific training signal.

## Why It Matters
- Removes the clean-reference bottleneck from hearing-aid SE training pipelines — DNNs can be optimized directly against an HI-relevant intelligibility proxy.
- Useful as a runtime QA signal for production hearing-aid firmware where ground-truth clean speech is unavailable.
- Complements ongoing Clarity Prediction Challenge work on HI-tuned objective metrics.

## Open Questions / Limitations
- Bias toward the HI listener distribution used at training time.
- Validation against subjective intelligibility ratings (e.g., real HASPI/HASPI v2 listener panels) needs scrutiny before adoption as a training loss.

## Used In
- [[wiki/concepts/speech-intelligibility-metrics.md]]
- [[wiki/concepts/non-intrusive-quality-prediction.md]]
- [[wiki/concepts/speech-enhancement-neural-networks.md]]
