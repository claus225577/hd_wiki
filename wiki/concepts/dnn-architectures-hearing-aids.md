---
title: Deep Neural Network Architectures for Hearing Aids
type: concept
created: 2026-04-15
updated: 2026-04-15
sources: []
related: [speech-enhancement-neural-networks.md, on-device-ml-hearing-aids.md, small-language-models-edge-ai.md, cochlear-implant-ai.md]
tags: [dnn, crn, transformer, cnn, rnn, hearing-aids, chips, low-latency, sepformer]
---

# Deep Neural Network Architectures for Hearing Aids

A technical survey of DNN architectures deployed or under active research for hearing aid signal processing, with emphasis on the compute/latency tradeoffs that govern real-world viability.

## The Core Constraint

Hearing aid DNNs must satisfy simultaneous requirements no other ML deployment faces:

| Constraint | Value | Reason |
|-----------|-------|--------|
| Algorithmic latency | < 10ms (1ms target) | Above this, users perceive delay |
| Power budget | < 1mW for ML block | Battery the size of a shirt button |
| Memory | 256KB–2MB SRAM | Full model must fit on-chip |
| Throughput | 16,000+ samples/sec | Real-time audio, no buffering |
| Deployment | No cloud, no WiFi | Privacy + always-on requirement |

## Optimal Architecture: Convolutional Recurrent Networks (CRN)

CRN is widely considered the **optimal production architecture** for hearing aid DNN processing as of 2025-2026.

### Why CRN Works
- **CNN layers** extract spatial and spectral features — good at pattern matching across frequency bins and microphone channels simultaneously
- **RNN layers** (LSTM or GRU) model temporal dynamics — handle non-stationary noise that changes over time
- The combination covers both the "what does this noise look like" (CNN) and "how is it evolving" (RNN) problems
- Causal architecture: only uses past audio frames, enabling true real-time processing

### CRN Variants
- **DCCRN** — Deep Complex CRN: operates on complex spectrogram to preserve phase information
- **DPCRN** — Dual-Path CRN: separates local and global temporal modeling
- **Lightweight CRN** — Stripped to ~200K parameters for extreme power budgets

## Transformer-Based Architectures (SepFormer)

**SepFormer** (Separation Transformer) uses dual self-attention: intra-chunk attention for local dependencies and inter-chunk attention for global context.

- State-of-the-art on WSJ0-2mix and WHAMR! benchmarks
- Captures much longer temporal dependencies than RNNs
- **Problem for hearing aids:** Attention is O(n²) in sequence length — prohibitively expensive for streaming audio
- **Current role:** Used as a **teacher model** for knowledge distillation into smaller CRN student models
- Active research into causal, linear-attention variants to reduce compute

## Time-Domain vs Frequency-Domain

### Time-Domain Processing
- Operates directly on audio waveform samples
- No explicit phase reconstruction step needed
- Example: Conv-TasNet, DEMUCS
- **Tradeoff:** Larger receptive fields needed; harder to constrain latency

### Frequency-Domain Processing
- Converts audio to STFT or filterbank representation first
- Well-understood signal properties; integrates with existing DSP pipeline
- Phase reconstruction (Griffin-Lim or neural phase estimator) adds complexity
- **Dominant in production** due to predictable behavior and DSP integration

### Hybrid Time-Frequency
- CRN variants that take filterbank features but reconstruct in time domain
- Tries to capture advantages of both; adds training complexity

## Ultra-Low Latency: 1ms DNN Target

Standard hearing aid latency budgets allow ~5-8ms for the DNN block. Emerging research targets **1ms latency** for noise reduction:

- Requires extremely short audio frames (often 1ms = 16 samples at 16kHz)
- Forces very shallow networks or highly parallelized convolutions
- Makes RNN hidden state the computational bottleneck (must compute in < 1ms per frame)
- Often achieved by reducing model depth and increasing parallel channels

## Chip-Level Implementation

### DEEPSONIC Chip
A frontier hearing AI chip demonstrating:
- **7.7 billion operations per second** (7.7 GOps/s)
- **4.5 million neural connections** (weights)
- Sub-milliwatt power for DNN inference
- Purpose-built for streaming audio with in-chip weight storage

### Sonova Dual-Chip Architecture
Phonak Infinio uses separate chips for classical DSP and neural processing:
- **DSP chip:** handles deterministic signal processing (compression, fitting curve)
- **ML chip:** runs DNN noise reduction and scene classification
- Advantage: each processor optimized for its workload, no resource contention
- Disadvantage: two chips = more power, more complex interconnect

### Demant Single-Chip Architecture
Oticon Intent uses a unified SoC:
- DSP and neural processing share silicon
- Lower total power at cost of scheduling complexity
- Better integration between DSP and ML processing steps
- Single chip revision needed to update either capability

## Training Data Scale

The quality gap between small and large manufacturers is largely a data problem:

| Scale | Sound Scenes | Approximate Manufacturer Tier |
|-------|-------------|-------------------------------|
| ~1M scenes | Regional/smaller players | — |
| 13.5M scenes | Large manufacturer lower end | — |
| 22M scenes | Large manufacturer upper end | — |

Scenes are synthetically generated by mixing:
- Speech: multiple languages, accents, talker distances, room impulse responses
- Noise: factory, restaurant, traffic, multi-talker babble, music
- Hearing aid microphone simulation: realistic mic frequency response + noise floor

## Neural Architecture Search (NAS) for Hearing Aids

Given the extreme constraints, several manufacturers use automated NAS to find Pareto-optimal architectures on the latency/accuracy/power frontier:
- Search space: number of layers, channels, kernel sizes, RNN hidden dimensions
- Objective: maximize STOI/SI-SNR improvement subject to latency and FLOP budget
- Result: models that humans would not design intuitively

## Related Pages
- [[speech-enhancement-neural-networks]] — Architecture catalog including CRN, SepFormer, and legacy models
- [[on-device-ml-hearing-aids]] — Hardware context: chips, power budgets, memory constraints
- [[small-language-models-edge-ai]] — Model compression techniques (distillation, quantization, pruning)
- [[cochlear-implant-ai]] — Parallel DNN development for cochlear implant signal processors
