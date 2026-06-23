---
title: Acoustic Feedback Cancellation in Hearing Aids
type: concept
created: 2026-06-03
updated: 2026-06-23
last_change: "2026-06-23 — Added DDSP-EQ recast of FxLMS (Marcos-Macias et al., arXiv:2606.22563, DAFx26, Jun 21 2026) as a complementary differentiable framing of the classical adaptive-filter side; added cross-refs to the new `fxlms-adaptive-filtering` and `differentiable-dsp` concept pages and the DDSP-EQ source."
sources:
  - arxiv-2606-03832-dfc-il-voit-doclo-jun-2026.md
  - arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md
related:
  - training-deployment-distribution-gap.md
  - dnn-architectures-hearing-aids.md
  - on-device-ml-hearing-aids.md
  - speech-enhancement-neural-networks.md
  - differentiable-dsp.md
  - fxlms-adaptive-filtering.md
  - room-aware-dereverberation.md
tags: [acoustic-feedback, dfc, howl, closed-loop, deep-feedback-cancellation, dsp, hearing-aid-fundamentals, fxlms, ddsp]
---

# Acoustic Feedback Cancellation in Hearing Aids

## Concept
Acoustic feedback is the closed-loop signal path from the hearing-aid receiver (loudspeaker) back to the microphone via the ear-canal vent and leakage around the device. When loop gain exceeds unity at any frequency, the system becomes unstable: the wearer hears the characteristic "howl" or "whistle."

Feedback cancellation is the **oldest** consequential signal-processing problem in hearing aids and constrains the maximum stable amplification gain the device can deliver — directly bounding the population the device can serve (more profound hearing losses need more gain).

## Classical Approach
Adaptive filters (LMS, NLMS, RLS, frequency-domain variants) estimate the feedback path and subtract its prediction from the microphone signal. Long studied; well understood; but:
- Slow convergence under non-stationary paths.
- Bias in the presence of correlated input (tonal music, narrowband speech features).
- Difficulty maintaining stability margin under sudden physical perturbation (jaw movement, hat, phone-to-ear).

## Deep Feedback Cancellation (DFC)
Neural networks have been applied to feedback cancellation since the late 2010s. Architectures include CRNs, lightweight LSTMs, and Mamba-class state-space models. The promised advantage is **better generalization across non-stationary paths and correlated inputs**.

Until June 2026, the predominant training paradigm was **open-loop**: the DFC network was exposed during training to feedback signals collected or simulated under stable conditions, then deployed into the closed-loop system at inference.

## In-the-Loop Training (DFC-IL, Voit & Doclo, June 2026)
A new arXiv preprint (2606.03832, 2 June 2026) by Voit & Doclo proposes integrating the DFC network **directly into the closed-loop optimisation during training**. The training signal includes the unstable dynamics the network will face at deployment.

Results:
- At low amplification gains, DFC-IL ties open-loop baselines (no penalty for the methodology).
- At high amplification gains — the clinically meaningful regime — DFC-IL holds stability while open-loop variants begin to howl.

This is the cleanest demonstration to date that the training-loop closure is itself the bottleneck, not the architecture. See [[training-deployment-distribution-gap]] for the broader methodological argument.

## Why This Matters
- **Profound-loss candidacy.** Maximum stable amplification gain bounds whom the device can serve. Better feedback cancellation expands the addressable population at the high-loss end.
- **Open-fit form factors.** Receiver-in-canal and open-fit RICs are inherently more feedback-prone than closed custom ITEs; better DFC enables more wearable form factors without sacrificing gain.
- **On-chip constraint.** Feedback cancellation runs in the deepest part of the on-chip DSP path, every sample, before any speech enhancement layer. Whatever ships here defines the ceiling for everything downstream.

## The Classical FxLMS Track — DDSP Recast (Marcos-Macias et al., Jun 21 2026)
While DFC-IL pursues the neural side of the feedback-cancellation problem, a parallel June 2026 paper [arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md](../../sources/arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md) recasts the **classical FxLMS** family as a **Differentiable DSP (DDSP)** special case. FxLMS is the workhorse adaptive filter behind feedback cancellation, vent compensation, and room EQ for streamed audio; the DDSP framing recovers it exactly under specific filter / loss / optimiser choices and lets alternative EQ topologies, perceptual losses, and modern optimisers plug in without re-deriving update rules.

The two threads are complementary rather than competing:

| Approach | Inductive bias | Strength |
|---|---|---|
| Classical FxLMS | Linear filter + MSE + LMS update | Cheap, stable, mature; safety floor |
| DDSP-EQ recast (Jun 21 2026) | Any filter topology + any loss + any optimiser | Topology / loss search; perceptual coupling |
| Neural DFC-IL (Jun 2 2026) | Generic neural network trained inside the closed loop | Handles fast non-stationary paths and correlated inputs |

A shipping product likely runs all three: classical FxLMS as the safety floor, DDSP-EQ for slow path drift and topology search, neural DFC for fast non-stationary feedback. Joint training across the trio is the obvious unbuilt experiment. See [[fxlms-adaptive-filtering]] and [[differentiable-dsp]].

## Open Questions
- What is the on-chip latency / parameter budget for DFC-IL?
- Does the in-the-loop training framing generalize to other on-chip components (noise reduction, beamforming, own-voice detection)?
- What does a closed-loop simulator that is differentiable end-to-end look like at production fidelity?
- Joint training of DDSP-EQ + neural DFC-IL + classical FxLMS as a single end-to-end stack is unpublished.
- Stability proofs for learned filter topologies (DDSP-EQ) vs the classical FxLMS convergence guarantees.

## Related Pages
- [[training-deployment-distribution-gap]] — the broader methodology argument DFC-IL exemplifies
- [[dnn-architectures-hearing-aids]] — the architectural alternatives within DFC
- [[on-device-ml-hearing-aids]] — the deployment substrate where DFC must live
- [[dsp-classical-vs-deep-learning]] — the classical-vs-neural comparison for this sub-problem
- [[fxlms-adaptive-filtering]] — the classical-DSP foundation that DDSP-EQ recasts
- [[differentiable-dsp]] — the broader DDSP operator family
- [[room-aware-dereverberation]] — RIR encoders on the SE side; DDSP-EQ on the adaptive-filter side; same axis (the room)

## Sources
- [Voit & Doclo — In-the-Loop Training of Deep Feedback Cancellation for Hearing Aids (arXiv:2606.03832)](../../sources/arxiv-2606-03832-dfc-il-voit-doclo-jun-2026.md) — DFC-IL framing, gain-regime stability evidence
- [Marcos-Macias et al. — DDSP Framework for Adaptive Room Equalization (arXiv:2606.22563, DAFx26, Jun 2026)](../../sources/arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md) — recovers classical FxLMS as a DDSP special case; ~70% system-distance reduction; open-source
