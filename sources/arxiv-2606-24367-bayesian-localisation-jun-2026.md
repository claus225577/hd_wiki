---
title: "Statistical validation and full-sphere extension of a Bayesian model for human static sound localisation"
type: source
source_type: arxiv-preprint
date_published: 2026-06-23
date_ingested: 2026-06-28
authors: [Roberto Barumerli, Fabian Brinkmann, Emanuele Zanoni, Anton Hoyer, Lorenzo Picinali, Michele Geronazzo]
identifier: arXiv:2606.24367
url: https://arxiv.org/abs/2606.24367
venue: arXiv eess.AS
tags: [binaural, hrtf, sound-localisation, bayesian-ideal-observer, hearing-aid-spatialisation, full-sphere, open-source-python]
---

# Statistical validation and full-sphere extension of a Bayesian model for human static sound localisation

## Bibliographic
- **Authors:** Roberto Barumerli, Fabian Brinkmann, Emanuele Zanoni, Anton Hoyer, Lorenzo Picinali, Michele Geronazzo
- **Affiliations:** University of Verona (Barumerli, Zanoni, Geronazzo); TU Berlin (Brinkmann, Hoyer); Imperial College London (Picinali)
- **arXiv ID:** 2606.24367 (eess.AS)
- **Submitted:** 23 Jun 2026
- **URL:** https://arxiv.org/abs/2606.24367
- **Code:** open-source Python implementation released alongside the paper.

## Headline Claim
A rigorously validated Bayesian ideal-observer model of static sound localisation, extended to the full sphere; the dominant driver of HRTF "template quality" is **full-sphere spatial coverage and high-frequency spectral fidelity**, while the **interpolation algorithm is secondary**.

## Methodology
- **Model:** Bayesian ideal-observer formalism for the static-source localisation task, with an explicit likelihood function over the cue space (ITD/ILD + monaural spectral cues).
- **Validation 1 — parameter recovery:** simulated datasets generated from known sensorimotor + spectral parameters; the inference procedure recovers them within expected precision.
- **Validation 2 — behavioural fit:** model fitted to localisation responses from **33 listeners**; identifies individual sensorimotor and spectral-template parameters.
- **Full-sphere extension:** the standard frontal-hemisphere validation is generalised to the entire sphere around the head, including rear and elevated sources.
- **HRTF template study:** four common HRTF interpolation methods compared by their effect on model template quality.

## Reported Findings
- The explicit likelihood enables principled parameter recovery — the model is statistically identifiable from realistic listener data.
- **Full-sphere spatial coverage + high-frequency spectral fidelity dominate** the determinants of HRTF template quality.
- **Interpolation-algorithm choice is a second-order effect.**
- Open-source Python implementation lowers the barrier for the field to adopt principled, likelihood-based localisation evaluation.

## Why This Matters for Hearing-Aid R&D
1. **The HA binaural-spatialisation debate has been about the wrong axis.** Linear vs spherical-harmonic vs Gaussian-process interpolation is a topic that has occupied 30 years of binaural HA engineering; this paper's verdict is that the gains there are small compared to the gains from measuring the back of the sphere properly.
2. **Personalised HRTFs become a data-acquisition problem, not a math problem.** Phone-photogrammetry pinna meshes, blocked-meatus in-situ probes, sparse-rig + neural-field reconstruction — the route to personalised binaural HAs runs through cheaper full-sphere capture.
3. **Spatial fitting protocols now have a published likelihood model that can score them.** Existing HA fitting suites quietly assume frontal-arc + symmetry. That assumption can now be quantitatively audited.
4. **Open-source Python lowers the moat.** A small startup can now run the same evaluation as a top-tier auditory lab; the IP value of "we have a localisation model" decreases.

## Limitations / Open Questions
- Static-source paradigm only; dynamic / moving sources and head movements remain outside the validated scope.
- 33 listeners — solid for parameter recovery but small relative to the inter-subject HRTF variability the field cares about.
- Acoustic-manikin vs individual-pinna template comparison not yet integrated.
- Does not address the joint problem of localisation + speech intelligibility in noise — only localisation accuracy.
- Implications for hearing-impaired listeners (compromised cues, asymmetric loss) are extrapolated from a normal-hearing-listener sample.

## Cross-References Inside This Wiki
- `wiki/concepts/binaural-sound-localisation-models.md` (new) — primary concept.
- `wiki/concepts/hrtf-personalisation.md` (new) — measurement vs algorithm trade-off framed here.
- `wiki/concepts/subjective-objective-hearing-gap.md` — likelihood-based ideal-observer is the cleanest bridge.
- `wiki/concepts/non-intrusive-intelligibility-prediction.md` — same family of "score a processed signal vs a normative model."
- `wiki/concepts/predictive-pediatric-earmolds.md` — pinna-photogrammetry pipeline relevant.
- `wiki/syntheses/hearing-aid-ai-stack-2026.md` — spatial stage of the stack now has a published ideal-observer benchmark.
