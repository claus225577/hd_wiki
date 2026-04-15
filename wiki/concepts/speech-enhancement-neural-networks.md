---
title: Speech Enhancement Neural Networks
type: concept
created: 2026-04-15
updated: 2026-04-15
sources: []
related: [on-device-ml-hearing-aids.md, small-language-models-edge-ai.md, dnn-architectures-hearing-aids.md, auditory-attention-decoding.md, cochlear-implant-ai.md]
tags: [deep-learning, speech, noise-reduction, dnn, hearing-aids, crn, transformer]
---

# Speech Enhancement Neural Networks

Neural network architectures designed to improve speech intelligibility by separating speech from noise, enhancing clarity, and adapting to listener preferences. This is the primary ML workload in modern hearing aids.

## Evolution
1. **Classical DSP** — Wiener filters, spectral subtraction (pre-2015)
2. **Simple DNNs** — Feedforward networks for noise estimation (2015-2018)
3. **RNNs/LSTMs** — Temporal modeling for non-stationary noise (2018-2021)
4. **CRN (Convolutional Recurrent Networks)** — CNN spatial + RNN temporal, now the dominant production architecture (2020-present)
5. **Attention/Transformer variants** — SepFormer and similar, better long-range dependencies (2021-present)
6. **Emerging: Diffusion-based** — Generative approaches for speech reconstruction (research stage)

## Key Architectures in Hearing Aid Research

### Convolutional Recurrent Networks (CRN) — Current Optimal
CRN is considered the optimal architecture for production hearing aids: CNN layers extract spatial/spectral features while RNN layers model temporal dynamics. This combination handles both stationary and non-stationary noise effectively within tight latency budgets.
- CNN branch: captures spectral patterns and multi-mic spatial information
- RNN branch: models temporal evolution of noise and speech
- Fusion: combines spatial and temporal representations for mask prediction

### SepFormer (Transformer-based)
- Self-attention mechanism captures long-range temporal dependencies
- Competitive on DNS Challenge benchmarks
- Compute cost remains a barrier for direct deployment; used as teacher model for distillation

### Legacy Architectures (Research Baseline)
- **Conv-TasNet** — Time-domain speech separation, influential but too large for HA chips
- **DCCRN** — Deep Complex Convolution Recurrent Network, good real-time performance
- **FullSubNet** — Full-band and sub-band fusion, strong on DNS Challenge benchmarks
- **TinyRecurrentUNet** — Designed for low-resource devices, closer to hearing aid constraints

## Time-Domain vs Frequency-Domain Approaches
| Approach | Pros | Cons | Example Models |
|----------|------|------|----------------|
| Frequency-domain | Interpretable, well-studied, integrates with existing DSP | Phase reconstruction artifacts | DCCRN, FullSubNet |
| Time-domain | No phase problem, end-to-end | Higher compute, harder to control | Conv-TasNet, DEMUCS |
| Hybrid | Best of both | Complex training | CRN variants |

## Ultra-Low Latency Requirements
- Hearing aids require < 10ms algorithmic latency (users perceive delay above this threshold)
- Some implementations target **1ms latency** for DNN noise reduction blocks
- This forces time-domain causal processing and small receptive fields
- Future lookahead is limited to a few milliseconds at most

## Training Data Scales
Leading manufacturers train on massive datasets to cover real-world acoustic diversity:
- **13.5M to 22M synthetic sound scenes** reported in recent manufacturer publications
- Scenes combine speech (various languages, accents, mic distances) with noise (stationary, non-stationary, multi-source)
- Hearing aid microphone simulation is critical — models trained on clean recordings generalize poorly to HA mics

## Challenges Specific to Hearing Aids
- Model must run in < 10ms (algorithmic latency budget); 1ms targets emerging
- Must handle hearing loss-specific processing (frequency-dependent amplification per audiogram)
- Training data rarely matches real-world hearing aid microphone characteristics
- Need to preserve spatial cues for localization (binaural processing)
- Must work across all environments without user intervention
- Cannot degrade music quality while enhancing speech

## Evaluation Metrics
- **PESQ** — Perceptual Evaluation of Speech Quality
- **STOI** — Short-Time Objective Intelligibility
- **SI-SNR** — Scale-Invariant Signal-to-Noise Ratio
- **DNS Challenge** — Industry benchmark for real-time speech enhancement
- **Subjective listening tests** — Still gold standard; ML metrics don't fully capture perceived quality for hearing aid users

## Related Pages
- [[dnn-architectures-hearing-aids]] — Deep dive on hardware-specific DNN architectures and chip implementations
- [[on-device-ml-hearing-aids]] — Deployment target for these networks
- [[small-language-models-edge-ai]] — Compression techniques applicable to speech models
- [[auditory-attention-decoding]] — Next frontier: steering enhancement based on where user is listening
- [[cochlear-implant-ai]] — Speech enhancement DNNs adapted for cochlear implant users
