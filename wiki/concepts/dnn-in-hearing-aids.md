---
title: Deep Neural Networks in Hearing Aids
type: concept
created: 2026-04-15
updated: 2026-04-15
sources: [dnn-effectiveness-frontiers-2025.md, selective-noise-cancellation-arxiv-2025.md, low-latency-dnn-noise-reduction-frontiers-2025.md]
related: [on-device-ml-hearing-aids.md, speech-enhancement-neural-networks.md, hearing-aid-chip-architectures.md, dnn-architectures-hearing-aids.md]
tags: [dnn, hearing-aids, history, inference, on-device, training-data, latency]
---

# Deep Neural Networks in Hearing Aids

An overview of how deep neural networks entered hearing aids: the historical milestones, how inference works on-device, key performance metrics, and the constraints that shape every design decision.

## History

### Pre-DNN Era (before 2021)
Hearing aids processed audio using classical digital signal processing (DSP): spectral subtraction, Wiener filtering, and rule-based directional microphone algorithms. These worked well for stationary noise but struggled in complex, unpredictable acoustic environments — restaurants, parties, busy streets.

### The First DNN Hearing Aid: Oticon More (2021)
Oticon More, launched in January 2021, was the **world's first commercially available DNN hearing aid**. Key facts:
- Trained on **12 million real-world sound scenes**
- On-device DNN runs continuously, classifying acoustic environment and guiding noise reduction
- Built on Oticon's Polaris chip platform
- Claimed measurable improvement in speech understanding over prior-generation classical DSP devices

### Rapid Industry-Wide Adoption (2022–2025)
Every major hearing aid manufacturer launched DNN-equipped devices within two years of Oticon More:
- Phonak Lumity (2022) — PRISM platform with dual-chip neural processing
- Starkey Genesis AI (2023) — Starkey Neuro Processor
- ReSound Nexia / Vivia (2024-2025) — 360+DNN architecture
- Signia Integrated Xperience (2023-2024)
By 2025, DNN processing was effectively table-stakes for premium hearing aids; it was also entering mid-tier OTC devices.

## How DNN Inference Works in Hearing Aids

### Training Phase (Cloud)
1. A massive dataset of sound scenes is assembled — typically 12M to 22M synthetic mixtures of speech, noise, and room acoustics
2. A DNN is trained (in the cloud, on GPU clusters) to predict a noise mask or enhanced speech signal
3. The trained model is compressed (quantization, pruning, knowledge distillation) to fit within chip memory and power budgets
4. The compressed model is embedded in firmware and shipped with the device

### Inference Phase (On-Device, Real-Time)
1. Hearing aid microphones capture audio at 16,000–24,000 samples/second
2. Audio is framed into short windows (1–10ms)
3. The on-device DNN runs forward pass on each frame, producing a noise mask or enhanced output
4. Processed audio is delivered to the speaker within the latency budget
5. This loop runs continuously, 24/7, on a battery the size of a shirt button

No cloud connectivity is involved during normal operation. This is non-negotiable for latency and privacy reasons.

## Key Architectures

See [[dnn-architectures-hearing-aids]] and [[speech-enhancement-neural-networks]] for detailed architecture breakdowns. Summary:

| Architecture | Status | Strengths |
|-------------|--------|-----------|
| CRN (Convolutional Recurrent Network) | Production optimal | Handles stationary + non-stationary noise; causal; fits chip constraints |
| Transformer / SepFormer | Research / teacher model | Long-range dependencies; too compute-heavy for direct deployment |
| Attention-based hybrid | Emerging | Lightweight attention variants targeting <1ms latency |
| Feedforward DNN | Legacy | Simple, fast; accuracy limited in complex scenes |

### Attention-Based Selective Noise Cancellation
Emerging architecture class (2025): context-aware attention mechanisms that selectively cancel specific noise sources (e.g., suppress HVAC hum but preserve a companion's voice) rather than applying a global noise mask. Represents a shift from environment-blind suppression to semantically-aware enhancement.

## Key Performance Metrics

### SNR Improvement
- Typical DNN systems achieve **5–15 dB SNR improvement** over unprocessed audio
- Classical DSP typically achieves 3–8 dB in the same conditions
- Improvement is most pronounced in non-stationary, multi-source noise

### Speech Intelligibility
- Measured via Word Recognition Score (WRS) or Speech Intelligibility Index (SII)
- DNN hearing aids show statistically significant WRS improvement in noisy environments versus classical DSP
- Oticon More clinical studies reported ~3 dB better SNR50 (SNR at 50% word recognition) vs. prior Oticon generation

### Latency
- **Hard upper limit: 10ms algorithmic latency** — users perceive delay and lip-sync artifacts above this
- Current production systems: 5–8ms DNN block latency
- Emerging target: **<1ms** for noise reduction block (enables lower-latency total system)
- Latency is measured from microphone sample in to speaker sample out

## Training Data Scales

| Manufacturer Tier | Sound Scene Count | Notes |
|------------------|-------------------|-------|
| Oticon More (2021) | 12M | First generation; real-world recordings |
| Later-gen large manufacturers | 13.5M–22M | Synthetic mixing + HA mic simulation |
| Emerging research | >22M | Expanding to rare acoustic edge cases |

Training data composition matters as much as scale:
- **Noise diversity:** factory, restaurant, traffic, babble, music, wind, appliance hum
- **Room acoustics:** reverberant rooms, open spaces, car interiors
- **HA microphone simulation:** critical for bridging lab training to real-device performance
- **Language and accent coverage:** multilingual for global markets

## Real-Time vs Cloud-Based DNN

| Dimension | On-Device (Hearing Aids) | Cloud-Based (Experimental) |
|-----------|--------------------------|---------------------------|
| Latency | <10ms, mandatory | 50–200ms round-trip — unacceptable |
| Privacy | Audio never leaves device | Requires audio streaming |
| Connectivity | None required | Requires reliable BT + internet |
| Model size | <1M–5M parameters | Unconstrained |
| Power | <1mW for ML block | Handled by cloud |
| Personalization | Static model, updated via firmware | Could adapt per-session |

**Cloud-based DNN inference is not viable for primary hearing aid processing** due to latency requirements. Cloud may play a role in offline model personalization and firmware updates, but real-time audio must be processed on-device.

## Clinical and Market Significance
- DNN hearing aids consistently outperform classical DSP in clinical trials for noisy environments — the primary complaint of hearing aid users
- DNN capability is now a premium differentiator; "AI hearing aid" is standard marketing language across the Big 5
- Training data scale and architecture quality are becoming competitive moats — large manufacturers have 10–20x more training data than smaller players

## Related Pages
- [[dnn-architectures-hearing-aids]] — Detailed CRN, SepFormer, and chip-level architecture deep-dive
- [[on-device-ml-hearing-aids]] — Hardware and deployment context for DNN inference
- [[speech-enhancement-neural-networks]] — Full architecture catalog with latency and benchmark analysis
- [[hearing-aid-chip-architectures]] — NPU vs dual-chip chip design debate

## Sources
- [DNN Effectiveness Frontiers 2025](../../sources/dnn-effectiveness-frontiers-2025.md) — Clinical evidence for DNN hearing aid performance
- [Selective Noise Cancellation arXiv 2025](../../sources/selective-noise-cancellation-arxiv-2025.md) — Context-aware attention-based noise cancellation architectures
- [Low-Latency DNN Noise Reduction Frontiers 2025](../../sources/low-latency-dnn-noise-reduction-frontiers-2025.md) — Sub-1ms latency DNN research
