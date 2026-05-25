---
title: "Multi-Speaker DOA Estimation in Binaural Hearing Aids using Deep Learning and Speaker Count Fusion"
source_type: research-paper
publisher: arXiv (eess.AS) — ICASSP 2026 submission
date: 2025-09
url: https://arxiv.org/list/eess.AS/recent
authors: [Authors per arXiv listing]
type: research-paper
tags: [binaural-hearing-aid, doa-estimation, beamforming, speaker-counting, deep-learning, multi-talker, icassp-2026, directional-microphones]
ingested: 2026-05-22
---

# Multi-Speaker DOA Estimation in Binaural HAs (ICASSP 2026 submission)

## Summary
A binaural-hearing-aid pipeline that combines a **deep direction-of-arrival (DOA) estimator** with a **speaker-count fusion head** so the device can estimate where multiple talkers are when the number of active sources is unknown a priori. Targets the practical limitation that classical beamformers assume a known small number of sources, while real listening scenes have an unknown and time-varying number of talkers.

## Headline Facts
- **Setup:** Binaural hearing aid configuration (two HAs cooperating across head, exploiting interaural cues).
- **Architectural contribution:** Joint DOA estimation + **speaker count fusion** head — the count estimate gates and resolves DOA outputs rather than assuming a fixed source count.
- **Venue:** Submitted to IEEE ICASSP 2026.

## Why It Matters
- **Beamforming is the largest single power expenditure in a modern HA's directional pipeline.** Making it correctly conditional on the number of talkers improves SNR in cocktail-party scenes without paying a constant cost.
- **Binaural cooperation** has been the major architectural upgrade across the top-five OEMs over the last 5 years (Phonak Sphere, Oticon Intent, ReSound Vivia, Starkey Edge AI/Omega, WSA). Better DOA + count estimation directly improves the upstream signal that all the downstream AI (speech enhancement, scene classification, attention decoding) operates on.

## Strategic / Data-Science Significance
- Pairs well with the **Brain-Informed CI Speech Separation** paper ingested today: that work assumes a separator-side fix; this work strengthens the **scene-analysis front-end** that any separator (audio-only or AAD-conditioned) feeds from.
- Speaker counting as a first-class output is a **labeled telemetry stream** that hearing-aid OEMs can in principle log and use to validate scene-classifier and beamformer behavior in the field.

## Limits / Open Questions
- Computational cost vs. classical MUSIC / SRP-PHAT baselines on the actual HA SoC — not yet evaluated on-device.
- Generalization across head sizes / HRTFs / receiver placements is a known open problem for any deep DOA model trained on a limited HRTF set.

## Related Wiki Pages
- [Beamforming in Hearing Aids](../wiki/concepts/beamforming-hearing-aids.md) (candidate)
- [Binaural Hearing Aid Cooperation](../wiki/concepts/binaural-cooperation.md) (candidate)
- [Brain-Informed CI Speech Separation (arXiv 2601.22260)](../wiki/sources/brain-informed-ci-speech-separation-arxiv-2601-22260.md)
- [Closed-Loop Data Flywheel](../wiki/concepts/closed-loop-data-flywheel.md)

## Sources
- [arXiv eess.AS recent listings](https://arxiv.org/list/eess.AS/recent)
