---
title: The Hearing Aid AI Stack — 2026 Landscape
type: synthesis
created: 2026-04-15
updated: 2026-04-18
sources: [small-language-models-edge-2026.md, large-sensor-models-arxiv-2026.md, oticon-verit-launch-april-2026.md, phonak-dnn-noise-reduction-clinical-trial-april-2026.md, auracast-ready-vs-enabled-venue-guides-april-2026.md, google-turboquant-iclr-2026.md, airpods-pro-3-hearing-health-april-2026.md]
related: [../concepts/on-device-ml-hearing-aids.md, ../concepts/speech-enhancement-neural-networks.md, ../concepts/small-language-models-edge-ai.md, ../concepts/large-sensor-models.md, ../comparisons/ai-hearing-aid-platforms-2026.md]
tags: [landscape, ai-stack, architecture, 2026, silicon, auracast]
---

# The Hearing Aid AI Stack — 2026 Landscape

A synthesis of the current state of AI/ML in hearing aids, organized as a technology stack from hardware to user experience.

## Layer 1: Silicon

Custom SoCs with dedicated DSP cores remain the foundation, but 2025–2026 has seen a meaningful jump in dedicated neural accelerator silicon.

### Key Chips (2025–2026)
| Chip | Manufacturer | Specs | Product |
|------|-------------|-------|---------|
| DEEPSONIC | Sonova (Phonak) | 7.7B ops/sec, dual-chip architecture | Phonak Sphere Infinio |
| DNN Chip | GN (ReSound) | 4.9 trillion operations/day | ReSound Vivia |
| 2nd-Gen AI | Demant (Oticon) | Single-chip, 2nd-gen AI | Oticon Verit (Apr 2026) |
| Polaris | Demant (Oticon) | Single-chip DNN 2.0 | Oticon Intent |
| Edge AI | Starkey | On-device ML | Genesis AI |
| H2 | Apple | General-purpose; hearing aid classification added 2024 | AirPods Pro 2 |

- Power budgets remain tight: 1–5 mW total device power
- Trend: more transistors dedicated to ML inference vs. traditional DSP
- Dual-chip designs (Sonova) trade PCB complexity for raw throughput
- Single-chip designs (Demant) trade throughput for form factor and power efficiency

### Generational Leap: Oticon Verit (April 2026)
Oticon Verit launched with "second-generation AI sound processing" — successor to DNN 2.0. Full architecture details not yet published, but the generational framing suggests a new or significantly updated SoC. Verit also brings Auracast and Google Fast Pair to Oticon's lineup.

### Clinical Evidence: Phonak DNN Trial (April 2026)
Phonak registered a clinical trial (NCT07526428) for DNN noise reduction in moderate-to-severe hearing loss — first trial targeting more severe loss populations with DNN technology.

### Real-Time AI: Only Two Products as of 2026
Of all marketed "AI" hearing aids, only two currently implement genuine real-time AI inference in the audio path:
- **Phonak Sphere Infinio** — DEEPSONIC dual-chip, real-time scene adaptation
- **ReSound Vivia** — Dedicated DNN chip, real-time Intelligent Focus

All others use AI for fitting, personalization, and background adaptation, not sample-by-sample audio processing.

## Layer 2: On-Device Models

- **Noise reduction:** DNNs replacing traditional Wiener filters
- **Scene classification:** CNN/RNN classifiers (quiet, speech, music, noise, outdoors, etc.)
  - Phonak: 22M scenes in training data
  - Oticon DNN 2.0: 13M scenes, plus 4D Sensor (head + body motion fusion)
  - ReSound: 13.5M sentences in training data
- **Speech enhancement:** Compact neural nets (< 1M params)
- **Beamforming:** ML-steered directional microphones
- **Feedback cancellation:** Adaptive filters augmented with ML
- **Own voice processing:** Unique to WS Audiology/Signia (OVP)
- **Ultra-low latency DNN:** 1ms time-domain processing (emerging; required for feedback cancellation and bone conduction paths)

### Processing Architecture Comparison
| Approach | Exemplar | Trade-off |
|----------|---------|-----------|
| Dual-chip raw power | Sonova/Phonak | Highest throughput, larger device, more power |
| Sensor fusion DNN | Demant/Oticon | Motion-aware but single-chip constrained |
| Cloud-hybrid DNN | WS Audiology/Signia | Larger effective model, latency risk for some functions |
| Health ecosystem | Starkey | Differentiates on sensors, not audio ML |
| Consumer chip | Apple (H2/H3) | General purpose, 5-min audiometry, OTC scale, 256 Hz PPG heart rate |

## Layer 3: Personalization

- **Fitting algorithms:** NAL-NL2, DSL v5, proprietary (prescription → gain curves)
- **On-device adaptation:** Devices learn user preferences over time
- **Audiologist adjustments:** Fine-tuning via manufacturer software (Phonak Target, Oticon Genie)
- **Self-adjustment:** Users tweak via smartphone apps, data feeds back
- **Signia DNN Assistant:** Cloud-based DNN that delivers personalization adjustments without a full clinic visit — a hybrid model where real-time audio stays on-device but fitting intelligence lives in the cloud

## Layer 4: Connectivity & Data

- **Bluetooth LE Audio / Auracast** — Emerging broadcast standard; key bridge between consumer and clinical devices. Auracast allows loop systems in public venues (theaters, airports) to broadcast directly to hearing aids and earbuds, reducing stigma and integration friction.
  - Auracast is expected to appear in public infrastructure (public transit, cinemas) through 2026–2028
  - Both hearing aid manufacturers and consumer audio brands (Sony, Apple) adopting Auracast
  - **April 2026:** Oticon Verit and Play SI ship with Auracast; venue installation guides published; "Ready vs Enabled" consumer education push underway
  - Consumer confusion between "Auracast Ready" (hardware capable, not yet active) and "Auracast Enabled" (active out of box) is an adoption barrier
- **Companion apps** — Data collection, remote control, health features
- **Cloud analytics** — Aggregated usage data for R&D
- **Remote fitting** — Teleaudiology via apps (accelerated by COVID, now standard)

## Layer 5: Ecosystem & Services

- **Health monitoring** — Fall detection, heart rate, activity (Starkey leading)
- **Translation** — Real-time speech translation (demo/experimental stage)
- **Cognitive health** — Hearing-cognition link monitoring (emerging research, ACHIEVE study data)
- **OTC self-fit** — Apple AirPods Pro 2 ($249, FDA-cleared OTC), Jabra Enhance, Bose SoundControl

### Apple AirPods Pro as Hearing Aid (2024–2026)
Apple AirPods Pro 2 received FDA OTC hearing aid clearance in 2024. AirPods Pro 3 (April 2026) deepened the disruption:
- FDA-approved hearing aid feature for mild-to-moderate loss
- 5-minute clinical-grade self-administered audiometry via iPhone
- **AirPods Pro 3 price: $200** (down from $249 for Pro 2) — now cheaper than ultra-affordable OTC
- **Heart rate monitoring** at 256 Hz via in-ear PPG — health monitoring convergence
- **Active hearing protection** — real-time sound exposure monitoring
- **67% more battery** in Transparency mode vs. previous gen
- **Continuous software updates** — device improves post-purchase
- Positioned as the primary OTC disruptor from consumer electronics, now with health monitoring parity

## What's Missing / Coming Next

1. **Foundation models for audio** — Pre-trained on massive audio datasets, fine-tuned for hearing; open-source MoE models (Qwen3.6-35B-A3B) demonstrate efficient inference at scale
1b. **Extreme model compression** — Google TurboQuant (ICLR 2026) achieves 6x KV cache compression at 3-bit with zero accuracy loss and no retraining. Combined with distillation and pruning, this trajectory could enable significantly more capable models on hearing aid chips. See [[model-compression]].
2. **Cross-device federated learning** — Training across user populations without centralizing raw audio data; privacy-preserving model improvement
3. **Causal personalization** — Moving from correlation (users like X) to causation (setting X improves outcomes because Y)
4. **Sensor fusion at scale** — Combining audio + motion + biometrics for holistic understanding (LSM concept); Oticon 4D Sensor now in both adult (Verit) and pediatric (Play SI) products
5. **Real-time translation** — Requires significant compute advances at hearing aid scale
6. **Auracast infrastructure rollout** — Venue installation now beginning (April 2026); consumer education on Ready vs Enabled distinction needed
7. **Clinical evidence for DNN efficacy** — Phonak clinical trial (NCT07526428) signals industry-wide push toward evidence-based DNN claims

## Related Pages
- [[on-device-ml-hearing-aids]] — Layer 2 deep dive
- [[speech-enhancement-neural-networks]] — Key workload in Layer 2
- [[small-language-models-edge-ai]] — Model paradigm for Layers 2-3
- [[large-sensor-models]] — Potential future for Layer 2 initialization
- [[ai-hearing-aid-platforms-2026]] — Platform-by-platform comparison table

## Sources
- [Small Language Models for Edge AI](../../sources/small-language-models-edge-2026.md)
- [Large Sensor Models (arXiv)](../../sources/large-sensor-models-arxiv-2026.md)
