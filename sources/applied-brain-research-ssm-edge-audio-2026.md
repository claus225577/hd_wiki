---
title: "State Space Models for Edge AI — Real-time Voice & DSP"
type: industry-article
date_published: 2026-04-01
date_ingested: 2026-04-22
url: https://www.appliedbrainresearch.com/state-space-models
organization: Applied Brain Research
tags: [state-space-models, edge-ai, speech-to-text, text-to-speech, tsp1, hardware-accelerator, streaming-audio, wearables]
---

# Applied Brain Research: SSMs for Edge Audio (2026)

## Summary

Applied Brain Research (ABR) builds state space models specifically for streaming audio on edge devices. Their approach treats speech as a continuous signal rather than chunked frames, enabling real-time voice processing (STT, TTS, speech-to-intent) entirely on-device with their TSP1 hardware accelerator running at under 30mW.

## Key Details

- **SSMs for streaming audio:** Models process speech as a continuous signal, not windowed/chunked — natural fit for real-time audio applications
- **On-device capabilities:** Speech-to-text, text-to-speech, and speech-to-intent all running on-device without cloud
- **TSP1 hardware accelerator:** Custom chip running at under 30mW — designed specifically for SSM inference
- **Always-on voice processing:** Power budget enables continuous voice and biosignal processing for wearables
- **Target applications:** Wearables, IoT devices, always-on voice interfaces, biosignal processing

## Significance for Hearing AI

- **30mW is ~6-30x current hearing aid total power budget** (1-5mW), but represents a stepping stone — the trajectory from general wearable to hearing-aid-specific silicon typically compresses power by 10-50x
- **Streaming audio paradigm** aligns perfectly with hearing aid requirements — no buffering, no chunking, continuous causal processing
- **Speech-to-intent on-device** could enable voice-controlled hearing aid adjustment without a phone intermediary
- **Biosignal processing** on the same chip could enable combined audio + health monitoring (PPG, EEG for AAD)
- ABR's approach validates SSMs as a production-ready alternative to transformer/CRN architectures for real-time audio
