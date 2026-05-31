---
title: "CFMDCTCodec: A Low-Bitrate Neural Speech Codec with Noise-Prior-aware Conditional Flow Matching for MDCT-Spectral Enhancement"
authors: Hui-Peng Du, Yang Ai, Xiao-Hang Jiang, Yuan Tian, Zhen-Hua Ling
venue: arXiv (eess.AS); accepted at IEEE/ACM Transactions on Audio, Speech, and Language Processing (TASLP)
arxiv_id: 2605.26812
published: 2026-05-26
ingested: 2026-05-28
url: https://arxiv.org/abs/2605.26812
type: paper
tags: [neural-speech-codec, mdct, conditional-flow-matching, low-bitrate, on-device, auracast, ble-audio]
---

# CFMDCTCodec — Low-Bitrate Neural Speech Codec with CFM-based MDCT-Spectral Enhancement

## Headline

A neural speech codec that operates **entirely in the MDCT (modified discrete cosine transform) domain**, integrating a lightweight encoder–quantizer–decoder with a noise-prior-aware **conditional-flow-matching (CFM)** enhancer for MDCT-spectral refinement. Achieves competitive perceptual quality at **0.65 kbps** with significantly fewer parameters than large-scale codec baselines.

## Architecture

- **Base codec module:** lightweight MDCT encoder–quantizer–decoder. Compactly discretizes the MDCT spectrum extracted from the input speech and produces an initial **coarse reconstruction**.
- **CFM-based enhancer:** restores fine-grained spectral detail by integrating a **conditional MDCT velocity-field filter** with an ODE solver. Noise-prior-aware design conditions the velocity field on noisy prior information.
- **Training strategy:** unified **non-adversarial** objective combining reconstruction + quantization + CFM losses. No discriminator → simpler training pipeline than GAN-based codec families.

## Results

- Outperforms competitive baselines in low-bitrate regimes (objective + subjective evaluations).
- Reference operating point: **0.65 kbps**.
- Approaches the perceptual quality of large-scale codecs with significantly fewer parameters → parameter-efficient frontier.

## Relevance to Hearing Aids

- **Auracast / BLE Audio bitrate budget:** Auracast broadcasts to hearing aids run on a constrained airtime budget. Sub-kbps codecs that preserve perceptual quality are the right operating point for low-power, multi-listener venue broadcast.
- **On-device decoding plausibility:** Small parameter counts make on-chip decoding viable for hearing-aid SoCs (Sirius, DEEPSONIC, etc.). The CFM enhancer is the most expensive component — whether the ODE solver can run within HA latency/MIPS budgets is the next open question.
- **Adjacency to SE pipelines:** MDCT-domain processing is already the substrate for many HA front-ends, so a codec in the same domain reduces representation conversion overhead in a streaming-aware pipeline.

## Open Questions

- Real-time inference cost of the CFM enhancer at HA-relevant block sizes — not reported in arxiv abstract; needs reading the full paper.
- Robustness to packet loss in Auracast broadcast scenarios.
- Whether the codec degrades gracefully for hearing-impaired listeners under HA amplification (post-codec amplification can expose quantization artifacts).

## Citation

Du, H.-P., Ai, Y., Jiang, X.-H., Tian, Y., Ling, Z.-H. (2026). *CFMDCTCodec: A Low-Bitrate Neural Speech Codec with Noise-Prior-aware Conditional Flow Matching for MDCT-Spectral Enhancement.* arXiv:2605.26812. Accepted at IEEE/ACM TASLP.
