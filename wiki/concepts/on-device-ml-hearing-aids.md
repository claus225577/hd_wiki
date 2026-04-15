---
title: On-Device ML in Hearing Aids
type: concept
created: 2026-04-15
updated: 2026-04-15
sources: [small-language-models-edge-2026.md, large-sensor-models-arxiv-2026.md]
related: [small-language-models-edge-ai.md, large-sensor-models.md, speech-enhancement-neural-networks.md, dnn-architectures-hearing-aids.md, auditory-attention-decoding.md, cochlear-implant-ai.md]
tags: [edge-ai, hearing-aids, inference, dsp, chips, deepsonic, neural-processing]
---

# On-Device ML in Hearing Aids

Machine learning inference running directly on hearing aid hardware, without cloud connectivity. This is the dominant paradigm for hearing aid AI due to latency, privacy, and connectivity constraints.

## Current ML Tasks Running On-Device
1. **Noise reduction** — Separating speech from background noise in real-time
2. **Acoustic scene classification** — Identifying environment (restaurant, outdoors, music, quiet) to select processing programs
3. **Speech enhancement** — Boosting speech clarity, especially in multi-talker scenarios
4. **Feedback cancellation** — Detecting and suppressing acoustic feedback loops
5. **Wind noise reduction** — Identifying and attenuating wind artifacts
6. **Directional processing** — Beamforming steered by ML-based source localization
7. **Health monitoring** — Heart rate from in-ear PPG sensors + ML classification
8. **Fall detection** — Accelerometer + ML (Starkey, others)

## Hardware Landscape
- **Dedicated audio DSPs** — Most hearing aids use custom or semi-custom DSP chips
- **ARM Cortex-M class** — Some newer designs use general-purpose microcontrollers alongside DSPs
- **NPUs** — Emerging: dedicated neural processing units on hearing aid SoCs
- Power budgets: typically 1-5 mW total for the entire device
- Memory: typically 256KB-2MB SRAM, flash for model weights

## Key Players & Their Chips
- **Sonova:** PRISM platform (Phonak Lumity, Infinio) — dual-chip approach separating DSP and ML processing
- **Demant:** Polaris platform (Oticon Real, Intent) — single-chip approach integrating DSP and DNN
- **Starkey:** Custom Starkey chips with "Edge AI" branding
- **WS Audiology:** TwinLink platform
- **GN Hearing:** Organic Hearing platform (ReSound Nexia, Vivia)

### DEEPSONIC Chip (Emerging)
A notable academic/startup chip demonstrating the frontier: **7.7 billion operations per second** with **4.5 million neural connections**, purpose-built for ultra-low-power DNN inference in hearing instruments. Benchmarks this against current commercial chips to show the trajectory of on-device neural compute.

### Sonova Dual-Chip vs Demant Single-Chip
| Approach | Sonova (dual-chip) | Demant (single-chip) |
|----------|-------------------|---------------------|
| Architecture | Separate DSP + ML processor | Unified SoC |
| Advantage | Each chip optimized for its task | Simpler design, lower total power |
| Disadvantage | Higher component count, more power | ML and DSP compete for resources |
| Flexibility | Can upgrade one chip independently | Requires full chip revision for change |

## Latency Constraints
- Users perceive processing delay above ~10ms
- **1ms latency DNN** targets are being pursued for noise reduction blocks
- Causal (non-lookahead) architectures are required — no future audio frames
- This rules out most standard Transformer architectures without modification

## Training Data Scales
On-device models are typically trained in the cloud on massive datasets:
- **13.5M–22M sound scenes** reported by leading manufacturers
- Synthetic mixing of speech + noise to cover rare acoustic conditions
- Hearing aid microphone simulation to bridge lab-to-device gap

## Emerging Capabilities
- **On-device learning / personalization:** Adapting to user preferences over time without cloud sync
- **Auditory attention decoding (AAD):** Using EEG/biosignals to steer beamforming toward attended speaker (see [[auditory-attention-decoding]])
- **Real-time translation:** Requires more compute than currently available on-chip
- **Health monitoring:** Heart rate from in-ear sensors, stress detection
- **Fall detection:** Via accelerometer + ML (shipping in some Starkey models)

## Related Pages
- [[dnn-architectures-hearing-aids]] — Detailed breakdown of DNN architectures used on these chips
- [[small-language-models-edge-ai]] — The model paradigm that makes on-device ML feasible
- [[speech-enhancement-neural-networks]] — Primary ML workload on hearing aid chips
- [[large-sensor-models]] — Future: pre-trained models distilled for on-device deployment
- [[auditory-attention-decoding]] — Next frontier for on-device intelligence
- [[cochlear-implant-ai]] — Parallel developments in cochlear implant processors

## Sources
- [Small Language Models Edge 2026](../../sources/small-language-models-edge-2026.md)
- [Large Sensor Models arXiv 2026](../../sources/large-sensor-models-arxiv-2026.md)
