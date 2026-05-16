---
title: "Speech Enhancement Based on Drifting Models (DriftSE)"
type: academic-paper
date_published: 2026-04
date_ingested: 2026-05-16
url: https://arxiv.org/html/2604.24199v1
venue: arXiv (eess.AS); submitted to Interspeech 2026
tags: [speech-enhancement, generative-se, single-step-inference, equilibrium-model, diffusion-alternative, voicebank-demand, interspeech-2026, low-latency-se]
---

# DriftSE — One-Step Generative Speech Enhancement via Equilibrium Drift

## Summary

DriftSE is a generative speech-enhancement framework that formulates denoising as an *equilibrium* problem rather than a stepwise diffusion / score-matching reverse process. The model evolves the pushforward distribution of a learnable mapping function so that it converges directly onto the clean-speech distribution, allowing **single-step inference** at test time. On VoiceBank+DEMAND it matches or beats multi-step diffusion baselines while needing only one forward pass. Submitted to Interspeech 2026.

## Key Result

- One forward pass at inference (vs 25–50 NFE for standard diffusion SE baselines).
- Quality on par with multi-step diffusion SE (VoiceBank+DEMAND benchmark).
- Authors frame this as the first equilibrium-style generative SE to ship competitive perceptual numbers without iterative sampling.

## Why it matters for hearing aids

### The latency objection to generative SE
Generative SE (diffusion / flow-matching / autoregressive LM) has had clear quality wins over discriminative SE since 2024, but multi-step sampling has been the gating constraint for hearing-aid deployment. A 25-step reverse diffusion at 16 kHz, 10 ms frame size, with a moderately sized backbone is fundamentally incompatible with the <5 ms input-to-output latency a hearing aid needs. DriftSE-style **single-step** generative SE collapses this gap if real-time stability holds under streaming conditions.

### Sits adjacent to the L3-SE / linguistic-hallucination thread
DriftSE is a generative SE architecture, so it inherits the same failure-mode risk as autoregressive-LM SE (see L3-SE source / linguistic-hallucination concept page) — generative models can produce perceptually plausible but factually wrong speech. However, because DriftSE optimizes a direct distributional match rather than autoregressive next-token prediction, the hallucination surface may differ in structure. Worth a dedicated comparison once code/checkpoint are released.

### Predictive-generative drift decomposition adjacency
Conceptually adjacent to the predictive-generative drift-decomposition line from MERL/Hamburg (Richter et al., May 2026, arXiv:2605.06189), but the architectural approach is distinct — DriftSE evolves the *mapping* rather than decomposing input-side drift.

## Limitations / Open Questions

- **Streaming evaluation not yet shown.** VoiceBank+DEMAND is offline / utterance-level. The harder test is causal, frame-online operation at sub-10 ms algorithmic latency.
- **Compute envelope.** No reported MACs/parameter count in the abstract; single-step inference still has to fit in a HA DSP / NPU budget to matter at the edge.
- **Hallucination-resistance unverified.** As above — the generative-SE failure modes haven't been audited for this architecture.
- **Submission, not acceptance.** Interspeech 2026 review outcomes still pending; methodology may iterate.

## Related Wiki Pages
- [[speech-enhancement-neural-networks]] — Add DriftSE under Recent Academic Advances / Single-Step Generative SE.
- [[probabilistic-generative-models-hearing-ai]] — DriftSE is an equilibrium-style generative model; adjacent paradigm.
- [[linguistic-hallucination-speech-enhancement]] — Open question: does the equilibrium formulation reduce hallucination surface vs autoregressive LM SE?
- [[on-device-ml-hearing-aids]] — Single-step inference is the precondition for deploying generative SE in HA latency budgets.
- [[interspeech-2026-audio-reasoning-challenge]] (source) — Same conference cycle.
