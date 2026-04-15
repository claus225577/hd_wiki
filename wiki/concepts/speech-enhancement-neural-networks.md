---
title: Speech Enhancement Neural Networks
type: concept
created: 2026-04-15
updated: 2026-04-15
sources: []
related: [on-device-ml-hearing-aids.md, small-language-models-edge-ai.md]
tags: [deep-learning, speech, noise-reduction, dnn, hearing-aids]
---

# Speech Enhancement Neural Networks

Neural network architectures designed to improve speech intelligibility by separating speech from noise, enhancing clarity, and adapting to listener preferences. This is the primary ML workload in modern hearing aids.

## Evolution
1. **Classical DSP** — Wiener filters, spectral subtraction (pre-2015)
2. **Simple DNNs** — Feedforward networks for noise estimation (2015-2018)
3. **RNNs/LSTMs** — Temporal modeling for non-stationary noise (2018-2021)
4. **Attention/Transformer variants** — Better long-range dependencies (2021-present)
5. **Emerging: Diffusion-based** — Generative approaches for speech reconstruction (research stage)

## Key Architectures in Hearing Aid Research
- **Conv-TasNet** — Time-domain speech separation, influential but too large for HA chips
- **DCCRN** — Deep Complex Convolution Recurrent Network, good real-time performance
- **FullSubNet** — Full-band and sub-band fusion, strong on DNS Challenge benchmarks
- **TinyRecurrentUNet** — Designed for low-resource devices, closer to hearing aid constraints

## Challenges Specific to Hearing Aids
- Model must run in < 10ms (algorithmic latency budget)
- Must handle hearing loss-specific processing (frequency-dependent amplification per audiogram)
- Training data rarely matches real-world hearing aid microphone characteristics
- Need to preserve spatial cues for localization (binaural processing)
- Must work across all environments without user intervention

## Evaluation Metrics
- **PESQ** — Perceptual Evaluation of Speech Quality
- **STOI** — Short-Time Objective Intelligibility
- **SI-SNR** — Scale-Invariant Signal-to-Noise Ratio
- **Subjective listening tests** — Still gold standard, ML metrics don't fully capture perceived quality

## Related Pages
- [[on-device-ml-hearing-aids]] — Deployment target for these networks
- [[small-language-models-edge-ai]] — Compression techniques applicable to speech models
