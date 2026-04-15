---
title: Phonak
type: entity
created: 2026-04-15
updated: 2026-04-15
sources: []
related: [sonova-ag.md, ../concepts/on-device-ml-hearing-aids.md, gn-hearing-resound.md, demant-oticon.md]
tags: [company, brand, phonak, sonova, deepsonic, ai-hearing-aid, dual-chip]
---

# Phonak

Primary hearing aid brand of Sonova AG. One of the world's top-selling hearing aid brands. Manufactured and owned by Sonova AG (Swiss parent company, headquartered in Stäfa).

For Sonova AG corporate structure, financials, and brands overview, see [[sonova-ag]].

## Current Flagship Products

### Audéo Sphere Infinio
- Phonak's flagship AI hearing aid
- Powered by the **DEEPSONIC chip** (dual-chip architecture)
- One of only **2 products globally** with real-time AI neural network processing as of mid-2025 (alongside ReSound Vivia)
- Key features: Spheric Speech Clarity, real-time DNN inference, AI-driven environment adaptation

### Virto R Infinio
- Custom hearing aid (ITE/ITC form factors) with Infinio AI platform
- DEEPSONIC-powered; brings AI processing to fully in-ear custom devices
- Rechargeable (the "R" designation)

## DEEPSONIC Chip (Core Technology)
- **7.7 billion operations per second**
- **4.5 million neural network connections** on-device
- **Dual-chip architecture**: dedicated AI co-processor alongside main audio SoC
- **53x more processing power** than industry standard (single-chip competitors)
- Trained on **22 million sound scenes**

See [[sonova-ag]] for full DEEPSONIC architecture details.

## Key AI Feature: Spheric Speech Clarity
- AI-driven speech processing that leverages DEEPSONIC compute to separate and enhance speech from complex acoustic backgrounds
- "Spheric" refers to 360-degree spatial audio awareness — not beam-limited like traditional directional microphones
- Version 2.0 ships with current Infinio Ultra devices

## Firmware & Ongoing Model Updates
- **Ultra firmware update (Oct 2025)**: delivered 18x more real-world training data to deployed devices via over-the-air update
- Demonstrates Phonak's post-deployment model improvement capability — analogous to how software companies ship model updates

## Awards & Recognition
- **2026 AI Excellence Award** — Industry recognition for the DEEPSONIC/Infinio platform

## Phonak vs. Competitors on AI Processing (Mid-2025 Snapshot)
| Product | AI Architecture | Training Data | Ops/sec |
|---------|----------------|---------------|---------|
| Phonak Audéo Sphere Infinio | Dual-chip (DEEPSONIC) | 22M sound scenes | 7.7B |
| ReSound Vivia | Dedicated DNN chip | 13.5M sentences | ~4.9T ops/day |
| Oticon Intent | Integrated DNN accelerator (single-chip) | 13M sound scenes | Not published |

Note: ops/sec comparisons should be treated cautiously — different architectures optimize for different workloads, and manufacturer claims use different measurement methodologies.

## Other Phonak Products & Ecosystem
- **Roger** — Proprietary wireless remote microphone system for classrooms and noisy environments; used in pediatric audiology and education
- **myPhonak app** — Consumer app; remote fine-tuning, hearing diary, usage data
- **Lumity line** — Previous generation (PRISM chip); still available/supported

## Position Within Sonova
Phonak accounts for the majority of Sonova AG's hearing aid revenue. Unitron is the mid-tier brand; Advanced Bionics handles cochlear implants. AudioNova is the retail arm. Phonak R&D drives Sonova's core chip investment (PRISM → DEEPSONIC).

## Related Pages
- [[sonova-ag]] — Parent company; corporate structure, financials, full brand portfolio
- [[gn-hearing-resound]] — ReSound Vivia is the only other product with real-time AI processing (mid-2025)
- [[demant-oticon]] — Single-chip competitor; architectural contrast
- [[on-device-ml-hearing-aids]] — DEEPSONIC dual-chip as key architecture case study

## Sources
- Research notes on DEEPSONIC chip specs, Audéo Sphere Infinio, Oct 2025 Ultra firmware update, 2026 AI Excellence Award
