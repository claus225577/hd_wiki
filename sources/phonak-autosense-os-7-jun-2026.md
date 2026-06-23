---
title: Phonak AutoSense OS 7.0 Announcement (June 2026)
type: source
source_type: vendor-whitepaper
created: 2026-06-23
date_published: 2026-06
url: https://www.phonak.com/content/dam/phonak/en/evidence-library/white-paper/technical-paper/PH_Insight_AutoSenseOS7.0_210x297_EN_029-1459-02_V1.00.pdf
tags: [phonak, autosense-os, automatic-scene-classification, dnn, firmware-update, infinio-ultra]
related: [../wiki/entities/phonak.md, ../wiki/entities/sonova-ag.md, ../wiki/concepts/dnn-in-hearing-aids.md, ../wiki/concepts/on-device-ml-hearing-aids.md]
---

# Phonak AutoSense OS 7.0 Announcement (June 2026)

## Summary

Phonak announced AutoSense OS 7.0 as part of the Infinio Ultra firmware refresh in June 2026. AutoSense OS is Phonak's automatic environment-detection system that classifies the listening scene and selects the appropriate processing program. Version 7.0 is a model-only update — delivered as a free firmware upgrade to existing Infinio and Infinio Sphere wearers — rather than a hardware change.

## Headline Numbers

- **24% more precise** at classifying listening situations than v6.0
- **18× more real-world training scenarios** than v6.0 (the underlying scene database was expanded ~18-fold)
- **30% better battery efficiency** vs v6.0
- **One-step Bluetooth pairing** (replacing previous multi-step flow)
- **Faster feedback management** in the AFC loop

## Delivery Mechanism

- Free firmware update via the hearing care provider's fitting software (Target)
- Available for all Phonak Infinio and Infinio Sphere devices
- On Sphere models specifically, the same firmware refresh also brings **Spheric Speech Clarity 2.0**
- Same delivery model Phonak used for the **October 2025 Ultra firmware refresh** that pushed an 18×-data DEEPSONIC model update over the air — establishing a pattern of post-deployment model improvements

## Why It Matters

1. **Demonstrates continued post-deployment model improvement** — Phonak is now on a roughly twice-a-year cadence of meaningful firmware model updates (Oct 2025 → Jun 2026), more like a software product than a traditional hearing aid release cycle
2. **Scene-classifier scaling continues** — the 18× scenario expansion is the same scaling lever Phonak pulled in Oct 2025 for the DNN noise reducer, suggesting Sonova has built a reusable real-world data pipeline they can apply across blocks (classifier, denoiser, etc.)
3. **Auracast / one-step BT pairing is now a competitive differentiation axis** — Starkey shipped a similar Auracast-assistant connectivity refresh in Jan 2026 (Edge AI) and again in 2026 for Omega AI; Phonak's one-step pairing pushes the OEMs toward consumer-electronics-grade pairing UX
4. **Battery efficiency improvement at the model level** matters because battery life dropped to ~10–11h with DEEPSONIC AI block active per the June 2026 HearingTracker review — every model-level efficiency gain widens the AI-on duty cycle

## Context Within Sonova's AI Story

- **Hardware:** DEEPSONIC dual-chip (7.7B ops/sec, 4.5M neural connections, trained on 22M sound scenes)
- **AI feature blocks:** Spheric Speech Clarity (now 2.0 on Sphere), DNN noise reduction (April 2026 clinical trial NCT07526428), AutoSense OS scene classifier (now 7.0)
- **Post-deployment update cadence:** Oct 2025 Ultra firmware → Jun 2026 AutoSense OS 7.0 + Spheric Speech Clarity 2.0
- AutoSense OS 7.0 sits *upstream* of the DEEPSONIC AI feature blocks — it's the soft router that decides which block(s) to engage

## Open Questions

- Is AutoSense OS 7.0 a discriminative classifier upgrade (more training data, same model class) or an architectural shift (e.g., to a small Transformer-class scene model)? Phonak's whitepaper frames it as a scene-database expansion, suggesting the former
- Does the +30% battery efficiency come from the classifier itself (less compute per inference) or from smarter routing (engaging DEEPSONIC AI blocks less often)? The latter would be more interesting because it suggests AutoSense OS 7.0 is now learning a *cost-aware* policy over the AI block stack
- How does AutoSense OS 7.0 interact with the user-controllable on-demand AI primitive (where the wearer presses a button to enable the AI block)? Does the classifier still override the user, or has Sonova moved to a fully user-deferential policy?

## Sources

- [Phonak — AutoSense OS 7.0 Whitepaper (PDF)](https://www.phonak.com/content/dam/phonak/en/evidence-library/white-paper/technical-paper/PH_Insight_AutoSenseOS7.0_210x297_EN_029-1459-02_V1.00.pdf) — primary
- HearingTracker / industry coverage (June 2026 Infinio Ultra rollout)
