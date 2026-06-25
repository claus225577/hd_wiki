---
title: "Neuromorphic Speech Enhancement with Dual-Branch Spiking Neural Networks (GSU-DBNet)"
type: source
source_type: arxiv-preprint
date_published: 2026-06-22
date_ingested: 2026-06-25
authors: [Taiyu Meng, Wenbin Jiang, Haoyi Zhang, Yuhan Zhou, Haibing Yin]
identifier: arXiv:2606.23761
url: https://arxiv.org/abs/2606.23761
venue: arXiv (eess.AS)
tags: [speech-enhancement, spiking-neural-network, snn, neuromorphic, gated-spiking-unit, gsu, dual-branch, on-device, edge-ai, hearing-aids]
---

# Neuromorphic Speech Enhancement with Dual-Branch Spiking Neural Networks (GSU-DBNet)

## Bibliographic
- **Authors:** Taiyu Meng, Wenbin Jiang, Haoyi Zhang, Yuhan Zhou, Haibing Yin
- **Posted:** 22 June 2026
- **Venue:** arXiv 2606.23761 (eess.AS)
- **URL:** https://arxiv.org/abs/2606.23761

## Problem
Existing spiking-neural-network (SNN) approaches to speech enhancement (SE) are bottlenecked by two limitations:
1. **Binary activations** are too coarse to reconstruct fine spectral structure.
2. **Architecture design** has lagged behind ANN-based SE — SNN models have not been able to compete with conformer / U-Net baselines on perceptual quality.

The result: SNNs have been the "energy-efficient on paper, behind on quality" option for over a decade, despite being the natural fit for power-constrained edge audio devices (including hearing aids).

## Contribution
**GSU-DBNet** — a dual-branch spiking neural network with a new primitive (Gated Spiking Unit, GSU):

- **Dual-branch architecture** simultaneously models **magnitude spectra** and **complex spectra** — addressing the long-standing magnitude-vs-complex trade-off in SE.
- **Gated Spiking Unit (GSU)** — a new SNN building block that introduces a learned gate over the spike output, raising the effective expressivity of the network without breaking event-driven sparsity.
- **Dual-path GSU module** exploits the GSU primitive along both **temporal** and **frequency** axes.

## Key Results
- **394K parameters** total — well inside the per-ear parameter budget of current hearing-aid SoCs.
- **PESQ 3.04** on speech enhancement.
- Uses **4.5%–10.6% of the parameter count** of representative ANN-based SE baselines while remaining competitive on quality.
- Outperforms prior SNN-based SE methods.

## Why It Matters for Hearing Aids
1. **Parameter budget alignment** — 394K params lands squarely in the realistic range for the next HA SoC generation (~1–2M total per ear). The SNN-for-HA argument moves from theoretical to architectural-review territory.
2. **Energy scaling** — Event-driven SNN inference on neuromorphic hardware is the only compute model whose energy *per active sample* scales with input sparsity. Speech is mostly silence; the energy savings compound.
3. **Two-axis exploitation** — The GSU's dual-path use along time *and* frequency parallels how production CRN architectures use 2D structure. SNN SE no longer requires throwing away inductive biases that ANN SE relies on.

## Adjacent / Related Work
- **DBHN-Net** (Fan et al., arXiv:2606.05911, 4 Jun 2026, accepted TPAMI) — hybrid SNN+ANN dual-branch SE running on standard hardware with 7.5× FLOP reduction. GSU-DBNet is the **pure-SNN** counterpart for neuromorphic substrates.
- **QC-GAN** (Yamauchi et al., arXiv:2606.18611, 17 Jun 2026) — algebraic weight-sharing via Hamilton product, 35K-param compact variant. Different axis (algebraic structure vs spike-timing) of the same parameter-efficiency push.
- **BASENet** (arXiv:2606.12662, Jun 2026) — band-adapted CRN at 0.83M params, 3.55 PESQ — the ANN incumbent that SNN approaches are now ~1 PESQ point behind at 2.1× fewer params.

## Open Questions
- **Neuromorphic substrate maturity** — Loihi 2 / SpiNNaker exist but no HA OEM ships neuromorphic silicon today. Does GSU-DBNet run usefully on the conventional MAC arrays in current HA chips, or does it require new silicon?
- **Latency** — Abstract does not report algorithmic latency. Hearing aids require sub-10 ms; SNN simulators often report slower wall-clock.
- **Power numbers** — Energy per inference not in abstract; the "energy efficient" claim needs a concrete number for a HA roadmap conversation.
