---
title: "Joint Learning of Covariance Estimation and White Noise Gain for Robust MVDR Beamforming"
type: source
source_type: arxiv-preprint
date_published: 2026-06-23
date_ingested: 2026-06-26
authors: [Yongyi Deng, Hanchen Pei, Jianbo Ma, Gongping Huang, Jingdong Chen, Jacob Benesty]
identifier: arXiv:2606.24137
url: https://arxiv.org/abs/2606.24137
venue: arXiv eess.AS / accepted Interspeech 2026
tags: [mvdr-beamforming, white-noise-gain, diagonal-loading, microphone-array, differentiable-beamforming, end-to-end-learning, hearing-aid-spatial-stage, interspeech-2026]
---

# Joint Learning of Covariance Estimation and White Noise Gain for Robust MVDR Beamforming

## Bibliographic
- **Authors:** Yongyi Deng, Hanchen Pei, Jianbo Ma, Gongping Huang, Jingdong Chen, Jacob Benesty
- **Affiliation:** Centre of Intelligent Acoustics & Immersive Communications (Northwestern Polytechnical University, Xi'an) and INRS-EMT (Montreal) — the Chen / Benesty / Huang collaboration is the standing reference cluster on robust array signal processing.
- **arXiv ID:** 2606.24137 (eess.AS)
- **Submitted:** 23 Jun 2026
- **Venue:** Accepted, Interspeech 2026
- **URL:** https://arxiv.org/abs/2606.24137

## Headline Claim
Conventional **Minimum Variance Distortionless Response (MVDR)** beamforming relies on a hand-tuned **White Noise Gain (WNG)** threshold or a fixed diagonal-loading constant to remain stable when the noise covariance is ill-conditioned. This paper makes both the noise-covariance estimate **and** the WNG threshold *learnable*, via a differentiable robust-MVDR layer, end-to-end.

## Architecture
- **Input:** multi-channel microphone signal (no specific channel count fixed; common targets: 2-mic BTE, 3-mic RIC, hearable arrays).
- **Single network jointly predicts:**
  1. A **time-frequency noise mask** used to estimate the noise spatial covariance matrix Φ_nn.
  2. A **frequency-dependent WNG threshold** per frame — the regularisation strength that decides how much diagonal loading is applied.
- **Differentiable robust-MVDR layer** consumes both predictions and applies the closed-form beamforming weights; gradients flow back through the layer to the joint network.
- End-to-end training against a speech-quality / intelligibility objective.

## Why This Is Non-Trivial
- Robust MVDR has a known weak point: when the noise covariance is rank-deficient or poorly estimated, the beamformer over-fits and amplifies microphone self-noise. Diagonal loading (Cox 1987) and explicit WNG constraints (Doclo / Gannot lineage) regularise it — but the loading constant or WNG threshold has been hand-tuned per application for 30+ years.
- The constant is a **single-number compromise** across all frequencies and all acoustic conditions. Per-program tables (Restaurant / Outdoors / Car) in commercial hearing aids are the field's empirical workaround.
- Joint learning of *covariance estimate and regularisation* avoids the standard pipeline pattern of "DNN mask → classical beamformer → classical post-filter," each tuned separately.

## Reported Results
- Consistent improvements in speech quality and intelligibility over fixed-WNG MVDR baselines under unknown / time-varying acoustic conditions (specific PESQ / STOI / SI-SDR numbers not detailed in the abstract excerpt available — full paper required for exact figures).
- The paper frames the learned WNG threshold as adaptive to instantaneous SNR and acoustic context — the regime where fixed thresholds are most fragile.

## Why This Matters for Hearing-Aid Spatial Processing
1. **The 30-year manual-tuning art becomes a back-prop problem.** WNG constants in HA beamformers have been one of the last bastions of audiologist-/DSP-engineer-tuned parameters that resisted ML displacement. This paper makes them learned.
2. **Per-program → per-frame.** Per-program WNG tables are an admission that one constant cannot span the acoustic world. Per-frame, frequency-dependent learned thresholds dissolve that constraint without a program switch.
3. **The DSP-vs-DNN boundary moves up one level.** DNN-NR has already replaced classical Wiener filtering in shipping HAs. This paper is the first plausible end-to-end-trainable replacement for the *spatial* stage — the part of the HA pipeline that has resisted ML longest because the physics was well understood and the analytical solutions were strong.
4. **Joint optimisation kills another cascade.** Same lesson as SE-AGCNet (arXiv:2606.25959, 24 Jun 2026) on the NR→WDRC interface, and as joint mask-estimator + beamformer work generally: cascades in the HA processing chain are organisational artefacts, not laws.

## Open Questions for Hearing-Aid Deployment
- Latency budget of the proposed differentiable robust-MVDR layer at sub-10 ms algorithmic latency on shipping HA SoCs.
- Behaviour with realistic BTE / RIC 2–3-mic constellations (paper venue is Interspeech, not Clarity Challenge; HA-specific arrays may need a follow-up evaluation).
- Interaction with downstream DNN-NR and WDRC — the joint-optimisation argument suggests the whole spatial-then-spectral-then-loudness chain should be one learned block, not three.
- Robustness to microphone mismatch over the life of a hearing aid (real-world wax / vent / sweat drift on tiny BTE mics is a long-standing pain point that fixed-WNG architectures partially mitigated by being conservative).

## Cross-References Inside This Wiki
- `wiki/concepts/dnn-architectures-hearing-aids.md` — the spatial stage is one of the few remaining DSP-only blocks in shipping HAs.
- `wiki/concepts/dnn-in-hearing-aids.md` — extends DNN displacement to spatial processing.
- `wiki/concepts/differentiable-dsp.md` — differentiable-MVDR is a flagship example of the differentiable-DSP operator family.
- `wiki/concepts/joint-se-wdrc-end-to-end.md` — parallel cascade-collapse argument at the loudness-control interface.
- `wiki/concepts/on-device-ml-hearing-aids.md` — deployability constraints.
- `wiki/concepts/speech-enhancement-neural-networks.md` — adjacent SE family.
- `wiki/syntheses/on-chip-hearing-ai-levers-june-2026.md` — adds a sixth lever to the on-chip-efficiency synthesis (the spatial stage itself).
- `wiki/syntheses/hearing-aid-ai-stack-2026.md` — moves another tile from "classical DSP" to "learned block."
