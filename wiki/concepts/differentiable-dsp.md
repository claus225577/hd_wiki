---
title: Differentiable DSP (DDSP) for Hearing AI
type: concept
created: 2026-06-23
updated: 2026-06-23
sources:
  - arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md
  - dal-differentiable-auditory-loop-google-june-2026.md
  - arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md
related:
  - acoustic-feedback-cancellation.md
  - room-aware-dereverberation.md
  - differentiable-cochlear-models.md
  - speech-enhancement-neural-networks.md
  - hidvas-dataset.md
  - training-deployment-distribution-gap.md
  - on-device-ml-hearing-aids.md
tags: [ddsp, differentiable-dsp, fxlms, adaptive-filtering, room-eq, vent-eq, feedback-cancellation, dafx, hearing-aids, open-source, autodiff]
---

# Differentiable DSP (DDSP) for Hearing AI

A class of methods that re-express classical analytical signal-processing algorithms (adaptive filters, fixed-coefficient EQs, parametric synthesisers) as **operations inside an autodiff graph**, so that the algorithm's free parameters can be optimised by gradient descent and the algorithm itself can be composed with neural networks under a unified training objective.

The term was popularised by Engel et al. 2020 in the music synthesis context (the original "DDSP" paper). In hearing AI, the same operator family is being applied to adaptive filtering, feedback cancellation, room and vent EQ, and the coupling to perceptual / cochlear losses.

## Why It Matters
Hearing-aid signal processing has been built for forty years out of analytically derived blocks: filterbank analysis, AGC, feedback cancellation (FxLMS family), vent compensation, noise reduction, multi-mic beamforming. Each block has its own hand-derived update rule, stability proof, and parameter-tuning ritual.

DDSP reframes each of those blocks as a **point in a continuous parameter space the framework can search over**. The classical algorithm is recovered as one configuration of the differentiable operator; novel filter topologies, perceptual losses, and modern optimisers (Adam, RMSprop) plug in without re-deriving update rules. Crucially, the resulting block is **end-to-end trainable** with whatever sits downstream — a perceptual loss, a neural SE network, a cochlear model.

## Three Hearing-AI DDSP Beachheads (June 2026)

### 1. DDSP-EQ — Adaptive Room Equalization (Marcos-Macias et al., Jun 21 2026)
[arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md](../../sources/arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md). Accepted at DAFx26. **Recovers classical filtered-x LMS (FxLMS) as a special case** of a general DDSP adaptive-EQ framework. Different EQ structures (cascade biquads, parametric EQs, learned implicit responses), perceptual losses, and modern optimisers all plug in. Reported: **~70% reduction in system distance**, **13% worst-case mel-spectral distance improvement** vs unequalised baseline. Open-source implementation. See [[fxlms-adaptive-filtering]] for the algorithmic foundation.

### 2. DAL — Differentiable Auditory Loop (Ballesta Rosen et al., Jun 4 2026)
[dal-differentiable-auditory-loop-google-june-2026.md](../../sources/dal-differentiable-auditory-loop-google-june-2026.md). Google Research Australia + Macquarie. Puts the **CARFAC** cochlear model inside the training loop via JAX. The training loss flows through a differentiable periphery: a SEANet UNet generator learns by gradient descent to push the impaired cochlea's output toward a normal-hearing reference. See [[differentiable-cochlear-models]].

### 3. HIDVAS — Real Measurement Substrate (Roebben et al., KU Leuven, Jun 12 2026)
[arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md](../../sources/arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md). Not a DDSP method, but the data substrate the DDSP-EQ framework needs: dummy-head recordings across **4 dome configurations × 4 reverberation conditions**, including impulse responses. Stacks with DDSP-EQ to support per-dome / per-room personalisation studies. See [[hidvas-dataset]].

## The Unifying Architectural Move
Across all three, the same shift recurs:

> **Take an analytically derived algorithm or hand-tuned block; re-express it as a parametric operator in an autodiff graph; expose its parameters, topology, and loss to gradient descent.**

For DAL, the analytical step being differentiated is the cochlear periphery. For DDSP-EQ, it is the FxLMS update rule. For neural feedback cancellation (DFC-IL, Voit & Doclo, Jun 2026), it is the closed-loop optimisation of the FC network. The result is a stack where every previously hand-derived hearing-aid block has a continuous, gradient-trainable formulation.

## Why FxLMS Recasting Matters for Hearing Aids
FxLMS sits at the deepest part of the on-chip path. It runs **every sample**, ahead of any neural SE stage, and bounds the maximum stable gain the device can deliver. Recasting it as a DDSP special case:
- **Unifies feedback cancellation, vent-EQ, and room-EQ** under a single differentiable operator family. All three are FxLMS-shaped problems with different secondary paths.
- **Exposes EQ topology + loss + optimiser as free hyperparameters.** Today these are hand-chosen per OEM, per product, per dome. DDSP lets them be searched.
- **Enables joint optimisation with downstream stages.** A DDSP-EQ block can be trained jointly with a neural SE backbone, with the perceptual loss flowing back through both. Today's stack treats them as independent calibration steps.

## Relationship to Other Hearing-AI Frontiers
- **Neural Feedback Cancellation (DFC-IL)** — Voit & Doclo, Jun 2026. Trains the feedback canceller inside the closed loop. Complementary to DDSP-EQ: DFC-IL handles fast non-stationary feedback (sudden jaw movement, hat); DDSP-EQ handles slow path drift and topology choice. See [[acoustic-feedback-cancellation]].
- **Room-aware SE (RIR encoders)** — Khanagha & Gerkmann, Jun 2026. Exposes the room as an explicit conditioning embedding the SE network can read. DDSP-EQ exposes the room as a parameterised filter the EQ stage can adapt. Two different operator families on the same axis (the room). See [[room-aware-dereverberation]].
- **Differentiable cochlear models (DAL / CARFAC-JAX)** — the differentiable-substrate move on the *perceptual* side. DDSP-EQ is the same move on the *acoustic-physical* side. Both are gradients-flow-where-they-couldn't-before. See [[differentiable-cochlear-models]].
- **Task-optimized DNNs as auditory models** — Saddler & McDermott. The *which features matter* programme that pairs with DAL's *how to train through them* programme. DDSP-EQ is the *which adaptive filters are deployable* programme on the DSP side.

## Open Questions
- **On-chip cost at deployment.** FxLMS is famously cheap (handful of MACs per sample). Does the DDSP recast preserve that footprint at inference, or only at training time?
- **Stability guarantees.** FxLMS has classical convergence proofs under known secondary-path conditions. Do learned EQ topologies inherit those guarantees, or do they need a new analysis?
- **Joint training stack.** No published framework trains DDSP-EQ + neural DFC-IL + RIR-conditioned SE + differentiable cochlear loss simultaneously. That's the obvious next experiment.
- **Per-wearer fitting workflow.** A personalised vent-EQ per dome configuration is the natural clinical use. Does the framework warm-start from population priors + fine-tune on the wearer's measured IRs?
- **Regulatory framing.** If every fitting flow becomes a gradient-descent run on patient-specific IRs (HIDVAS-style), Predetermined Change Control Plans and FDA AI/ML SaMD framing apply to what was previously an off-line calibration step.

## Related Pages
- [[acoustic-feedback-cancellation]] — the canonical FxLMS hearing-aid application; DDSP-EQ is the differentiable recast
- [[room-aware-dereverberation]] — RIR encoders as the SE-side parallel
- [[differentiable-cochlear-models]] — the perceptual-side differentiable substrate (DAL / CARFAC-JAX)
- [[speech-enhancement-neural-networks]] — downstream consumer of jointly-trained DDSP blocks
- [[hidvas-dataset]] — real measurement substrate for DDSP-EQ training and evaluation
- [[training-deployment-distribution-gap]] — DDSP-EQ closes the gap by allowing training-time IRs to match deployment-time configurations
- [[on-device-ml-hearing-aids]] — deployment target; inference-time cost is the open number

## Sources
- [Marcos-Macias et al. — DDSP Framework for Adaptive Room Equalization (arXiv:2606.22563, DAFx26, Jun 2026)](../../sources/arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md) — recovers FxLMS as a DDSP special case; ~70% system-distance reduction; open-source
- [Ballesta Rosen et al. — Differentiable Auditory Loop (arXiv:2606.04103, Jun 2026)](../../sources/dal-differentiable-auditory-loop-google-june-2026.md) — perceptual-side DDSP
- [Roebben et al. — HIDVAS (arXiv:2606.14175, EURASIP JASMP, Jun 2026)](../../sources/arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md) — measurement substrate
