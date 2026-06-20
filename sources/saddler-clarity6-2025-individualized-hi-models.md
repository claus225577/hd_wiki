---
title: "Towards individualized models of hearing-impaired speech perception"
type: paper
authors: ["Mark R. Saddler", "Torsten Dau", "Josh H. McDermott"]
venue: "Proceedings of the 6th Clarity Workshop on Improving Speech-in-Noise for Hearing Devices"
year: 2025
date_ingested: 2026-06-20
tags: [task-optimized-dnn, hearing-impaired, intelligibility-prediction, clarity-challenge, dtu, mit, individualization, calibration-finding]
---

# Towards individualized models of hearing-impaired speech perception

**Authors:** Mark R. Saddler, Torsten Dau, Josh H. McDermott
**Venue:** Proceedings of the 6th Clarity Workshop on Improving Speech-in-Noise for Hearing Devices (2025)
**Labs:** DTU Hearing Systems (Saddler, Dau); McDermott Computational Audition Lab, MIT (McDermott)
**URL:** Saddler's publication page — https://msaddler.github.io/publications/

## Core finding

Task-optimized deep neural networks jointly trained for sound localization and speech recognition, evaluated through individualized hearing-loss simulations, can predict speech intelligibility in hearing-impaired listeners. However, the **majority of the explainable variance in the prediction dataset is driven by the hearing aid itself, not by the listener** — meaning that individualization, while measurable, sits beneath a much larger device-level signal.

## Why this matters for the hearing-aid field

- **A calibration finding for personalization claims.** Hearing-aid marketing often emphasizes "personalized AI." The Clarity-6 result is the cleanest public quantitative reminder that the device's own processing dominates the listener-specific variance in current evaluation datasets. Personalization is real and measurable, but the bar for it being worth the extra complexity should be informed by how large the device-level signal already is.
- **Towards "fit not the audiogram, but the model."** The framing extends the Saddler & McDermott 2024 task-optimized-DNN-as-hypothesis program to the impaired periphery. The deployment implication: a fitting algorithm of the future could be tuned against a simulated patient that was itself optimized to be a behavioral model of that specific wearer, with the audiogram as a warm start rather than the endpoint.
- **Clarity Workshop substrate.** This is the public substrate the Clarity Prediction Challenge community uses to benchmark intelligibility-prediction models. Anyone shipping a real intelligibility-prediction module should be on this leaderboard or explain why not.

## Cross-references

- Upstream: [[saddler-mcdermott-2024-nature-comms-temporal-coding]] — the normal-hearing task-optimized-DNN paper this extends to HI listeners.
- Saddler's VCCA 2026 pre-conference ML workshop: [[vcca2026-pre-conference-workshops-jun-19-2026]].
- Concept: [[../wiki/concepts/task-optimized-dnn-as-auditory-model]]; [[../wiki/concepts/differentiable-cochlear-models]].
- Entity: [[../wiki/entities/clarity-prediction-challenge]].

## Carry-Forward Flags
- Whether per-wearer individualization gains scale once datasets cover more listeners per device condition (vs the current device-dominated variance).
- Whether the jointly-optimized localization + recognition objective is the right multi-task setup, or whether a third task (e.g. effort / cognitive-load) further constrains the individualization.
