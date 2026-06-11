---
title: "HALO: Half-Frame-Rate Adaptive Learnable Operator for Lightweight STFT-Based Speech Enhancement"
type: source
source_type: paper
date_published: 2026-06-10
date_ingested: 2026-06-11
authors: [Jiadong Zhao, Dahan Wang, Yu Sun, et al.]
identifier: arXiv:2606.12328
url: https://arxiv.org/abs/2606.12328
venue: arXiv (eess.AS)
tags: [speech-enhancement, lightweight, stft, dynamic-convolution, on-device, hearing-aid-applicable]
---

# HALO: Half-Frame-Rate Adaptive Learnable Operator

## Bibliographic
- **Authors:** Jiadong Zhao, Dahan Wang, Yu Sun, and five co-authors
- **Venue:** arXiv eess.AS, submitted 10 Jun 2026
- **ID:** arXiv:2606.12328
- **URL:** https://arxiv.org/abs/2606.12328

## What
HALO is a drop-in module for STFT-based speech enhancement networks that halves the internal frame rate via adaptive dynamic-convolution-based rate reduction, then learns a restoration step back to the full frame rate at the output. The STFT analysis/synthesis is left untouched. The freed compute budget is reinvested as wider channels in the SE backbone. Evaluated on DNS3 against multiple lightweight SE baselines; reports consistent quality gains at the same FLOP budget.

## Why It Matters
STFT-based SE backbones for hearing aids and hearables are budget-bound at the frame rate the analysis window dictates, even when most of that frame-by-frame activity is redundant (high inter-frame correlation under overlap-add). HALO is the first general-purpose plug-in that targets this specific redundancy without touching the STFT pipeline that downstream HA-DSP stages assume. The shape of the win — same FLOPs, better quality — is exactly what the embedded HA-chip integrators care about.

Pairs naturally with:
- DBHN-Net (arXiv 2606.05911) — orthogonal: HALO trims frame rate, DBHN-Net trims branch cost.
- FPGA SuDoRM-RF++ on Kria KV260 (arXiv 2606.04221) — same compute-budget framing on real silicon.

## Context
- Part of the June 2026 wave of lightweight-SE-for-hearing-applicable hardware papers.
- One-day before HLAA 2026 Friday Research Symposium on AI in hearing health — useful illustration of the "table stakes are getting cheaper" pattern.

## Used In
- [[wiki/concepts/speech-enhancement-neural-networks.md]]
- [[wiki/concepts/on-device-ml-hearing-aids.md]]
- [[wiki/concepts/model-compression.md]]
- [[wiki/concepts/dnn-architectures-hearing-aids.md]]
