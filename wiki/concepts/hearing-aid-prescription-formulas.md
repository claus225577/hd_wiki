---
title: Hearing Aid Prescription Formulas (NAL, DSL, OEM)
type: concept
created: 2026-05-12
updated: 2026-05-12
sources: [gn-nal-nl3-global-launch-march-2026.md, nal-nl3-fitting-protocol-2026.md, ml-personalized-fitting-review-2024.md]
related: [ml-personalized-fitting.md, dnn-in-hearing-aids.md, closed-loop-data-flywheel.md, gn-hearing-resound.md, phonak.md, demant-oticon.md, starkey.md, wsa-sound-preference-program-april-2026.md, vcca-computational-audiology.md]
tags: [fitting, prescription, nal-nl2, nal-nl3, dsl-v5, gain-curve, audiology, fairness, computational-audiology]
---

# Hearing Aid Prescription Formulas

A **prescription formula** is the algorithm that converts an individual audiogram into a target gain curve — how much amplification to apply at each frequency for soft, medium, and loud input sounds. It is the upstream baseline that every other hearing-aid setting (compression, noise reduction, DNN enhancement, beamforming) is layered on top of.

## Core Function

For a given audiogram (hearing thresholds in dB HL across 250 Hz – 8 kHz), a prescription formula outputs:
- Target real-ear aided response (REAR) curves at three input levels — typically 50, 65, 80 dB SPL.
- Compression ratios and knee-points implied by the loudness model.
- Output limiting targets to prevent loudness discomfort.

These targets are then verified at the ear using **real-ear measurement (REM)** with a probe-mic system. Deviation from prescribed target is one of the few objective fitting-quality metrics.

## The Major Formulas

### Independent / Research-Derived

| Formula | Origin | Status |
|---------|--------|--------|
| **NAL-NL1** | NAL (Australia), 1999 | Superseded |
| **NAL-NL2** | NAL, 2011 | De facto default 2011–2026 |
| **NAL-NL3** | NAL, 2026 | Now rolling out (GN first to integrate) |
| **DSL v5.0** | University of Western Ontario, 2005 | Pediatric default; adult use varies |
| **DSL v5 Adult** | UWO | Used for severe-profound adult losses |

### OEM Proprietary

| Formula | Manufacturer | Notes |
|---------|--------------|-------|
| **Phonak APD / Adaptive Phonak Digital** | Phonak (Sonova) | Default in Phonak Target software |
| **Oticon VAC+** | Oticon (Demant) | Default in Genie 2 |
| **Starkey e-STAT** | Starkey | Iteratively refined since e-STAT 2.0 |
| **WSA SoundFit / Sound Preference** | WS Audiology | Layered with Sound Preference Tool (April 2026) for preference phenotyping |

## NAL-NL3 — The Data-Native Successor (2026)

The shift from NL2 to NL3 is the most consequential change to the field's default starting point in 15 years.

- **NL2 (2011):** Built on perceptual models, predicted speech intelligibility models, and curated lab datasets.
- **NL3 (2026):** Large-scale clinical fitting datasets, real-world user feedback, newer computational methods. GN's launch materials describe it as leveraging "sophisticated AI insights."

Key changes:
- Refined targets for complex hearing-loss configurations (reverse-slope, cookie-bite, severe high-frequency losses, minimal/no measurable loss).
- A new explicit philosophy for noise — trading intelligibility against listening comfort rather than maximizing intelligibility at the cost of fatigue.
- Backed by Lansbergen et al. (*Trends in Hearing* 2026) showing that NL2 deviations at 4–8 kHz have a small but reliable association with self-reported benefit — i.e., the high-frequency region matters more than NL2 implicitly assumed.

GN was the first to ship NL3 in clinical software (global launch 11 March 2026 in ReSound Smart Fit 2.3.1, Beltone Solus Max 2.3.1, Hearing Australia Fitware 2.3.1). The methodology paper appeared in *International Journal of Audiology* (2026, DOI 10.1080/14992027.2026.2648713).

## Why Prescription Formulas Are an AI/ML Story Now

When the baseline target was a hand-tuned acoustic-loudness model (NL2-era), the prescription was effectively a fixed reference. Every downstream personalization or DNN-driven feature added value relative to that fixed reference. When the baseline becomes a data-derived statistical prior (NL3-era), the entire stack changes:

1. **Manufacturer divergence as a competitive variable.** NL3, the legacy NL2, DSL v5, and OEM proprietaries now all start from different defaults — and the training distribution of each formula is no longer audiologically equivalent. Whose data the prior was learned on becomes a competitive moat.

2. **Closed-loop feedback opportunity.** Once the formula is population-derived, in-field telemetry (datalogs, user-initiated adjustments, ecological momentary assessment data, longitudinal outcome measures) can feed back into the next NL revision. The prescription becomes a moving target rather than a fixed reference. This is the same closed-loop pattern already deploying in [[ml-personalized-fitting]], but at the prior level rather than the per-user fine-tuning level.

3. **Outcome equity / fairness.** A data-derived prior is only as representative as its training distribution. Audiology datasets historically over-represent older, English-speaking, mild-to-moderate hearing-loss adults from high-income countries. NL3's clinical validity depends on whether its training distribution looks like the patient distribution — a dataset-curation problem before it is a model-architecture problem, and an obvious entry point for AI/fairness literature into clinical audiology.

4. **Verification still matters.** Even with a learned target, **real-ear measurement** remains the only way to verify that the actual SPL at the eardrum matches the prescribed target. GN's enhanced AutoREM tooling is the corresponding automation of the verification step.

## Relationship to Personalization

A prescription formula is the **prior**; per-user fitting is the **posterior**. In a hierarchical-model framing:

- The formula provides population-level targets given an audiogram.
- The audiologist's fitting adjustments (and in-app user adjustments) provide per-user updates conditioned on subjective response, REM verification, and outcome measures.
- ML personalization approaches ([[ml-personalized-fitting]]) sit between these two levels — using population data to nudge the prior, or per-user telemetry to nudge the posterior.

WSA's [[wsa-sound-preference-program-april-2026]] is a parallel move at a different layer: rather than re-deriving the prior, it captures structured preference phenotypes (natural vs enhanced) before fitting, providing a categorical conditioning variable on top of the formula.

## Open Questions

- Will Phonak / Oticon / Starkey / WSA migrate to NL3, or maintain proprietary formulas? (Commercial incentives push toward proprietary; clinical interoperability pushes toward NL3.)
- How will NL3 perform on the patient sub-populations its training data under-represents?
- Can NL3 be re-trained on national hearing-aid telemetry datasets (Hearing Australia, NHS, US VA) to localize the prior?
- Where does the NL3 vs NL2 boundary land in the courtroom of "best practice" — and what is the audiologist's obligation when fitting an existing NL2-fitted patient with a new device?

## Related Pages
- [[ml-personalized-fitting]] — Personalization layer that sits on top of the prescription target.
- [[dnn-in-hearing-aids]] — Downstream DNN processing inherits the prescription baseline.
- [[closed-loop-data-flywheel]] — Telemetry-driven iteration applies at the prior level too.
- [[wsa-sound-preference-program-april-2026]] — Parallel personalization at the preference-phenotype layer.
- [[gn-hearing-resound]] — First OEM to ship NL3.
- [[vcca-computational-audiology]] — Major venue for computational-fitting research.

## Sources
- [GN NAL-NL3 Global Launch (March 2026)](../sources/gn-nal-nl3-global-launch-march-2026.md)
- [NAL-NL3 Fitting Protocol (trade-press summary, April 2026)](../sources/nal-nl3-fitting-protocol-2026.md)
- [ML-Personalized Fitting Review (2024)](../sources/ml-personalized-fitting-review-2024.md)
