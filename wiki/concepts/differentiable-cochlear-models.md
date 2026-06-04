---
title: Differentiable Cochlear Models
type: concept
created: 2026-06-04
updated: 2026-06-04
sources: [dal-differentiable-auditory-loop-google-june-2026.md]
related: [brain-aligned-speech-foundation-models.md, communication-accessibility-metric.md, on-device-ml-hearing-aids.md, ../entities/google-research.md, ../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md]
tags: [differentiable-cochlea, carfac, jax, perceptual-loss, gradient-based-fitting, end-to-end-personalization]
---

# Differentiable Cochlear Models

A differentiable cochlear model is an auditory-periphery simulation (cochlear mechanics → inner-hair-cell → auditory-nerve response) implemented in an autodiff framework (JAX, PyTorch) such that gradients can flow through it. When placed inside a training loop, it lets a downstream signal-processing network be optimized against losses defined in the cochlear / auditory-nerve representation rather than in the signal domain.

## Why it matters

For decades, hearing-aid processing has been optimized against signal-domain surrogates (PESQ, STOI, HASPI). Those metrics are convenient because they are differentiable functions of the audio waveform, but they only approximate what reaches the auditory cortex. A differentiable cochlea collapses that approximation: the loss can be the mismatch between a normal-hearing cochlea's output and the per-wearer impaired cochlea's output, evaluated as the network trains.

This reframes hearing-aid fitting as a per-wearer optimization in perceptual space, rather than a population-derived prescription in signal space.

## Key implementations

- **CARFAC** (Cascade of Asymmetric Resonators with Fast-Acting Compression) — Richard F. Lyon, Google. The most widely cited differentiable cochlear model. Open-source. CARFAC v2 paper: arXiv:2404.17490. CARFAC-JAX makes the model differentiable and runs on GPU/TPU. Outer-hair-cell (OHC) health parameters allow per-wearer impairment fitting.
- **Differentiable hearing-loss models** — earlier work by Tu et al. (arXiv:2106.04639, 2021) proposed differentiable hearing-loss functions for hearing-aid fitting. CARFAC + DAL goes further by including the cochlear mechanics, not only the audibility curve.

## End-to-end frameworks

- **Differentiable Auditory Loop (DAL)** — Ballesta Rosen et al., Google Research Australia + Macquarie, arXiv:2606.04103 (4 Jun 2026). First open-source end-to-end hearing-aid framework where the loss function operates on CARFAC neural activity patterns (NAPs) and stabilized auditory images (SAIs). A SEANet UNet learns by gradient descent to push the impaired cochlea's output toward a normal-hearing reference.

## Loss-function primitives

- **Neural Activity Pattern (NAP)** — Auditory nerve firing pattern across cochlear place; output of the inner-hair-cell stage of CARFAC.
- **Stabilized Auditory Image (SAI)** — 2D phase-insensitive temporal-structure representation derived from NAP; captures pitch and timbre patterns the brain is sensitive to.

## Implications for the field

- The fitting target stops being a prescription (NAL-NL3, DSL v5, manufacturer-specific defaults) and becomes a per-wearer cost function.
- Population priors don't disappear — they become warm starts for a personal optimization.
- The differentiable perceptual model becomes a strategic asset: whoever controls the loss-function substrate effectively controls what "personalized hearing" optimizes toward.
- Adjacent to the brain-aligned-loss / FUEL / communication-accessibility argument: differentiable cochlea provides the tractable gradient bridge.

## Open questions

- How well do CARFAC-derived perceptual losses transfer to subjective wearer preference?
- Can per-wearer cochlear-parameter fitting be done from passive in-situ telemetry, or does it require a clinical session?
- Regulatory framing: if every fitting is a training run, what does a predetermined change control plan look like?
- Will OEMs build proprietary differentiable cochlear models or fork CARFAC?

## Related Pages
- [[brain-aligned-speech-foundation-models]] — the receive-side analog: foundation models implicitly model the brain; differentiable cochleas explicitly model the periphery.
- [[communication-accessibility-metric]] — FUEL argument calls for new metrics; differentiable cochlea is one viable substrate.
- [[on-device-ml-hearing-aids]] — DAL is currently training-side; deployment to chip is the next-step gap.
- [[../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026]] — the May 2026 papers naming evaluation cracks; perceptual-domain loss is one alternative.
- [[../entities/google-research]] — institutional steward of CARFAC and DAL.

## Sources
- [DAL paper (arXiv 2606.04103, Jun 2026)](../../sources/dal-differentiable-auditory-loop-google-june-2026.md) — first open-source end-to-end differentiable-cochlea hearing-aid framework.
