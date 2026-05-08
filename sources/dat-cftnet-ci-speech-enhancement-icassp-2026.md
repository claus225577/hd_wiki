---
title: "DAT-CFTNet: Attention-Based Dual-Path RNN for CI Speech Enhancement"
type: paper
date: 2026-04-08
url: https://arxiv.org/abs/2604.06744
tags: [speech-enhancement, cochlear-implant, dual-path-rnn, attention, icassp-2026, musical-artifacts]
---

# DAT-CFTNet: Attention-Based Dual-Path RNN for CI Speech Enhancement

**Authors:** Mamun & Hansen
**Venue:** ICASSP 2026
**arXiv:** 2604.06744 (April 8, 2026)

## Key Findings

- Proposes DAT-CFTNet: an attention-based dual-path RNN architecture specifically designed for cochlear implant speech enhancement
- **Outperforms CFTNet and DCCRN** — two established baselines for real-time speech enhancement
- **Eliminates musical artifacts** — a long-standing problem in CI speech enhancement where spectral subtraction/masking creates tonal remnants that sound unnatural through CI electrode stimulation
- Dual-path architecture processes both intra-chunk (local) and inter-chunk (global) patterns, improving temporal modeling
- Attention mechanism enables the network to focus on speech-relevant time-frequency regions

## Significance for Hearing AI

- Advances the CI-specific speech enhancement pipeline beyond generic noise reduction
- Musical artifact elimination is particularly important for CI users because:
  - CI users have limited spectral resolution (~20 channels vs ~3,500 in normal hearing)
  - Artifacts that are barely noticeable to normal-hearing listeners can be highly disruptive through CI processing
  - Prior approaches (CFTNet, DCCRN) traded noise reduction quality against artifact generation
- Validates dual-path RNN + attention as a viable architecture for CI-constrained speech enhancement
- ICASSP 2026 presentation signals growing research attention to CI-specific DNN design

## Architecture Details

- Dual-path structure: segments input into chunks, processes intra-chunk and inter-chunk paths separately
- Attention mechanism applied to capture long-range dependencies across chunks
- Builds on CFTNet (Complex Frequency-Time Network) with architectural improvements
- Targets real-time operation for potential deployment in CI speech processors
