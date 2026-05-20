---
title: "Moonshine v2 — Useful Sensors Ergodic Streaming Encoder for Latency-Critical ASR"
source_type: model-release
type: industry-news
date: 2026-05
date_ingested: 2026-05-20
url: https://www.gladia.io/blog/best-open-source-speech-to-text-models
tags: [moonshine, useful-sensors, on-device-asr, streaming-asr, small-model, edge-ai, latency, hearing-aid-accessories, keyword-spotting]
---

# Moonshine v2 — Useful Sensors

## Key Extractions

- **Vendor:** Useful Sensors (founded by Pete Warden et al., known for the on-device "Person Sensor" and earlier TinyML work).
- **Model family:** Moonshine, an open ASR family designed for resource-constrained hardware.
- **Smallest variants:** ~27M parameters — comparable in footprint to Whisper-tiny but architected for latency-first rather than accuracy-first deployment.
- **v2 contribution:** an "Ergodic Streaming Encoder" specifically targeting latency-critical applications where every frame's emission delay matters (vs. typical chunked/lookahead streaming encoders).
- **Positioning:** Open-source, runs on commodity microcontrollers and mobile NPUs without cloud connectivity.

## Relevance for Hearing Tech

Three immediate hooks for hearing-aid and hearable accessories:

1. **On-aid keyword spotting** — sub-frame ASR is the substrate for hands-free control of program switching, beam steering, accessory pairing.
2. **Remote-mic / companion-device caption pipelines** — when an aid-paired phone or remote mic is doing the heavy lifting, a sub-30M-param streaming ASR with tight latency keeps captions usable.
3. **Federated personalization** — a model this small is feasible to *fine-tune on-device* on a user's voice or accent without shipping audio off-device, dovetailing with the federated TinyML thread elsewhere in the wiki.

Worth tracking against AONDevices, Aizip, and other edge-ASR vendors for hearing-aid accessory integration.
