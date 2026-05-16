---
title: "DFingerNet: Noise-Adaptive Speech Enhancement for Hearing Aids"
type: academic-paper
venue: arXiv (preprint)
arxiv_id: 2501.10525
date_published: 2025-01
date_ingested: 2026-05-13
url: https://arxiv.org/abs/2501.10525
tags: [speech-enhancement, hearing-aids, noise-adaptive, on-device, dnn-in-hearing-aids, deep-filter-network, fingerprinting, conditional-inference, edge-ai, low-latency]
---

# DFingerNet: Noise-Adaptive Speech Enhancement for Hearing Aids

## Summary

DFingerNet (DFiN) extends the Deep Filter Network (DFN) architecture for hearing-aid speech enhancement by adding a **noise-fingerprint** adaptation module. The fingerprint conditions the SE network on the current acoustic environment, enabling the same model to specialize across noise classes without retraining or model-switching at inference.

## Approach (Compressed)

- **Backbone:** Deep Filter Network (DFN) — a complex-spectral filtering SE architecture proven competitive in DNS / hearing-aid challenges.
- **Adaptation module:** A noise-fingerprint extractor produces a compact embedding of the current noise environment. The embedding is injected into the SE network as a conditioning signal.
- **Effect:** The network's mask/filter behavior adapts per-frame to the noise class without explicit scene classification or model swapping.
- **Target deployment:** On-device, low-latency hearing-aid inference (DFN was designed with this in mind).

## Why It Matters for Hearing AI

1. **Single-model multi-environment generalization.** Hearing-aid programs traditionally use scene-classification → preset-switching. DFiN replaces the discrete switch with a continuous embedding-driven adaptation — closer to what large speech models do internally.
2. **Conditional inference fits HA constraints.** Adding a fingerprint embedding is cheap relative to running multiple SE networks. The compute budget stays within HA on-device ranges (microwatts to low milliwatts).
3. **Bridge to foundation-model thinking.** Noise fingerprinting is a step toward HA SE that conditions on richer acoustic-scene representations — potentially WavLM/Whisper-style embeddings, which are now competitive perceptual-loss proxies (see [[gap-urgenet-urgent-challenge-icassp-2026]]).
4. **Complement to custom-silicon plays.** Fortell's Spatial AI (see [[fortell-spatial-ai-ija-may-2026]]) bets on custom chips for raw compute. DFiN is the alternative path: keep commodity silicon, get specialization gains from clever conditioning.

## Limitations / Open Questions

- Generalization to unseen noise classes depends on fingerprint coverage during training.
- Fingerprint module power cost not detailed for the actual HA on-chip deployment.
- Subjective HASPI/HASQI evaluation not headline — most results are on objective SE metrics.

## Related Wiki Pages

- [[../concepts/dnn-in-hearing-aids]] — Conditional SE as next-step DNN architecture
- [[../concepts/on-device-ml-hearing-aids]] — Power/latency budget DFiN must respect
- [[../concepts/speech-enhancement-neural-networks]] — Direct lineage from DFN family
- [[../sources/gap-urgenet-urgent-challenge-icassp-2026]] — Sibling speech-enhancement work using foundation-model features
- [[../sources/fortell-spatial-ai-ija-may-2026]] — Custom-silicon alternative path
