---
title: Digital Phenotyping for Cognitive Decline
type: concept
created: 2026-05-07
updated: 2026-05-07
sources: [jmir-ai-wearables-cognitive-impairment-2026.md, achieve-trial-cognitive-hearing-2025.md, apple-hearing-study-results-may-2026.md]
related: [hearing-loss-dementia-link.md, longitudinal-hearing-phenotyping.md, large-sensor-models.md, on-device-ml-hearing-aids.md, closed-loop-data-flywheel.md]
tags: [digital-phenotyping, dementia, cognitive-decline, wearables, preclinical, ai-prediction, hearing-aids, telemetry]
---

# Digital Phenotyping for Cognitive Decline

A measurement framework in which continuous, passive signals from wearables — gait, sleep, heart-rate variability, behavioral routines, and (in this wiki's framing) ear-based acoustic and conversational data — are aggregated and interpreted by AI as preclinical biomarkers of cognitive impairment and dementia.

## The Evidence Base

The Feb 2026 [[../sources/jmir-ai-wearables-cognitive-impairment-2026]] systematic review synthesized 49 studies pairing wearable devices with AI for early detection of cognitive impairment. Its central methodological argument:

> The field is shifting from descriptive associations toward a **digital phenotyping framework** that evaluates AI-driven prediction in the preclinical window.

This complements the interventional evidence in [[hearing-loss-dementia-link]] — the ACHIEVE trial showed hearing aids slow cognitive decline by 48% in higher-risk older adults — by providing the measurement substrate for population-scale early identification of who needs the intervention in the first place.

## Why Hearing Aids Are an Underused Substrate

Most digital phenotyping research has used wrist-based wearables. Hearing aids have structural advantages that the literature is only beginning to exploit:

- **Wear duration:** Hearing aid users wear devices ~10–14 hours/day, every day; wrist-wearable adherence in older adult cohorts is typically lower and less consistent.
- **Population coverage:** Hearing aid users skew toward the population most at risk for dementia (older adults), making the substrate inherently well-targeted.
- **Already-captured signals:** Modern hearing aids log acoustic environment classification, streaming hours, conversation/speech detection, program changes — all currently used for fitting and warranty data, not phenotyping.
- **Sensor expansion in 2026 platforms:** PPG (heart rate, HRV), accelerometers (gait, falls), and temperature are being added to flagship devices. See [[../entities/starkey]] and [[../entities/apple-hearing-features]].
- **Conversational uptake as a behavioral signal:** Time-in-conversation and listening engagement patterns are unique signals not available from wrist devices.

## Feature Set: What a Hearing-Aid-Native Digital Phenotype Could Look Like

| Signal | Source | Cognitive relevance |
|---|---|---|
| Gait variability / walking speed | Onboard accelerometer | Strong literature link to MCI / dementia (Apple Hearing Study mobility sub-analysis confirmed) |
| HRV trends | Onboard PPG | Autonomic dysregulation is an early dementia marker |
| Time-in-conversation | Acoustic classifier + own-voice detection | Social withdrawal precedes diagnosis by years |
| Acoustic environment diversity | Scene classifier | Routine deviation = behavioral marker |
| Listening effort proxies | Real-time SNR + program changes | Cognitive load in real-world listening |
| Sleep continuity | Inferred from wear / motion | Sleep disturbance precedes cognitive decline |
| Speech-in-noise decline rate | Periodic ecological tests | Direct hearing trajectory |

A model fusing even a subset of these is qualitatively different from any single-modality wrist-based digital phenotype.

## Methodological Challenges (per JMIR review)

- Heterogeneous data formats and sampling rates across devices
- Small sample sizes; few studies with multi-year longitudinal follow-up
- Lack of standardized AI evaluation protocols (no shared benchmark)
- Cohort bias — most studies recruit from clinic populations, not general aging populations
- Privacy and governance: continuous behavioral monitoring creates a regulatory surface that current FDA AI/ML SaMD guidance does not fully cover

## Connection to Industry Strategy

If digital phenotyping for cognitive decline becomes a clinical category, hearing aid manufacturers face a strategic choice:
1. **Treat the signal as a byproduct** — license telemetry to digital health partners (Apple, Mayo Clinic, dementia drug developers).
2. **Build the feature in-house** — make dementia-risk monitoring a default fitting outcome, validated under SaMD pathways.
3. **Open the substrate** — publish hearing-aid telemetry standards so academic and clinical groups can build the models.

The [[closed-loop-data-flywheel]] pattern argues for option 2 if the manufacturer also has retail patient access (e.g., post-Amplifon-GN merger).

## Related Pages
- [[hearing-loss-dementia-link]] — Epidemiological and RCT evidence linking hearing loss and dementia
- [[longitudinal-hearing-phenotyping]] — Outcome-measurement framework that this concept extends to cognitive endpoints
- [[large-sensor-models]] — Foundation-model architectures that could fuse heterogeneous wearable streams
- [[on-device-ml-hearing-aids]] — Privacy-preserving compute substrate for behavioral signal extraction
- [[closed-loop-data-flywheel]] — Strategic framing of telemetry as feedstock for product improvement

## Sources
- [JMIR systematic review (Feb 2026, 49 studies)](../../sources/jmir-ai-wearables-cognitive-impairment-2026.md) — The defining recent synthesis of the field; basis for this page
- [ACHIEVE trial](../../sources/achieve-trial-cognitive-hearing-2025.md) — Interventional anchor: hearing aids slow cognitive decline 48% in at-risk adults
- [Apple Hearing Study (May 2026)](../../sources/apple-hearing-study-results-may-2026.md) — Confirms hearing-loss/walking-speed link at population scale; n=57k mobility sub-analysis
