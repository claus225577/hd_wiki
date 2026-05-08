---
title: "TinyML Speech Recognition: 97% Accuracy on Arduino Nano 256KB RAM"
type: paper
date: 2025-04-23
url: https://arxiv.org/abs/2504.16213
tags: [tinyml, speech-recognition, edge-ai, keyword-spotting, microcontroller, arduino, ultra-low-resource]
---

# TinyML Speech Recognition on Arduino Nano

**Authors:** Barovic & Moin
**arXiv:** 2504.16213

## Key Findings

- Achieves **97% accuracy** on speech recognition task
- Recognizes **23 keywords** — sufficient vocabulary for hearing aid control commands
- Runs on **Arduino Nano with 256KB RAM** — among the most resource-constrained platforms for ML inference
- Demonstrates that meaningful speech recognition is possible at extreme edge with sub-megabyte memory

## Significance for Hearing AI

- **Hearing aid memory budgets:** 256KB is within range of hearing aid SRAM budgets (typically 256KB–2MB) — this directly validates keyword spotting on hearing aid hardware class
- **23 keywords at 97%:** Sufficient for a hearing aid command vocabulary (volume up/down, program change, mute, call, assistant trigger, etc.)
- **Ultra-low resource proof point:** Shows the floor for on-device speech recognition has dropped to microcontroller level — no NPU or GPU required
- **Potential applications in hearing aids:**
  - Voice-activated program switching
  - Hands-free hearing aid control for users with dexterity limitations
  - Wake-word detection for assistant integration
  - Acoustic event detection (doorbell, alarm, name call)
- **Complements (not replaces) DNN enhancement:** Keyword spotting runs alongside the speech enhancement pipeline as a separate lightweight task
- Validates the TinyML trajectory for hearing devices — useful ML tasks can run on the smallest hardware
