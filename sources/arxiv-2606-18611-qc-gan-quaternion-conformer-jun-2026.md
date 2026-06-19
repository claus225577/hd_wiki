---
title: "QC-GAN — Parameter-Efficient Quaternion Conformer GAN for High-Fidelity Speech Enhancement (arXiv:2606.18611)"
type: source
source_type: arxiv-paper
date: 2026-06-17
authors: [Shogo Yamauchi, Hideaki Tamori, Makoto Sakai, Yosuke Yamano, Tohru Nitta]
arxiv_id: 2606.18611
url: https://arxiv.org/abs/2606.18611
ingested: 2026-06-18
tags: [speech-enhancement, quaternion-neural-networks, conformer, metricgan, parameter-efficiency, on-device-ai, hamilton-product, hearing-aid-silicon, gan]
---

# QC-GAN — A Parameter-Efficient Quaternion Conformer GAN for High-Fidelity Speech Enhancement

## Citation
Shogo Yamauchi, Hideaki Tamori, Makoto Sakai, Yosuke Yamano & Tohru Nitta — "QC-GAN: A Parameter-Efficient Quaternion Conformer GAN for High-Fidelity Speech Enhancement," arXiv:2606.18611 (cs.SD / eess.AS), 17 June 2026.

## Core Mechanism
- **Generator:** Standard real-valued conformer replaced with a **Quaternion Conformer**. The Hamilton product encodes magnitude + phase information via structured weight sharing — one quaternion-valued layer parametrically substitutes for ~4 real-valued layers, with algebraic constraints baked in rather than learned. Phase, which standard real-valued SE typically discards or under-uses, is preserved by construction.
- **Training paradigm:** **MetricGAN** discriminator trained against perceptual metrics (PESQ-aligned objectives), rather than vanilla GAN against waveform/spectrogram MSE.
- **Pipeline:** Standard SE input/output spectrogram contract — no exotic representation; STFT-compatible downstream.

## Headline Numbers
| Variant | Parameters | PESQ (VoiceBank+DEMAND) | Notes |
|---------|-----------|--------------------------|-------|
| QC-GAN (full) | 0.89 M | **3.48** | Comparable to SOTA at less than half their size |
| QC-GAN (compact) | **0.035 M (35K)** | **3.23** | First arXiv result this year living natively inside hearing-aid memory budget |

- Validated on **DNS-Challenge 3** for real-world generalization.
- Compact variant trades ~0.25 PESQ for a **25× parameter cut**.

## Why This Matters for Hearing Aids
1. **35K parameters** is genuinely hearing-aid-silicon-scale. Typical HA DSP budgets are 256KB-2MB SRAM; a 35K-parameter model in INT8 fits in <40KB — leaves room for the rest of the pipeline (beamformer, AGC, classifier).
2. **Phase preservation by construction.** Quaternion algebra encodes 4-channel structure with one Hamilton-product operation; for stereo-mic hearing aids, the complex-spectrogram pair (L mag, L phase, R mag, R phase) maps natively onto a quaternion. The hand-crafted dual-stream architectures the field has been using become unnecessary.
3. **MetricGAN training.** Aligns optimization with perceptual metrics rather than spectrogram MSE — closer to what listeners (and HASPI/HASQI evaluations) actually score.

## Position in the June 2026 On-Chip Lever Cluster
QC-GAN is the **fifth orthogonal on-chip lever** in the cluster catalogued in [[../wiki/syntheses/on-chip-hearing-ai-levers-june-2026]]:

| Lever | Paper | Axis |
|-------|-------|------|
| 1. Memory bandwidth | Olalere FPGA (arXiv:2606.04221, Jun 4) | Bytes per inference |
| 2. SNN+ANN sparsity | DBHN-Net (arXiv:2606.05911, Jun 5) | Active units × time |
| 3. One-step inference | SB-RF (arXiv:2606.05575, Jun 4) | Forward passes per sample |
| 4. Frame-rate subsampling | HALO (arXiv:2606.12328, Jun 10) | Temporal samples processed |
| 5. **Quaternion weight sharing** | **QC-GAN (arXiv:2606.18611, Jun 17)** | **Parameters per layer via algebraic structure** |

The five levers are mutually compatible — a 2027 best-in-class hearing-aid SE model is likely a combination, not a single lever.

## Open / Unbuilt Pieces
- **No latency benchmark.** Paper reports parameter count but not on-chip end-to-end latency on a specific HA DSP — first team to land the FPGA / ARM Cortex-M55 benchmark closes the loop with Olalere.
- **No multi-channel reporting.** The compelling stereo-mic native quaternion use case is not directly evaluated.
- **No combination study.** Quaternion + half-frame-rate (HALO) or quaternion + one-step (SB-RF) — both are obvious next experiments, neither published.
- **Affiliation not specified in abstract.** Author names are Japanese; likely industrial / academic research lab in Japan, but the abstract does not name the institution.

## Relevance Links
- Direct: [[../wiki/concepts/speech-enhancement-neural-networks]]
- Direct: [[../wiki/concepts/model-compression]]
- Direct: [[../wiki/concepts/on-device-ml-hearing-aids]]
- Direct: [[../wiki/concepts/hearing-aid-chip-architectures]]
- Direct: [[../wiki/syntheses/on-chip-hearing-ai-levers-june-2026]]
- Adjacent: [[../wiki/concepts/tinyml-edge-ai]]
- Adjacent: [[../wiki/concepts/dnn-architectures-hearing-aids]]
