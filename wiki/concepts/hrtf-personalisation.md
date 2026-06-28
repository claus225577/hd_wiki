---
title: HRTF Personalisation
type: concept
created: 2026-06-28
updated: 2026-06-28
sources: [arxiv-2606-24367-bayesian-localisation-jun-2026.md]
related: [binaural-sound-localisation-models.md, predictive-pediatric-earmolds.md, on-device-ml-hearing-aids.md, hearing-aid-prescription-formulas.md]
tags: [hrtf, personalisation, binaural, spatial-audio, pinna, anthropometry, hearing-aid-fitting]
---

# HRTF Personalisation

The pipeline that turns a generic head-related transfer function (HRTF) into one matched to a specific listener's anatomy. For binaural hearing aids it is the spatial analogue of audiogram-based fitting: the device cannot render correct directional cues without knowing how that listener's outer ear shapes incoming sound.

## The Old Frame: Algorithm Choice

For thirty years the binaural-HA R&D debate has framed personalisation as an **interpolation problem**: given a sparse set of HRTF measurements, which algorithm best estimates the rest?

The candidate algorithms:
- Linear, spherical-harmonic, Gaussian-process, nearest-neighbour, magnitude-LSF, barycentric.
- More recent: neural-field reconstruction, NeRF-style implicit HRTF representation, conditional diffusion.

Every team had a favourite. The literature is large.

## The New Frame: Measurement Quality

Barumerli et al. (arXiv:2606.24367, Jun 2026) compared four HRTF interpolation methods inside a Bayesian ideal-observer of localisation. Headline:

> **Full-sphere spatial coverage** and **high-frequency spectral fidelity** dominate template quality. The interpolation algorithm is secondary.

This re-frames personalisation as a **data-acquisition problem**.

## Practical Implications for HA Pipelines

If algorithm choice is second-order, the budget moves to:

1. **Full-sphere coverage.** The frontal-arc + symmetry shortcut that every HA fitting suite uses is now under audit. Rear-hemisphere and elevation matter.
2. **High-frequency spectral fidelity.** Anti-aliasing on fast HRTF rigs has been quietly low-pass-filtering the very cues monaural-spectrum localisation depends on.
3. **Cheap personalisation capture.** The candidates for "good-enough personalised HRTF capture without a special lab":
   - **Phone-photogrammetry pinna meshes** + parametric HRTF synthesis from the mesh.
   - **In-situ blocked-meatus probe** measurements during a fitting visit.
   - **Sparse-rig + neural-field reconstruction** — measure a few directions, reconstruct the rest.
4. **Open-source Python benchmarking.** Anyone can now score their measurement pipeline on the same ideal-observer likelihood.

## Coupling to Audiogram-Based Fitting

A natural next step is a joint personalisation model: a single optimisation that fits both the wearer's audiogram-driven gain prescription and their HRTF template, on the same likelihood scale. The DAL framework (`differentiable-cochlear-models.md`) is the cochlear half of that joint problem; the Bayesian localisation model is the spatial half.

## Related Pages
- [[binaural-sound-localisation-models]] — the evaluation framework that validates this concept.
- [[predictive-pediatric-earmolds]] — the pinna-mesh capture pipeline overlaps.
- [[on-device-ml-hearing-aids]] — once HRTF is personalised, the spatial DSP that uses it has to run on-device.
- [[hearing-aid-prescription-formulas]] — analogous fitting problem, different perceptual dimension.

## Sources
- [Barumerli et al., "Statistical validation and full-sphere extension of a Bayesian model for human static sound localisation", arXiv:2606.24367 (Jun 2026)](../sources/arxiv-2606-24367-bayesian-localisation-jun-2026.md) — the measurement-vs-algorithm verdict.
