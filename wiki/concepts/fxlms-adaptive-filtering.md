---
title: FxLMS and Adaptive Filtering in Hearing Aids
type: concept
created: 2026-06-23
updated: 2026-06-23
sources:
  - arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md
related:
  - acoustic-feedback-cancellation.md
  - differentiable-dsp.md
  - room-aware-dereverberation.md
  - hidvas-dataset.md
  - dnn-architectures-hearing-aids.md
  - on-device-ml-hearing-aids.md
tags: [fxlms, filtered-x-lms, adaptive-filter, lms, nlms, feedback-cancellation, room-eq, vent-eq, secondary-path, dsp, classical-dsp, hearing-aid-fundamentals]
---

# FxLMS and Adaptive Filtering in Hearing Aids

The **Filtered-x Least Mean Squares (FxLMS)** algorithm is the workhorse adaptive filter behind a large fraction of classical hearing-aid signal processing: feedback cancellation, dome/vent compensation, leak management, room equalisation of streamed audio, and active noise control more broadly. Introduced for active noise control in the 1980s (Widrow, Burgess, Morgan), FxLMS handles the case where the **secondary path** between the controller's output and the error sensor must be accounted for in the gradient update — the "filtered-x" of the name.

## The Algorithm in One Paragraph
Classical LMS adapts a finite-impulse-response filter to minimise the instantaneous squared error between a desired and actual signal. In hearing-aid feedback cancellation, the actual signal is contaminated by the secondary path from the receiver (loudspeaker) back through the vent / leak to the microphone. FxLMS pre-filters the reference signal by an estimate of that secondary path before forming the gradient update — preserving stability and convergence guarantees that vanilla LMS loses in the presence of a non-trivial secondary path.

Variants in production hearing-aid silicon include NLMS (normalised step size), frequency-domain block LMS, partitioned-FFT FxLMS for long impulse responses, and various stabilisation tricks (leakage, regularisation, step-size scheduling) for non-stationary inputs.

## Where It Lives in the Hearing-Aid Stack
- **Feedback cancellation.** The canonical use case. Estimate the receiver-to-mic feedback path through vent and leakage; subtract its prediction from the mic signal. Bounds the maximum stable amplification gain the device can deliver — directly bounding the population it can serve. See [[acoustic-feedback-cancellation]].
- **Vent / dome compensation.** Open and semi-open dome fittings allow low-frequency leak that interacts with applied gain. FxLMS-family filters adapt the compensation EQ to the wearer's chosen dome and to time-varying physical conditions (jaw movement, hat, phone-to-ear).
- **Room EQ for streaming audio.** When a hearing aid streams from TV / phone / Auracast, the receiver-to-eardrum path inside the ear canal is a small "room" that the device equalises.
- **Multi-mic noise reduction (legacy / classical).** Adaptive directional and noise-reduction blocks predating modern neural SE — still ship in the classical processing branch of every OEM platform.

## Strengths
- **Computationally cheap.** A handful of MACs per sample; trivial to fit inside hearing-aid power and area budgets.
- **Well-understood stability.** Classical convergence and stability proofs under specified secondary-path conditions and input signal classes.
- **Predictable on-chip latency.** Sample-by-sample updates inside a tight DSP loop.
- **Decades of OEM productisation.** Every shipping hearing-aid platform has a mature FxLMS-family implementation tuned, regression-tested, and clinically validated.

## Weaknesses That Recent Work Targets
- **Locked to a specific filter topology and update rule.** Changing the EQ structure, loss, or optimiser requires re-deriving the analytical update rules and re-proving stability.
- **Slow convergence under non-stationary paths.** Sudden physical perturbations (donning a hat, jaw motion) can outrun classical adaptation rates.
- **Bias in the presence of correlated input.** Tonal music and narrowband speech features can bias the FC estimate.
- **No native coupling to perceptual losses.** FxLMS minimises a signal-domain MSE; it has no direct route to HASPI / STOI / cochlear-domain losses.

## The 2026 DDSP Recast (Marcos-Macias et al., Jun 21 2026)
[arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md](../../sources/arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md). A **Differentiable DSP (DDSP)** framework for adaptive room EQ that **recovers classical FxLMS as a special case** under a specific choice of EQ structure (linear filter), loss (per-sample MSE), and optimiser (SGD with secondary-path-filtered reference). Different EQ topologies, perceptual losses, and modern optimisers (Adam, RMSprop) plug in without re-deriving update rules.

Reported numbers:
- **~70% reduction in system distance** vs unequalised baseline
- **13% worst-case mel-spectral distance improvement** vs unequalised response (the *worst* test condition improves by 13% — not just the average)
- Open-source implementation

**Why this matters:** the analytical algorithm engineers spent forty years tuning by hand becomes one point in a continuous parameter space the framework can search over. FxLMS is preserved as a deployable default; everything else above it (alternative topologies, perceptual losses, modern optimisers) becomes a hyperparameter choice rather than a research project. See [[differentiable-dsp]] for the broader operator family.

## Complementary to Neural Feedback Cancellation
The DDSP-EQ recast and the neural-feedback-cancellation thread (DFC-IL, Voit & Doclo, Jun 2026 — see [[acoustic-feedback-cancellation]]) target the same underlying loop with different inductive biases:

| Approach | Inductive bias | Strength |
|---|---|---|
| Classical FxLMS | Linear filter + MSE loss + LMS update | Cheap, stable, mature |
| DDSP-EQ recast | Any filter topology + any loss + any optimiser | Topology / loss search; perceptual coupling |
| Neural DFC (DFC-IL) | Generic neural network trained inside the closed loop | Handles fast non-stationary paths and correlated inputs |

These are likely complementary in a shipping product: DDSP-EQ for slow path drift and topology search, neural DFC for fast non-stationary feedback, classical FxLMS as the safety floor. The joint-training stack across all three is not yet published.

## HIDVAS as the Measurement Substrate
The KU Leuven HIDVAS dataset (`hidvas-dataset.md`) publishes real dummy-head impulse responses across **4 dome configurations × 4 reverberation conditions** — exactly the variation an adaptive-filter framework needs to train, evaluate, and personalise against. DDSP-EQ + HIDVAS together close a loop where the data substrate, the optimiser, and the differentiable operator are all open.

## Open Questions
- **Inference-time cost of DDSP-EQ.** Training-time autodiff is fine; the deployable footprint at runtime is the open number for any chip-targeted use.
- **Stability proofs for learned topologies.** Classical FxLMS has known convergence guarantees. Do gradient-trained filter topologies inherit them, or do they need new analysis?
- **Per-wearer fitting workflow.** Warm-start from a population FxLMS prior, fine-tune on the wearer's measured IRs — fits cleanly into clinical practice but no OEM has published a workflow.
- **Joint training with neural DFC and DDSP-EQ.** Open.
- **Coupling to perceptual losses.** Can DDSP-EQ losses flow through a differentiable cochlea (DAL) for per-wearer perceptually-grounded EQ?

## Related Pages
- [[acoustic-feedback-cancellation]] — the canonical FxLMS application; neural DFC-IL is the parallel research thread
- [[differentiable-dsp]] — the DDSP operator family DDSP-EQ belongs to
- [[room-aware-dereverberation]] — RIR encoders as the SE-side parallel to FxLMS room EQ
- [[hidvas-dataset]] — measurement substrate for DDSP-EQ
- [[dnn-architectures-hearing-aids]] — neural architectures competing with / complementing classical adaptive filters
- [[on-device-ml-hearing-aids]] — deployment target

## Sources
- [Marcos-Macias et al. — DDSP Framework for Adaptive Room Equalization (arXiv:2606.22563, DAFx26, Jun 2026)](../../sources/arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md) — recovers FxLMS as a DDSP special case
