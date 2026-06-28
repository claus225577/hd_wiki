---
title: Differentiable MVDR Beamforming (Learned Covariance + Learned WNG)
type: concept
created: 2026-06-26
updated: 2026-06-26
sources:
  - deng-pei-ma-joint-mvdr-wng-arxiv-2606-24137-jun-2026.md
related:
  - dnn-architectures-hearing-aids.md
  - dnn-in-hearing-aids.md
  - differentiable-dsp.md
  - joint-se-wdrc-end-to-end.md
  - on-device-ml-hearing-aids.md
  - speech-enhancement-neural-networks.md
  - fxlms-adaptive-filtering.md
  - ../syntheses/on-chip-hearing-ai-levers-june-2026.md
  - ../syntheses/hearing-aid-ai-stack-2026.md
tags: [mvdr, beamforming, white-noise-gain, diagonal-loading, differentiable-dsp, microphone-array, spatial-processing, hearing-aid-spatial-stage, interspeech-2026]
---

# Differentiable MVDR Beamforming (Learned Covariance + Learned WNG)

## Definition
A class of beamforming architectures in which the **noise spatial covariance matrix estimate** and the **regularisation strength** (White Noise Gain threshold or diagonal-loading constant) are *both* parameterised by a neural network, and the MVDR / robust-MVDR closed-form solution is implemented as a **differentiable layer** so that gradients flow end-to-end from a downstream quality / intelligibility loss back through the beamformer.

This is distinct from the prior generation of "DNN mask → classical beamformer → classical post-filter" pipelines, in which only the mask was learned and the spatial estimator + regulariser were hand-tuned.

## The Robust-MVDR Stability Problem
The Minimum Variance Distortionless Response beamformer minimises output power subject to a unit-response constraint on the look direction. Closed form:

```
w = (Φ_nn^{-1} a) / (a^H Φ_nn^{-1} a)
```

It is famously fragile when:
1. The noise covariance matrix Φ_nn is poorly estimated or rank-deficient (insufficient noise frames; non-stationary noise).
2. The steering vector a is mismatched (head movement; microphone mis-calibration over the hearing-aid lifetime).

The classical fix is **diagonal loading** (Cox 1987): replace Φ_nn with Φ_nn + ε·I, where ε is a regularisation constant. The dual formulation (Doclo / Gannot lineage) constrains the **White Noise Gain (WNG)** — the ratio of array output noise to microphone self-noise — to stay above a threshold so the beamformer doesn't degenerate into a self-noise amplifier.

For 30+ years in hearing-aid signal processing, ε and the WNG threshold have been **manually tuned per program** (Restaurant, Outdoors, Car, etc.) by DSP engineers who knew which fitting room would complain on Monday morning.

## The Joint-Learning Recipe (Deng et al., arXiv:2606.24137, Jun 2026)
The first published differentiable robust-MVDR that learns both estimate and regulariser jointly:

1. **One neural network** consumes the multi-channel mic signal and predicts:
   - A **time-frequency noise mask** that masks frames / bins to estimate Φ_nn.
   - A **frequency-dependent WNG threshold per frame** — the regularisation strength that decides diagonal loading.
2. **Differentiable robust-MVDR layer** computes the beamforming weights from those two predictions and applies them.
3. **End-to-end loss** (speech-quality / intelligibility) trains the network through the layer.

Reported result: consistent quality and intelligibility gains over fixed-WNG MVDR baselines under unknown / time-varying acoustic conditions — the exact regime where fixed thresholds were always a compromise.

## Why This Matters Specifically for Hearing Aids

### 1. Microphone arrays are tiny and self-noise-dominated
BTE / RIC arrays sit at 8–14 mm spacing with miniature MEMS mics. Self-noise is structurally high; the WNG constraint is what keeps the beamformer from amplifying it. A *learned*, frequency-dependent threshold can be aggressive at frequencies where the SNR supports it and conservative where it doesn't, on the same frame.

### 2. Per-program → per-frame
The "Restaurant" / "Outdoors" / "Car" / "Music" program-switching architecture in commercial hearing aids is an implicit admission that one WNG constant cannot span the acoustic world. Per-frame, frequency-dependent learned thresholds dissolve that constraint — the program switch becomes redundant.

### 3. The DSP-vs-DNN boundary moves up one level
- 2010s: DNN-NR began displacing classical Wiener filtering in the *spectral* stage.
- 2020s: DNN feedback cancellation appeared in shipping HAs.
- **June 2026: First credible end-to-end-trainable replacement for the *spatial* stage.** This is the part of the pipeline that resisted ML longest because the physics was well understood and the analytical solutions were strong.

### 4. Joint optimisation collapses another cascade
Same lesson as SE-AGCNet (arXiv:2606.25959, joint SE+AGC/WDRC) hit the day before: the cascaded NR→Spatial→WDRC structure of HA processing is an organisational artefact of the eras when each block was tuned by a separate team. Differentiable joint training removes the artefact.

## Open Questions for Deployment in Hearing Aids
- **Latency budget:** the differentiable robust-MVDR layer must fit inside the algorithmic latency budget (≤10 ms is the clinical comfort threshold). Whether the joint network + layer fits at sub-10 ms on shipping HA SoCs is unproven.
- **Realistic HA arrays:** the venue is Interspeech, not Clarity Challenge; HA-specific 2–3-mic BTE/RIC constellations may require follow-up evaluation. The reported results may not transfer directly to small-aperture arrays.
- **Microphone drift:** wax, vent, and sweat drift on tiny BTE mics over the device lifetime is partially mitigated today by conservative fixed WNG. A learned threshold must remain robust under this drift, ideally calibrated by continual on-device learning.
- **Interaction with downstream DNN-NR and WDRC:** if spatial is learned, spectral is learned, and loudness control is learned, the whole chain wants to be *one* learned block end-to-end. The cascade-collapse argument from SE-AGCNet (joint SE+WDRC) and from this paper (joint mask+beamformer) compose into one design pressure for 2028 HA architectures.
- **Audiologist interpretability:** when WNG is a fixed parameter, the fitter knows what it does. When it's a per-frame learned function, the fitter has no direct lever. The fitting-software UI question is open.

## Adjacent Operator Families
- **Differentiable cochlear models** (Drakopoulos / Verhulst lineage; Google DAL arXiv:2606.04103) — the differentiable-operator paradigm one stage upstream (auditory periphery as a layer).
- **Differentiable adaptive filtering** (DDSP-FxLMS, June 2026) — the adaptive-filter operator family for ANC / room EQ as a learned layer.
- **Joint SE + WDRC** (SE-AGCNet, arXiv:2606.25959) — joint optimisation across NR and loudness control.

Together these three plus differentiable MVDR are the operator family that turns the entire classical-DSP HA processing chain into one trainable graph.

## Related Pages
- [[dnn-architectures-hearing-aids]] — the architectural context this concept extends.
- [[dnn-in-hearing-aids]] — the broader DNN displacement timeline (Wiener → spatial → loudness).
- [[differentiable-dsp]] — parent operator family.
- [[joint-se-wdrc-end-to-end]] — sibling cascade-collapse work the day before.
- [[on-device-ml-hearing-aids]] — deployment constraints (latency, power, mic-drift).
- [[fxlms-adaptive-filtering]] — adjacent learned-adaptive-filter operator.
- [[../syntheses/hearing-aid-ai-stack-2026]] — moves another tile from "classical DSP" to "learned block."
- [[../syntheses/on-chip-hearing-ai-levers-june-2026]] — sixth lever (the spatial stage itself).

## Sources
- [Deng, Pei, Ma, Huang, Chen, Benesty — Joint Learning of Covariance Estimation and White Noise Gain for Robust MVDR Beamforming](../sources/deng-pei-ma-joint-mvdr-wng-arxiv-2606-24137-jun-2026.md) — primary; arXiv:2606.24137, 23 Jun 2026, Interspeech 2026.
