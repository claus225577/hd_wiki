---
title: "PAS-SE: Personalized Auxiliary-Sensor Speech Enhancement for Hearables"
url: https://arxiv.org/list/eess.AS/recent
date: 2026-04-26
type: paper
tags: [speech-enhancement, hearables, personalization, multi-sensor, icassp-2026, on-device]
---

# PAS-SE — Personalized Auxiliary-Sensor Speech Enhancement

## Summary
Accepted at **ICASSP 2026**. Introduces a speech-enhancement architecture that fuses the primary acoustic mic with an **auxiliary in-ear sensor stream** (e.g., bone-conduction / accelerometer / occlusion-pickup) to personalize voice pickup for the wearer. The auxiliary sensor provides a clean reference biased toward the wearer's own voice; the model uses it both as a target signal and as a personalization conditioning input.

## Why It Matters
- Personalization without cloud: the in-ear sensor is the personalization signal — no per-user training corpus, no profile upload.
- Robust to confusable talkers: external mics alone struggle to separate the wearer from a nearby same-pitch speaker; aux-sensor fusion is one of the few reliable cues for "is this me?"
- Directly relevant to **own-voice processing** in hearing aids — a long-standing pain point (occlusion, voice quality).
- Likely candidate for next-gen hearable SoCs that already expose IMU/bone-conduction telemetry.

## Open Questions / Limits
- Power: a second sensor stream and fusion model competes with the audio NN budget on a hearing-aid DSP.
- Generalization to hearables with mechanically different sensor placements.
- Whether the architecture is end-to-end deployable on existing HA chip families (Sonova ERA, GN Cosmos, Widex Pure Sound).

## Related
- `dnn-architectures-hearing-aids.md`
- `speech-enhancement-neural-networks.md`
- `on-device-ml-hearing-aids.md`
