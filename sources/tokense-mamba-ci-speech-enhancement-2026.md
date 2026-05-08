---
title: "TokenSE: Mamba-Based Discrete Token Speech Enhancement for Cochlear Implants"
type: paper
date: 2026-04-14
url: https://arxiv.org/abs/2604.12246
tags: [speech-enhancement, cochlear-implant, mamba, state-space-models, discrete-tokens, subjective-testing]
---

# TokenSE: Mamba-Based Discrete Token Speech Enhancement for Cochlear Implants

**Authors:** Chiang & Hansen
**arXiv:** 2604.12246 (April 14, 2026)

## Key Findings

- Proposes TokenSE: a speech enhancement system using **Mamba (selective state space model)** architecture operating on **discrete speech tokens** for cochlear implant users
- **Linear complexity O(n)** vs quadratic O(n^2) for Transformer-based approaches — critical for real-time CI processing
- Discrete token representation: encodes speech as a sequence of learned tokens rather than raw spectral features
- **Subjective tests with actual CI users** confirm intelligibility gains — not just objective metrics (PESQ/STOI)
- CI user evaluation is the gold standard for this domain; many SE papers only report objective metrics or test with normal-hearing listeners using vocoded speech

## Significance for Hearing AI

- **First Mamba-based speech enhancement for CI:** Demonstrates that state space models (specifically Mamba's selective mechanism) are viable for CI-specific speech enhancement
- **Linear complexity is a game-changer for CI processors:** CI speech processors have even tighter compute budgets than hearing aids; O(n) scaling vs O(n^2) could enable more sophisticated models within the same power envelope
- **Discrete tokens + Mamba:** The combination of discrete speech representations with SSM processing is a novel architectural direction — tokens enable compression/abstraction while Mamba provides efficient sequential modeling
- **Subjective CI user validation:** Moves beyond proxy metrics to actual end-user evaluation, providing stronger evidence for clinical relevance
- Connects to the broader SSM trend in hearing AI (see Michigan CIM-SSM work, Applied Brain Research TSP1)

## Architecture Details

- Speech tokenizer converts waveform to discrete token sequence
- Mamba backbone processes token sequence with selective state space mechanism
- Token decoder reconstructs enhanced speech from processed tokens
- Selective gating allows input-dependent information retention (vs fixed S4 dynamics)
- Linear recurrence enables streaming inference with fixed memory footprint
