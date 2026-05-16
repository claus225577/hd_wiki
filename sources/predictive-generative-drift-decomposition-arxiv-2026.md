---
title: "Predictive-Generative Drift Decomposition for Speech Enhancement and Separation"
authors: [Julius Richter, Yoshiki Masuyama, Christoph Boeddeker, Takahiro Edo, Gordon Wichern, Jonathan Le Roux]
affiliation: Mitsubishi Electric Research Labs (MERL) / Universität Hamburg / Paderborn
date: 2026-05-08
arxiv_id: "2605.06189"
url: https://arxiv.org/abs/2605.06189
arxiv_listing: https://arxiv.org/list/eess.AS/2026-05
type: research-paper
tags: [speech-enhancement, speech-separation, predictive-models, generative-models, diffusion, drift-decomposition, hearing-aids, merl]
---

# Predictive-Generative Drift Decomposition for Speech Enhancement and Separation (Richter et al., May 2026)

## Key Extraction

- **Question:** Predictive (deterministic, mask-based) speech-enhancement models are robust but plateau in perceptual quality and over-suppress speech in low-SNR conditions. Generative (diffusion / flow-based) models reach higher quality ceilings but can hallucinate and are less reliable. Can these be decomposed cleanly so each handles what it's good at?
- **Method:** Decompose the enhancement target into a predictive component (deterministic, learned mask / regression) and a generative *drift* component (a stochastic refinement modeled with a generative process). Train and infer them jointly so the generative path corrects the residual the predictive path leaves behind.
- **Authors / Affiliation:** Richter, Masuyama, Boeddeker, Edo, Wichern, Le Roux — MERL / Universität Hamburg / Paderborn. Le Roux's group at MERL is a long-running source of state-of-the-art in this space (DPRNN, MossFormer, GAP-URGENet lineage).

## Why This Matters for Hearing AI

- **The "robotic over-suppression" failure mode** is the #1 user complaint about modern DNN noise reduction in hearing aids — speech sounds artificial, especially in low SNR. Predictive models cause this; generative models could fix it.
- **Drift decomposition gives a knob.** A scalar weighting between predictive and generative paths lets a hearing-aid manufacturer expose a perceptual-comfort vs. fidelity slider — without retraining. This is exactly the kind of personalization handle that the field has been asking for.
- **Continuation of the GAP-URGENet thread.** GAP-URGENet (also MERL-adjacent, ICASSP 2026) won URGENT 2026 with a generative-predictive fusion approach. Drift decomposition is a more principled formulation of the same fusion idea — same group, same architecture family, more theory.
- **Hearing-aid hardware tradeoffs:** Generative inference is expensive. The decomposition makes it possible to gate the generative path conditionally (only when the predictive residual is high), which is the only way generative HA enhancement gets to fit in a 10 ms budget.

## Open Questions

- How heavy is the generative path at inference? Can it be conditional / gated rather than always-on?
- Subjective evaluation with hearing-impaired listeners (not normal-hearing benchmarks) — does the over-suppression complaint actually go away?
- Interaction with the listener-group analysis from Schulz et al. 2026 (CI users +5.7 dB vs HI +0.8 dB vs NH degraded): does generative drift refinement help most where predictive enhancement helps least?

## Source

arXiv:2605.06189 (eess.AS, submitted 8 May 2026). https://arxiv.org/abs/2605.06189 — backfilled 2026-05-11 from May 11 digest cycle.
