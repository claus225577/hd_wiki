---
title: "SB-RF: Schrödinger Bridge Rectified Flow for One-Step Robust Speech Enhancement"
type: source
source_type: arxiv-preprint
date_published: 2026-06-04
date_ingested: 2026-06-05
authors: [Caixia Lu, Xueyang Lv, Penglong Hu, Jiaming Xu]
identifier: arXiv:2606.05575
url: https://arxiv.org/abs/2606.05575
venue: arXiv (eess.AS)
tags: [speech-enhancement, generative-model, rectified-flow, schrodinger-bridge, optimal-transport, one-step-inference, low-snr, on-device]
---

# SB-RF: Schrödinger Bridge Rectified Flow for One-Step Robust Speech Enhancement

## Bibliographic
- **Authors:** Caixia Lu, Xueyang Lv, Penglong Hu, Jiaming Xu
- **Posted:** 4 June 2026
- **arXiv:** 2606.05575 (eess.AS)
- **URL:** https://arxiv.org/abs/2606.05575

## Problem
Diffusion- and flow-based generative speech-enhancement models deliver high perceptual quality but require many sampling steps at inference, making them unattractive for real-time / on-device use. Rectified flow shortens the trajectory but still suffers degradation under low-SNR conditions where the noisy prior is far from the clean target.

## Contribution
SB-RF combines **Rectified Flow** with **Schrödinger Bridge** theory to construct a conditional bridge between the clean speech distribution and the noisy speech distribution using **entropy-regularized optimal transport**. The bridge replaces the standard Gaussian prior of diffusion SE with a *data-conditional* prior anchored on the noisy observation, yielding a model that produces enhanced speech in **a single generation step**.

## Key Results
- Competitive performance on VoiceBank-DEMAND.
- Robust on a simulated low-SNR dataset where standard rectified-flow SE degrades.
- Single forward-pass inference — order-of-magnitude latency reduction vs multi-step diffusion baselines.

## Why It Matters
Generative SE has been the obvious next step for hearing-aid speech enhancement once compute permits it, but multi-step samplers are a non-starter for the < 10 ms loop budget. One-step generative SE that holds up at low SNR closes one of the larger gaps between the diffusion-SE literature and the hearing-aid deployment envelope. Also a useful data point for the [[probabilistic-generative-models-hearing-ai]] vs DNN-SE debate: SB-RF is generative *and* compact at inference time.

## Open Questions / Limitations
- Parameter count / FLOPs not reported in the abstract — "computational efficiency suitable for real-world applications" is asserted, not quantified for hearing-aid silicon.
- No on-device benchmark; VoiceBank-DEMAND is a clean offline corpus.
- Behavior under non-stationary noise (the actual hearing-aid case) not yet shown.

## Used In
- [[wiki/concepts/speech-enhancement-neural-networks.md]]
- [[wiki/concepts/probabilistic-generative-models-hearing-ai.md]]
- [[wiki/concepts/on-device-ml-hearing-aids.md]]
