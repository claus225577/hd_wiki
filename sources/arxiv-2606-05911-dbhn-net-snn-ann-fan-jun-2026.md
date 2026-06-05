---
title: "DBHN-Net: Dual-Branch Hybrid Neural Network For Low-Complexity Monaural Speech Enhancement"
type: source
source_type: arxiv-preprint
date_published: 2026-06-04
date_ingested: 2026-06-05
authors: [Cunhang Fan, Enrui Liu, Jing Zhou, Jian Kang, Jie Li, Andong Li, Jian Zhou, Zhao Lv, Xuelong Li]
identifier: arXiv:2606.05911
url: https://arxiv.org/abs/2606.05911
venue: arXiv (eess.AS) / accepted at IEEE TPAMI
tags: [speech-enhancement, spiking-neural-network, snn, hybrid-architecture, low-complexity, on-device, monaural, edge-ai, tinyml]
---

# DBHN-Net: Dual-Branch Hybrid Neural Network for Low-Complexity Monaural Speech Enhancement

## Bibliographic
- **Authors:** Cunhang Fan, Enrui Liu, Jing Zhou, Jian Kang, Jie Li, Andong Li, Jian Zhou, Zhao Lv, Xuelong Li
- **Posted:** 4 June 2026
- **Venue:** arXiv 2606.05911 (eess.AS); **accepted at IEEE Transactions on Pattern Analysis and Machine Intelligence (TPAMI)**
- **URL:** https://arxiv.org/abs/2606.05911

## Problem
Monaural speech enhancement is dominated by ANN architectures (CRN, DCCRN, MP-SENet variants) that are accurate but expensive — too expensive for the < 1 mW envelope of a hearing-aid SoC. Spiking neural networks (SNNs) offer event-driven, low-power operation but lose information at the spike-encoding step, especially for fine-grained spectral structure.

## Contribution
**DBHN-Net** is a dual-branch architecture:
- **SNN branch** — reduces power consumption via event-driven sparse activations.
- **ANN branch** — addresses the information loss inherent to spike encoding.
- **Inter-branch fusion** modules transfer representations between the two paths, plus specialized feature-extraction modules.

The network is trained end-to-end and evaluated on three public SE datasets.

## Key Results
- **Average 7.5× reduction in computational complexity** vs strong ANN baselines.
- Performance maintained across three public datasets.
- Accepted at IEEE TPAMI — a notable venue for an SE paper that is fundamentally an architecture-efficiency contribution.

## Why It Matters
Hearing-aid SE has been stalled at the same trade-off for years: any architecture that approaches state-of-the-art quality is too power-hungry for the device, and any architecture that fits the device is well behind state-of-the-art quality. Hybrid SNN+ANN architectures are one of the few credible paths to compress the gap without an exotic chip (neuromorphic substrates such as Loihi, SpiNNaker) — DBHN-Net runs on standard hardware while harvesting most of the SNN energy advantage.

The TPAMI acceptance also signals that "low-complexity SE" is being taken seriously as an architecture-research direction rather than a deployment afterthought.

## Open Questions / Limitations
- "Computational complexity" reduction reported but exact FLOPs / parameter count on the hearing-aid envelope (< 1 mW, < 10 ms loop) not explicitly characterized here.
- SNN training remains finicky (surrogate gradients, time-step choice); reproducibility outside the authors' setup is an open question.
- Public datasets (VoiceBank-DEMAND etc.) are mismatched with real hearing-aid acoustic environments.

## Used In
- [[wiki/concepts/speech-enhancement-neural-networks.md]]
- [[wiki/concepts/dnn-architectures-hearing-aids.md]]
- [[wiki/concepts/tinyml-edge-ai.md]]
- [[wiki/concepts/on-device-ml-hearing-aids.md]]
