---
title: Speech Enhancement Neural Networks
type: concept
created: 2026-04-15
updated: 2026-04-15
sources: [dnn-noise-reduction-intelligibility-2026.md, sub-millisecond-speech-enhancement-hearables-2025.md, multichannel-deep-speech-enhancement-ha-2024.md, speech-foundation-models-hearing-impaired-2024.md, ssl-loss-functions-hearing-aid-enhancement-2024.md]
related: [on-device-ml-hearing-aids.md, small-language-models-edge-ai.md, dnn-architectures-hearing-aids.md, auditory-attention-decoding.md, cochlear-implant-ai.md, vcca-computational-audiology.md]
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

## Recent Academic Advances (2024–2026)

### Sub-Millisecond Latency (2025)
Achieved 0.32–1.25 ms mean algorithmic latency using minimum-phase FIR filter for sample-by-sample processing on hearables. Eliminates comb-filter artifacts entirely (arXiv, 2025).

### Ultra-Low Latency DNN Noise Reduction (2026)
Pre-trained convolutional time-domain network achieving 1 ms latency. Validated on normal-hearing, hearing-impaired, and CI users. Published in Frontiers in Audiology and Otology.

### Binaural Deep Speech Enhancement (2024)
IEEE/ACM TASLP paper comparing monaural vs. binaural DNN processing. Shows binaural processing preserves spatial cues (ITD/ILD) while enhancing speech — solving a key limitation of earlier independent-ear processing.

### Self-Supervised Speech Models as Loss Functions (2024)
Novel approach using self-supervised speech representations in the loss function during training (not as input features). Produces enhancement models better aligned with hearing-impaired perceptual quality. Connected to Clarity Challenge; funded by WS Audiology and Toshiba.

### Foundation Models for Intelligibility Prediction (2024)
Self-supervised speech models (e.g., NVIDIA Parakeet, 600M params, 120k hours) correlate better with human intelligibility ratings than PESQ/STOI. Opens path to non-intrusive quality prediction without listener panels.

## Related Pages
- [[dnn-architectures-hearing-aids]] — Deep dive on hardware-specific DNN architectures and chip implementations
- [[on-device-ml-hearing-aids]] — Deployment target for these networks
- [[small-language-models-edge-ai]] — Compression techniques applicable to speech models
- [[auditory-attention-decoding]] — Next frontier: steering enhancement based on where user is listening
- [[cochlear-implant-ai]] — Speech enhancement DNNs adapted for cochlear implant users
- [[vcca-computational-audiology]] — Central topic across all VCCAs

## Sources
- [Sub-ms Latency Speech Enhancement](../sources/sub-millisecond-speech-enhancement-hearables-2025.md)
- [Low-Latency DNN Noise Reduction](../sources/dnn-noise-reduction-intelligibility-2026.md)
- [Binaural Deep Speech Enhancement](../sources/multichannel-deep-speech-enhancement-ha-2024.md)
- [SSL Loss Functions for HA Enhancement](../sources/ssl-loss-functions-hearing-aid-enhancement-2024.md)
- [Speech Foundation Models for HI Prediction](../sources/speech-foundation-models-hearing-impaired-2024.md)
