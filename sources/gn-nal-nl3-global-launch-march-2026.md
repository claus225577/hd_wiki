---
title: "GN Launches Next-Generation Fitting Software Featuring NAL-NL3 Integration"
date_published: 2026-03-11
date_ingested: 2026-05-12
url: https://www.resound.com/en/press/gn-launches-next-gen-fitting-software-for-better-patient-outcomes-with-worlds-first-with-nal-nl3
type: press-release
venue: GN / ReSound press
tags: [nal-nl3, prescription-formula, fitting-software, gn, resound, beltone, hearing-australia, audiology, computational-audiology]
---

# GN — World's First Fitting Platform with NAL-NL3 (Global Launch, March 2026)

## Summary

GN became the first hearing-aid manufacturer to ship a clinical fitting platform built on the new NAL-NL3 prescription formula, with a global software release on 11 March 2026. NAL-NL3 is the successor to NAL-NL2 (in clinical use since 2011) developed by Australia's National Acoustic Laboratories.

## Products Updated

- ReSound Smart Fit 2.3.1 (ReSound clinician software)
- Beltone Solus Max 2.3.1
- Hearing Australia Fitware 2.3.1

## What Changes vs NAL-NL2

- **NL2 foundation:** Perceptual models, predicted speech intelligibility, curated lab data.
- **NL3 foundation:** Large-scale clinical fitting datasets, real-world user feedback, newer computational methods. Per GN's own framing, the formula "leverages sophisticated AI insights and real-world user feedback."
- **Targets refined:** Especially for complex hearing-loss configurations (reverse-slope, cookie-bite, severe high-frequency losses) and for minimal/no measurable hearing loss.
- **Noise philosophy:** New explicit trade-off between intelligibility and listening comfort, rather than maximizing intelligibility at the cost of fatigue.

## Companion Tooling

- Enhanced AutoREM (Real-Ear Measurement) — automated verification that the hearing aid's actual SPL output at the ear matches the NL3 target curve, reducing the gap between prescribed and delivered fit.

## Why It Matters (Data-Science Framing)

- **Upstream of every downstream feature:** The prescription target is the gain curve every personalization layer, every DNN noise reducer, every "AI-driven" feature fine-tunes on top of. When the baseline target moves from a hand-tuned acoustic model to a population-derived statistical prior, the entire downstream stack inherits the shift.
- **Competitive divergence:** NL3, the legacy NL2, DSL v5, and OEM proprietary formulas (Phonak's APD, Oticon's VAC+, Starkey's e-STAT, Signia's SoundFit) now all start from different defaults. Whose population the prior was trained on becomes a competitive variable.
- **Closed-loop opportunity:** Once the baseline is data-derived, telemetry (datalogs, in-the-wild user adjustments, ecological outcome measures) can feed back into the next NL revision. The prescription itself becomes a moving target rather than a fixed reference curve.
- **Equity / fairness:** A data-derived prior is only as representative as its training distribution. This is a dataset-curation problem before it is a model-architecture problem — and one where the AI/fairness literature has obvious lessons for audiology.

## Companion Source

A separate concise summary already in the wiki: `sources/nal-nl3-fitting-protocol-2026.md` (April 2026 trade-press coverage of NL3 rollout philosophy, including Lansbergen et al. *Trends in Hearing* 4–8 kHz target-deviation finding). This source is the GN-specific commercial launch / global software release version.

## Methodology Paper

- The NAL-NL3 Fitting System, *International Journal of Audiology*, 2026 (online ahead of print) — DOI 10.1080/14992027.2026.2648713. Published behind paywall; methodology paper details the algorithmic and data foundation of NL3.

## Coverage

- Hearing Health & Technology Matters (March 2026): https://hearinghealthmatters.org/hearing-technologies/2026/resound-fitting-software-nl3/
- The Hearing Review (March 2026): https://hearingreview.com/hearing-products/hearing-aids/gn-launches-fitting-software-with-nal-nl3-prescription-formula
- Hearing Health & Technology Matters "What's Changing" explainer (April 2026): https://hearinghealthmatters.org/thisweek/2026/nl3-update-hearing-aid-fitting/

## Related Wiki Pages
- [[hearing-aid-prescription-formulas]] — New concept page covering the NAL / DSL / OEM landscape.
- [[gn-hearing-resound]] — GN as the launch vendor.
- [[ml-personalized-fitting]] — Personalization layered on top of prescription targets.
- [[closed-loop-data-flywheel]] — Telemetry-driven iteration on population priors.
