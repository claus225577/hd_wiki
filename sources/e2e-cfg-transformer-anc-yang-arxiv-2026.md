---
title: "Transformer-based End-to-End Control Filter Generation for Active Noise Control"
authors: [Ziyi Yang, Zhengding Luo, Yisong Zou, Boxiang Wang, Qirui Huang, Woon-Seng Gan]
date: 2026-05-01
arxiv_id: "2605.00494"
url: https://arxiv.org/abs/2605.00494
type: research-paper
tags: [active-noise-control, transformer, unsupervised-learning, anc, feedback-cancellation, hearables, hearing-aids]
---

# E2E-CFG: Transformer End-to-End Control-Filter Generation for ANC (Yang et al., 2026)

## Key Extraction

- **Problem addressed:** Generative Fixed-Filter ANC (GFANC) decomposes the control filter into sub-filters whose weights are predicted, then reconstructed. This decomposition–reconstruction pipeline introduces error accumulation and limits adaptability.
- **Proposed method (E2E-CFG):** A transformer that **directly generates the time-domain ANC control filter end-to-end**, trained **unsupervised** using accumulated error signals as the objective in a fully differentiable loop.
- **Reported result:** Better noise reduction and broader adaptability across noise types than GFANC, validated on simulations with real-recorded noise.

## Architectural Notes

- Unsupervised training removes the dependence on labeled (noise → ideal-filter) pairs that supervised ANC ML approaches typically require.
- Attention is used to capture both global statistics and dynamic structure of the noise field — relevant for non-stationary, multi-source environments (street, café, transit).
- The framework is structurally compatible with on-device deployment if the transformer is compressed (linear-attention, KV-cache pruning, etc.).

## Relevance to Hearing + AI

- **Direct hearing-device implication:** Adaptive feedback cancellation, occlusion compensation, and active in-canal noise cancellation in hearables / open-fit hearing aids are all members of the ANC family. An unsupervised end-to-end formulation that generates control filters from running error is portable to those problems.
- **Pairs naturally with SOTA SE pipelines:** ANC handles the physical-acoustic suppression path, SE handles the post-mic enhancement path. End-to-end-learned ANC complements DNN-SE rather than competing with it.
- **Watch for:** Latency budgets. Hearing-aid ANC needs sub-millisecond control loops at the analog/digital boundary — transformers will have to be aggressively distilled or replaced with linear/state-space surrogates to fit.

## Open Questions

- What is the inference latency on commodity hearing-aid SoCs?
- Does the unsupervised objective generalize to closed-loop instability scenarios (acoustic feedback in vented fits)?
- How does it compare to state-space-model ANC variants (Mamba, S5) which offer linear-time inference?
