---
title: Binaural Sound Localisation Models
type: concept
created: 2026-06-28
updated: 2026-06-28
sources: [arxiv-2606-24367-bayesian-localisation-jun-2026.md]
related: [hrtf-personalisation.md, subjective-objective-hearing-gap.md, non-intrusive-intelligibility-prediction.md, on-device-ml-hearing-aids.md]
tags: [binaural, sound-localisation, bayesian, ideal-observer, hrtf, hearing-aid-spatialisation]
---

# Binaural Sound Localisation Models

Computational models that predict how a (normal-hearing or hearing-impaired) listener localises a sound source given the binaural acoustic signal. These models are the principled-evaluation analogue of HASPI for spatial perception: instead of asking "how intelligible did this signal become after HA processing?" they ask "where will a listener think the source is after HA processing?"

## Why Hearing Aids Care

Localisation is a wearer outcome that survey instruments (SSQ, APHAB) have measured for decades, but the field has historically lacked a per-condition objective model that maps an HA-processed binaural recording to a predicted localisation response. That gap is what binaural ideal-observer models fill.

Use cases inside the HA stack:
- Score a beamformer's localisation cost (most beamformers degrade ITDs in exchange for SNR).
- Compare HRTF personalisation pipelines on a likelihood scale rather than a perceptual-rating proxy.
- Audit binaural fitting suites' "frontal arc + symmetry" shortcut.
- Quantitatively assess the rear-hemisphere cost of any signal-processing change.

## Bayesian Ideal-Observer Family

The state-of-the-art family treats the listener as a Bayesian observer with:
- A prior over source positions (often uniform over the validated sphere).
- A likelihood that the observed cue values (ITD, ILD, monaural spectrum) came from a hypothesised source position, given the listener's individual HRTF template.
- A read-out stage with sensorimotor noise (response-mapping precision, motor noise on head-pointing).

The free parameters split into **sensorimotor** (precision, lapse rate, response noise) and **spectral-template** (frequency-band weighting on the monaural cues). Both can be fitted per listener.

Barumerli et al. (arXiv:2606.24367, 23 Jun 2026) provides the first **statistically validated** version of this approach, with parameter recovery on simulated data, behavioural fits on 33 listeners, and an extension from the frontal hemisphere to the **full sphere**. An open-source Python implementation accompanies the paper.

## Key Finding for HRTF Design

Across four HRTF interpolation methods, **template quality is dominated by**:

1. **Full-sphere spatial coverage** of the measurement grid.
2. **High-frequency spectral fidelity** of the captured HRTFs.

The interpolation algorithm choice is a second-order effect.

For HA spatial pipelines this redirects the engineering budget from interpolation R&D to measurement R&D.

## Implications for HA Personalisation

- Personalised HRTFs are a **data-acquisition problem**, not an algorithm-selection problem.
- Photogrammetric pinna meshes, sparse-rig blocked-meatus probes, and neural-field reconstruction of full-sphere HRTFs all become more important than picking the interpolator.
- Open-source Python implementations of the Bayesian model mean any team can benchmark their measurement pipeline on the same ideal-observer scale.

## Related Pages
- [[hrtf-personalisation]] — the measurement-vs-algorithm debate that this concept settles in favour of measurement.
- [[subjective-objective-hearing-gap]] — likelihood-based ideal-observer is the principled bridge.
- [[non-intrusive-intelligibility-prediction]] — same evaluation philosophy, different perceptual dimension.
- [[on-device-ml-hearing-aids]] — model is currently a fitting-software / R&D tool, not on-device.

## Sources
- [Barumerli et al., "Statistical validation and full-sphere extension of a Bayesian model for human static sound localisation", arXiv:2606.24367 (Jun 2026)](../sources/arxiv-2606-24367-bayesian-localisation-jun-2026.md) — primary source establishing the validated ideal-observer.
