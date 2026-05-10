---
title: Longitudinal Hearing Phenotyping
type: concept
created: 2026-04-26
updated: 2026-05-09
sources: [harvard-mass-eye-ear-gene-therapy-otof-nature-2026.md, otarmeni-fda-gene-therapy-approval-april-2026.md, apple-hearing-study-results-may-2026.md, hearing-aid-cortical-reorganization-meg-frontiers-2026.md, pediatric-softband-bcd-database-frontiers-may-2026.md]
related: [gene-therapy-hearing.md, cochlear-implant-ai.md, on-device-ml-hearing-aids.md, closed-loop-data-flywheel.md, automated-audiometry.md, large-sensor-models.md, vcca-computational-audiology.md, subjective-objective-hearing-gap.md, hearing-loss-dementia-link.md, digital-phenotyping-cognitive-decline.md, cortical-reorganization-hearing-aids.md]
tags: [phenotyping, longitudinal, outcome-measurement, ecological-momentary-assessment, gene-therapy, ml-monitoring, real-world-evidence, neuroplasticity, telemetry, candidacy-expansion]
---

# Longitudinal Hearing Phenotyping

A measurement framework for tracking an individual's hearing function continuously and ecologically over months to years — across modalities (gene therapy, cochlear implants, hearing aids), contexts (clinic, home, social), and signals (audiograms, speech-in-noise, listening behavior, real-world device telemetry).

The concept gained urgency in April 2026 with the Nature paper reporting 2.5-year durability of OTOF gene therapy (90% of 42 participants maintained restored hearing) — see [[../sources/harvard-mass-eye-ear-gene-therapy-otof-nature-2026]]. A clinic audiogram every six months is too coarse to characterize the trajectory of a one-shot biological intervention or to detect drift in a software-defined hearing aid over a decade.

## Why a New Phenotype Layer Is Needed

### Limitations of Current Outcome Measurement
- **Audiogram in clinic:** Single timepoint, unrepresentative acoustic environment
- **Self-report (questionnaires):** Sparse, biased, low-resolution
- **Speech-in-noise tests in clinic (e.g., HINT, QuickSIN):** Same single-timepoint problem
- **Existing device telemetry:** Streaming hours, program use — but not interpreted as a phenotype

### The Multi-Modality Problem
By 2026, hearing care had become a multi-modality field:
- **Gene therapy** for genetic targets (e.g., OTOF — see [[gene-therapy-hearing]])
- **Cochlear implants** for severe-to-profound loss — see [[cochlear-implant-ai]]
- **Hearing aids** for mild-to-severe loss
- **Hybrid devices and bimodal fittings**

Each modality currently has its own outcome metrics. A unified longitudinal phenotype that crosses all of them is the missing measurement layer.

## What a Longitudinal Phenotype Should Capture

### Core Signals
- **Continuous speech-in-noise performance** captured in real-world acoustic contexts
- **Listening effort proxies** — pupillometry, EEG, behavioral
- **Time-to-recognition** curves across listening conditions
- **Real-world listening behavior** — context entry/exit, duration in noise, social engagement
- **Adaptive testing** delivered through the device and paired smartphone
- **Adherence** to wear time and rehabilitation protocols
- **Cortical efficiency proxies** — telemetry features that approximate the MEG-measurable cortical reorganization shown to occur within 12 weeks of HA wear (see [[cortical-reorganization-hearing-aids]])

### Drawn from Existing Telemetry
Modern hearing aids and CIs already stream:
- Acoustic scene labels
- Volume / program changes
- Wear time and battery cycling
- Bluetooth streaming patterns
- Auracast reception events

The data exists. The phenotype layer that interprets it does not yet.

## Connections to Existing Frameworks

### Closed-Loop Data Flywheel
The longitudinal phenotype is the measurement substrate of the closed-loop data flywheel — see [[closed-loop-data-flywheel]]. Without it, the flywheel cannot converge on the right outcomes.

### Large Sensor Models
Foundation models for wearable sensor data — see [[large-sensor-models]] — provide the unsupervised learning substrate that could digest device telemetry into latent representations of hearing function over time.

### Ecological Momentary Assessment (EMA)
A pre-existing public-health methodology now being instrumented through wearables. Hearing-specific EMA, delivered through the device, is one path to the longitudinal phenotype.

## Population-Scale Exemplar: Apple Hearing Study (May 2026)

The Apple Hearing Study released results on 1 May 2026 (run with U-M School of Public Health) that demonstrate the framework working at population scale through consumer hardware:

- **n=160,000** consented U.S. participants — the largest hearing cohort assembled to date
- **57,183** participants in the mobility sub-analysis — worse hearing correlated with slower walking speed, strongest in adults 60+
- **16%** of ~85,000 "clinically normal" participants self-rated their hearing as fair/poor — quantifying the perception–measurement gap (see [[subjective-objective-hearing-gap]])
- **Continuous 4PTA monitoring** through AirPods Hearing Test as an instrument for users to track drift outside the clinic

This is the first time the longitudinal phenotype has been operationalized at this scale in a free-living population — and it was generated by a consumer-electronics company, not a hearing aid manufacturer or academic clinical network. The competitive implication: traditional manufacturers' fitting telemetry datasets are dwarfed by Apple's free-living hearing + activity + biometric cohort.

See [[../sources/apple-hearing-study-results-may-2026]] and [[apple-hearing-features]].

## Pediatric BCD Exemplar — Telemetry Becomes the Warrant (May 2026)

A second exemplar — quieter than Apple but methodologically purer — was published in Frontiers in Audiology and Otology on 8 May 2026: a retrospective review of **5,490 children** fitted with softband bone-conduction devices over 1998–2025 within a publicly-funded pediatric audiology system.

The headline numbers (PEACH 46% unaided → 82% aided, 74% regular daily use) matter less than the candidacy finding: **88% of fittings were not the textbook microtia/atresia population.** OME, craniofacial anomalies, cleft palate, and unknown etiologies dominated, and outcomes within these expanded groups were comparable to the historical indication.

Candidacy expansion happened in the data before it happened in the guideline. The dataset was not produced by an RCT. It was produced by routine clinical care that captured outcomes consistently for nearly three decades. That is exactly the property the longitudinal phenotype framework is meant to formalize for adult hearing aids.

Implications:

- **Routine clinical telemetry, captured uniformly, is sufficient warrant for guideline change** — the pediatric BCD literature is now the proof of concept.
- **The hearing aid analogue does not yet exist at this scale.** Most national hearing aid systems do not capture wear time, satisfaction, or acoustic-context history as structured longitudinal fields.
- **Manufacturers and clinics that begin treating routine fitting and wear-time data as a strategic asset stand to control the next candidacy expansion** — and the regulatory / reimbursement moat that comes with it.

See [[../sources/pediatric-softband-bcd-database-frontiers-may-2026]].

## Use Cases

### 1. Gene Therapy Durability Monitoring
- Detect slow drift in restored hearing over years
- Identify responders vs. partial responders for re-treatment or alternative therapy
- Quantify age-of-treatment effects beyond pediatric-vs-adult dichotomy

### 2. CI / Hearing Aid Software Update Validation
- Detect whether a firmware or model update degrades real-world function before adverse events accumulate — see [[software-defined-medical-implants]]
- Provide surveillance signal for FDA TPLC / PCCP frameworks

### 3. Clinical Trial Endpoint Modernization
- Replace single-timepoint trial endpoints with trajectory-based ones
- Reduce sample size requirements through within-subject longitudinal contrasts

### 4. Personalization Targets
- Define what "good hearing" looks like for an individual user across contexts
- Inform [[on-device-ml-hearing-aids]] adaptation models

## Challenges

- **Consent and privacy** — continuous behavioral telemetry from a medical device demands strong governance
- **Cross-device standardization** — manufacturers each have proprietary telemetry schemas
- **Confounding** — listening behavior is shaped by life events, not only hearing function
- **Validation** — without ground truth, phenotype validity must be established statistically across cohorts

## Open Research Directions

- Self-supervised pretraining on cross-manufacturer telemetry corpora — see [[large-sensor-models]]
- Federated learning for multi-site phenotype models without centralizing PHI
- VCCA / computational audiology venues are natural homes for this research — see [[vcca-computational-audiology]]
- Standardization efforts (HIMSA-style) for cross-manufacturer telemetry schemas

## Related Pages
- [[gene-therapy-hearing]] — Primary motivating use case (OTOF durability)
- [[cochlear-implant-ai]] — CIs as a key telemetry source
- [[on-device-ml-hearing-aids]] — Hearing aids as a key telemetry source
- [[closed-loop-data-flywheel]] — Phenotype is the measurement substrate of the flywheel
- [[automated-audiometry]] — Adaptive testing component
- [[large-sensor-models]] — Foundation-model substrate for telemetry
- [[vcca-computational-audiology]] — Research community
- [[software-defined-medical-implants]] — Phenotype required to safely deploy model updates

## Sources
- [Harvard/Mass Eye and Ear OTOF Nature Study](../sources/harvard-mass-eye-ear-gene-therapy-otof-nature-2026.md) — 2.5-year durability data motivating the longitudinal phenotype need
- [FDA Approves Otarmeni](../sources/otarmeni-fda-gene-therapy-approval-april-2026.md) — 24-week regulatory endpoint as contrast to multi-year real-world phenotype
- [Apple Hearing Study — May 2026 Results (n=160,000)](../sources/apple-hearing-study-results-may-2026.md) — Population-scale exemplar of the framework operationalized through consumer hardware; mobility and perception findings
- [Becker et al., MEG Cortical Reorganization, Apr 2026](../sources/hearing-aid-cortical-reorganization-meg-frontiers-2026.md) — Adds cortical efficiency as a sub-3-month signal motivating telemetry-based proxies in the phenotype layer
- [Pediatric Softband BCD Database, Frontiers, May 8 2026](../sources/pediatric-softband-bcd-database-frontiers-may-2026.md) — n=5,490 28-year database showing routine clinical telemetry as warrant for candidacy expansion beyond historical indications
