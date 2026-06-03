---
title: "In-the-Loop Training of Deep Feedback Cancellation for Hearing Aids"
type: source
source_type: arxiv-preprint
date_published: 2026-06-02
date_ingested: 2026-06-03
authors: [Svantje Voit, Simon Doclo]
identifier: arXiv:2606.03832
url: https://arxiv.org/abs/2606.03832
venue: arXiv (eess.AS)
tags: [hearing-aids, acoustic-feedback, deep-feedback-cancellation, in-the-loop-training, closed-loop-dynamics, training-deployment-gap, dsp, on-chip]
---

# In-the-Loop Training of Deep Feedback Cancellation for Hearing Aids

## Bibliographic
- **Authors:** Svantje Voit, Simon Doclo
- **Posted:** 2 June 2026
- **arXiv:** 2606.03832 (eess.AS)
- **URL:** https://arxiv.org/abs/2606.03832

## Problem
Acoustic feedback (the "howl" loop between hearing-aid receiver and microphone via the ear-canal vent and surrounding leakage paths) limits useable amplification gain. Classical adaptive filters (LMS / RLS variants) and modern deep feedback cancellation (DFC) networks both face the same structural problem: the closed-loop feedback path is **non-stationary, gain-dependent, and unstable at the operating points that matter clinically**.

Prior DFC literature has trained networks in an **open-loop** regime — that is, the network is exposed during training to feedback signals generated under stable conditions and asked to learn the mapping. At deployment, when the device runs at high amplification and the feedback path approaches instability, the open-loop-trained network sees inputs unlike anything in its training distribution.

## Contribution
DFC-IL ("In-the-Loop") integrates the neural network **directly into the closed-loop optimisation during training**. The training signal includes the unstable dynamics the network will face at deployment, not just the steady-state ones.

## Key Results
- At **low amplification gains**, DFC-IL performs **comparably** to open-loop-trained baselines.
- At **high amplification gains** — the operating regime where feedback failures are clinically meaningful — DFC-IL **holds stability** while the open-loop alternative begins to howl.

## Why This Matters Beyond Feedback Cancellation
The methodology generalizes. Most hearing-aid ML pipelines (speech enhancement, beamforming, scene classification, noise reduction, own-voice detection) are trained on **clean offline corpora** under quasi-stationary conditions and deployed into **non-stationary, closed-loop acoustic environments**. The train/deploy distribution gap that DFC-IL addresses for feedback cancellation is the same gap, structurally, that other hearing-aid ML components silently inherit. The architectural lever has been "bigger model, more data"; this paper argues the training-loop lever may be larger.

## Open Questions / Limitations
- Affiliations not specified in the abstract page text retrieved (likely University of Oldenburg given Doclo's group; not verified here).
- The paper does not report on-chip latency / parameter footprint trade-offs explicitly in the abstract.
- Generalization claim (to SE, beamforming, etc.) is implied by the methodology but not demonstrated in this paper.

## Used In
- [[wiki/concepts/training-deployment-distribution-gap.md]]
- [[wiki/concepts/acoustic-feedback-cancellation.md]] (new)
- [[wiki/syntheses/hearing-aid-ai-stack-2026.md]] (update)
