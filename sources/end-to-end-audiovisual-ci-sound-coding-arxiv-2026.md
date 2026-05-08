---
title: "End-to-End Audio-Visual Learning for Cochlear Implant Sound Coding"
url: https://arxiv.org/html/2508.13576v1
date: 2026-04-23
type: paper
tags: [cochlear-implant, audio-visual, lip-reading, sound-coding, deep-learning, multimodal, noise-robustness, arxiv]
---

# End-to-End Audio-Visual Learning for CI Sound Coding

## Key Extraction

- **Combines audio and visual modalities** for cochlear implant sound coding in noisy environments
- **Leverages lip-reading signals** — uses visual information from the speaker's face to supplement degraded audio
- **End-to-end architecture** — learns directly from raw audio + video inputs to produce CI electrodogram outputs
- **Noisy environment focus** — designed for conditions where audio-only CI processing degrades significantly

## Significance

- **First end-to-end audio-visual CI sound coding system** — previous CI sound coding strategies (ACE, CIS, etc.) are purely audio-based
- **Lip-reading as a CI input** is a natural extension: CI users already rely heavily on lip-reading as a compensatory strategy; this formalizes it computationally
- **Addresses CI's core limitation:** With only ~20 spectral channels, CI users struggle in noise far more than hearing aid users. Adding visual information provides an independent noise-robust signal
- **End-to-end learning** means the model jointly optimizes audio processing, visual processing, and electrodogram generation — avoiding the suboptimality of separate, hand-designed pipeline stages

## Technical Details

- **Input:** Microphone audio + camera video of speaker's face
- **Output:** Electrodogram — the pattern of electrical pulses delivered to CI electrodes
- **Training:** End-to-end with a loss function tied to speech intelligibility metrics for CI users
- **Multimodal fusion:** Learns to weight audio vs. visual signals based on noise conditions — in quiet, audio dominates; in noise, visual gains weight

## Relevance to Hearing + AI

- **Extends multimodal AI to cochlear implants** — hearing aids are adding sensors (4D, health); CIs adding visual modality
- **Hardware implications:** Requires a camera (smartphone, smart glasses, or future CI accessory) — not yet feasible in standalone CI processors
- **Practical deployment path:** Most likely first as a smartphone app that processes audio-visual input and streams optimized audio to the CI processor
- **Research precursor to audio-visual hearing aids** — if successful for CI, the approach could be adapted for hearing aid users in extreme noise
- Connects to the broader trend of multimodal AI in hearing devices (head rotation in hearing aids, lip-reading in CIs)
