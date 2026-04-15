---
title: The Hearing Aid AI Stack — 2026 Landscape
type: synthesis
created: 2026-04-15
updated: 2026-04-15
sources: [small-language-models-edge-2026.md, large-sensor-models-arxiv-2026.md]
related: [../concepts/on-device-ml-hearing-aids.md, ../concepts/speech-enhancement-neural-networks.md, ../concepts/small-language-models-edge-ai.md, ../concepts/large-sensor-models.md]
tags: [landscape, ai-stack, architecture, 2026]
---

# The Hearing Aid AI Stack — 2026 Landscape

A synthesis of the current state of AI/ML in hearing aids, organized as a technology stack from hardware to user experience.

## Layer 1: Silicon
- Custom SoCs with dedicated DSP cores (all major manufacturers)
- Emerging: on-chip neural network accelerators (Demant Polaris, Starkey Edge)
- Power budgets: 1-5 mW total device power
- Trend: more transistors dedicated to ML inference vs. traditional DSP

## Layer 2: On-Device Models
- **Noise reduction:** DNNs replacing traditional Wiener filters
- **Scene classification:** CNN/RNN classifiers (quiet, speech, music, noise, outdoors, etc.)
- **Speech enhancement:** Compact neural nets (< 1M params)
- **Beamforming:** ML-steered directional microphones
- **Feedback cancellation:** Adaptive filters augmented with ML
- **Own voice processing:** Unique to WS Audiology/Signia

## Layer 3: Personalization
- **Fitting algorithms:** NAL-NL2, DSL v5, proprietary (prescription → gain curves)
- **On-device adaptation:** Devices learn user preferences over time
- **Audiologist adjustments:** Fine-tuning via manufacturer software (Phonak Target, Oticon Genie)
- **Self-adjustment:** Users tweak via smartphone apps, data feeds back

## Layer 4: Connectivity & Data
- **Bluetooth LE Audio / Auracast** — Emerging broadcast standard
- **Companion apps** — Data collection, remote control, health features
- **Cloud analytics** — Aggregated usage data for R&D
- **Remote fitting** — Teleaudiology via apps (accelerated by COVID)

## Layer 5: Ecosystem & Services
- **Health monitoring** — Fall detection, heart rate, activity (Starkey leading)
- **Translation** — Real-time speech translation (demo/experimental stage)
- **Cognitive health** — Hearing-cognition link monitoring (emerging research)
- **OTC self-fit** — Apple AirPods Pro, Jabra Enhance, Bose SoundControl

## What's Missing / Coming Next
1. **Foundation models for audio** — Pre-trained on massive audio datasets, fine-tuned for hearing
2. **Cross-device learning** — Federated learning across user populations
3. **Causal personalization** — Moving from correlation (users like X) to causation (setting X improves outcomes because Y)
4. **Sensor fusion** — Combining audio + motion + biometrics for holistic understanding (LSM concept)
5. **Real-time translation** — Requires significant compute advances at hearing aid scale

## Related Pages
- [[on-device-ml-hearing-aids]] — Layer 2 deep dive
- [[speech-enhancement-neural-networks]] — Key workload in Layer 2
- [[small-language-models-edge-ai]] — Model paradigm for Layers 2-3
- [[large-sensor-models]] — Potential future for Layer 2 initialization
