---
title: On-Device ML in Hearing Aids
type: concept
created: 2026-04-15
updated: 2026-04-15
sources: [small-language-models-edge-2026.md, large-sensor-models-arxiv-2026.md]
related: [small-language-models-edge-ai.md, large-sensor-models.md, speech-enhancement-neural-networks.md]
tags: [edge-ai, hearing-aids, inference, dsp, chips]
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

## Hardware Landscape
- **Dedicated audio DSPs** — Most hearing aids use custom or semi-custom DSP chips (e.g., Sonova's PRISM chip)
- **ARM Cortex-M class** — Some newer designs use general-purpose microcontrollers alongside DSPs
- **NPUs** — Emerging: dedicated neural processing units on hearing aid SoCs
- Power budgets: typically 1-5 mW total for the entire device

## Key Players & Their Chips
- **Sonova:** PRISM platform (Phonak Lumity, Infinio)
- **Demant:** Polaris platform (Oticon Real, Intent)
- **Starkey:** Custom Starkey chips with "Edge AI"
- **WS Audiology:** TwinLink platform
- **GN Hearing:** Organic Hearing platform (ReSound)

## Emerging Capabilities
- On-device learning / personalization (adapting to user preferences over time)
- Real-time translation (requires more compute than currently available)
- Health monitoring (heart rate from in-ear sensors)
- Fall detection (via accelerometer + ML)

## Related Pages
- [[small-language-models-edge-ai]] — The model paradigm that makes on-device ML feasible
- [[speech-enhancement-neural-networks]] — Primary ML workload on hearing aid chips
- [[large-sensor-models]] — Future: pre-trained models distilled for on-device deployment
