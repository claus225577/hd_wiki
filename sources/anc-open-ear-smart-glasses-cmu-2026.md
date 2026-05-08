---
title: "Real-Time ANC for Open-Ear Smart Glasses"
type: paper
date: 2026-04-07
url: https://arxiv.org/abs/2604.05519
tags: [active-noise-cancellation, smart-glasses, open-ear, distributed-microphones, real-time]
---

# Real-Time ANC for Open-Ear Smart Glasses

**Authors:** Yuan, Liu et al.
**Affiliation:** Carnegie Mellon University (CMU)
**arXiv:** 2604.05519 (April 7, 2026)

## Key Findings

- **First real-time active noise cancellation system for open-ear smart glasses**
- Achieves **9.6 dB noise reduction** — significant for an open-ear form factor where traditional ANC is extremely challenging
- Uses **8 distributed microphones** placed around the glasses frame
- Effective frequency range: **100–1000 Hz** — targets the low-frequency range where ANC is most effective and most needed
- Open-ear design means no ear canal occlusion — fundamentally different from in-ear ANC (AirPods, hearing aids)

## Significance for Hearing AI

- **Extends ANC beyond earbuds/hearing aids:** Smart glasses represent a new form factor for hearing assistance without occluding the ear canal
- **Open-ear challenge:** Without a sealed ear canal, ANC must cancel noise in free-field conditions — dramatically harder than in-ear ANC which benefits from passive isolation
- **Distributed microphone array:** 8 mics around the frame enable spatial noise estimation that wouldn't be possible with 1-2 microphones in a hearing aid
- **100–1000 Hz band:** Targets low-frequency environmental noise (traffic, HVAC, crowd rumble) that is the primary masker of speech intelligibility
- **Complements hearing aid DNN:** Could work alongside neural speech enhancement — ANC handles low-frequency noise physically, DNN handles mid/high-frequency noise computationally (dual-layer paradigm, similar to Orka O1 Pro concept)
- **Smart glasses as hearing devices:** Supports the hearables convergence thesis — smart glasses could become an alternative hearing assistance platform alongside traditional hearing aids

## Technical Details

- Distributed microphone array with spatial filtering
- Real-time feedforward ANC architecture
- Signal processing optimized for open-ear acoustic path (no sealed cavity)
- 9.6 dB reduction represents useful improvement given the open-ear constraint (in-ear ANC systems typically achieve 20-40 dB)
