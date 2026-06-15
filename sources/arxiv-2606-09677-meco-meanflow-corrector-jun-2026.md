---
title: MeCo — One-Step MeanFlow-based Corrector for Multi-Channel Speech Separation
type: source
date: 2026-06-08
ingested: 2026-06-15
authors: [Dohwan Kim, Jung-Woo Choi]
publication: arXiv:2606.09677 (eess.AS), accepted Interspeech 2026
url: https://arxiv.org/abs/2606.09677
institution: KAIST (School of Electrical Engineering)
tags: [speech-separation, multi-channel, generative-correction, meanflow, one-step-inference, data-space-optimization, dso, si-sdr, interspeech-2026, hearing-aids, discriminative-generative-stack, hallucination-mitigation]
---

# MeCo — One-Step MeanFlow-based Corrector for Multi-Channel Speech Separation

## Metadata
- **Title:** MeCo: One-Step MeanFlow-based Corrector for Multi-Channel Speech Separation
- **Authors:** Dohwan Kim, Jung-Woo Choi (KAIST)
- **arXiv:** 2606.09677 (eess.AS)
- **Posted:** June 8-9, 2026
- **Accepted:** Interspeech 2026 (5 pages)

## Method
- Architecture: a **discriminative multi-channel speech separator** produces an initial estimate; a **single-step MeanFlow-based corrector** maps that estimate onto the clean-speech manifold using a learned **conditional average velocity field**.
- Inference: one forward step through the corrector — no diffusion-style multi-step sampling.
- Loss: **Data-Space Optimization (DSO)** — combines:
  - **x_r-loss**, penalizing reconstruction error on longer displacement intervals (perceptual / listening quality target)
  - **Endpoint SI-SDR loss**, optimizing terminal signal fidelity
- Claimed result: SOTA on multi-channel separation in both in-domain and out-of-domain scenarios with "minimal computational overhead."

## Why It Matters for Hearing AI

### One step clears the latency floor
- Hearing-aid algorithmic delay budgets typically sit at ~1-10 ms; multi-step diffusion SE (25-50 steps at ~100 µs/step) cannot fit.
- One-step generative correction is one of the few generative-family designs structurally compatible with HA latency.
- Sibling axis: **SB-RF** (arXiv:2606.05575, June 4) — also one-step, but standalone generative SE rather than a corrector.

### Discriminative + thin generative head answers the hallucination question
- Pure generative SE produces measurably more hallucinations (phoneme-level WER gap) than discriminative SE — quantified in Saha Shetu et al., arXiv:2606.02913 (June 1, 2026).
- The MeCo stacking pattern — **discriminative for "what was said" + generative corrector for "how it should sound"** — preserves the hallucination-resistance of the discriminative front while recovering perceptual naturalness from the generative back.
- Translates the field debate ("discriminative vs generative") into a stack design ("where in the pipeline does the corrector live").

### DSO is a perceptual-fidelity hybrid loss
- SI-SDR alone over-rewards signal-space alignment; perceptual-only losses over-reward smoothness.
- DSO explicitly carries both axes — closer to what hearing-aid listeners actually rate.
- Complements the field's still-incomplete evaluation-stack work (HASPI/STOI for perceptual + WER for lexical fidelity + listening effort as separate axes).

### Multi-channel = directly relevant to hearing aids
- Hearing aids are inherently multi-channel devices (≥2 mics per side, 4-6 total in bilateral fittings).
- Most generative SE work has been monaural; MeCo's multi-channel framing is the more deployment-relevant target.

### Open piece
- Reported benchmarks are general multi-channel separation; the port to CPC3 / HASPI / listening-effort metrics in a hearing-aid scenario is unwritten.
- Compute overhead is "minimal" but not stated in chip-level numbers; FPGA-style measurements (cf Olalere et al., arXiv:2606.04221, June 4) would close that gap.

## Cross-References
- Related source: `arxiv-2606-02913-generative-vs-discriminative-se-jun-2026.md` (the hallucination-receipts paper that this post is the constructive answer to)
- Related source: `arxiv-2606-05575-sbrf-schrodinger-bridge-jun-2026.md` (sibling one-step generative-SE axis)
- Related source: `arxiv-2606-04221-olalere-fpga-speech-enhancement-jun-2026.md` (the on-chip latency budget MeCo's one-step inference is designed to clear)
- Related concept: `speech-enhancement-neural-networks.md` (add MeCo as a discriminative-plus-generative-corrector pattern)
- Related concept: `linguistic-hallucination-speech-enhancement.md` (MeCo's stack design as a mitigation pattern)
- Related concept: `listening-effort-evaluation.md` (DSO as a hybrid-loss precedent)
- Related concept: `one-step-generative-correction.md` (new candidate concept page — MeCo + SB-RF define this category)
