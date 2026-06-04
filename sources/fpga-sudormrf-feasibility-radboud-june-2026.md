---
title: "Feasibility of Time-Domain DNN-Based Speech Enhancement on Embedded FPGA for Hearing Aids"
url: https://arxiv.org/abs/2606.04221
date: 2026-06-04
type: paper
authors: Feyisayo Olalere, Umut Altin, Kiki van der Heijden, Marcel van Gerven
affiliations: Radboud University Donders Institute for Brain, Cognition and Behaviour (Nijmegen, NL); Mortimer B. Zuckerman Mind Brain Behavior Institute, Columbia University (USA)
arxiv_id: 2606.04221
tags: [fpga, embedded, on-chip, speech-enhancement, sudormrf, kria-kv260, data-movement-bottleneck, latency-budget, parameter-caching, donders, columbia-zuckerman]
---

# Feasibility of Time-Domain DNN-Based Speech Enhancement on Embedded FPGA for Hearing Aids

## Key Extractions

- arXiv 2606.04221, submitted 4 Jun 2026
- Authors: Olalere, Altin, van der Heijden, van Gerven (Radboud Donders; van der Heijden also Columbia Zuckerman Mind Brain Behavior Institute)
- Cross-lab note: Columbia Zuckerman is the same institute where Mesgarani published the first closed-loop human brain-controlled hearing-aid demonstration (Nat Neurosci, 11 May 2026, DOI 10.1038/s41593-026-02281-5)
- Hardware platform: AMD-Xilinx Kria KV260 (commercial embedded FPGA evaluation board)
- Architecture under test: SuDoRM-RF++ — lightweight DNN speech separation / enhancement
- Two tasks evaluated: denoising and speech separation, each at FP32 and 16-bit fixed-point

## Headline Numbers

- Denoising first-sample latency: **9.7 ms** (FP, 16-bit fixed-point) — **under** the 10 ms clinical threshold
- Speech separation first-sample latency: **16.0 ms** — **over** the threshold
- 16-bit fixed-point halves model memory footprint with no measurable degradation in objective speech quality
- First-sample latency **tracks with on-chip parameter caching**, not with arithmetic throughput

## Core Finding

> Data movement is the primary bottleneck, not compute.

The paper measures the gap between current on-chip DNN feasibility and clinical hearing-aid deployment, and locates that gap in memory hierarchy / parameter caching rather than in MAC count or operator efficiency.

## Relevance to Hearing + AI

- **Compute-story → memory-story.** For two years the on-chip-AI race has been framed as compute (Phonak DEEPSONIC, Sonova Sphere Infinio, Fortell ~235× custom AI chip per IJA May 2026, Tufts neuro-symbolic 100× efficiency Apr 2026). This paper is the first concrete published benchmark on an embedded eval-board that says: at a reasonable compute budget, the binding constraint shifts to memory bandwidth.
- **Architectural implication.** U-Net-on-spectrograms (and most current speech-enhancement publishing) is memory-hungry per sample. Streaming-friendly architectures (state-space models à la Mamba/Applied Brain Research, recurrent layers, single-pass causal transformers) are designed against different memory access patterns and may be a structurally better fit for embedded silicon than for academic benchmarks.
- **Compute-in-memory link.** Reinforces the April 2026 Michigan RRAM compute-in-memory direction (arXiv via U Michigan Nature Communications) — moving compute to where data lives — but at a different abstraction layer: classical von Neumann FPGA today, with the data-movement bottleneck *measured* rather than asserted.
- **Clinical-threshold framing.** 10 ms first-sample latency is the long-standing hearing-aid clinical bar (occlusion artifacts, audio-visual asynchrony, comb-filter effects with own-voice). The paper places denoising under that bar and speech separation above it — a defensible deployment threshold question.
- **Industry telemetry use.** Manufacturers benchmarking their own on-chip pipelines have rarely published raw latency / cache-hit numbers. A peer-reviewable third-party benchmark on a standard FPGA platform changes what teams can cite externally.
- **Pair with neural-decoding ceiling.** The same lab (Zuckerman, via van der Heijden's joint affiliation) is also publishing the highest-end neural-decoding work for hearing aids. Bracketing the problem from both the chip-latency floor and the brain-decoding ceiling is the right pair of constraints to optimize between.

## Cross-references
- SuDoRM-RF original paper: Tzinis et al., MLSP 2020
- AMD-Xilinx Kria KV260 product page: xilinx.com/products/som/kria/kv260-vision-starter-kit
- Mesgarani brain-controlled hearing aid (same Zuckerman institute): Nat Neurosci, 11 May 2026, DOI 10.1038/s41593-026-02281-5
- Adjacent compute-in-memory direction: U Michigan RRAM crossbar paper (Nature Communications, April 2026)
- Adjacent vertical-integration / chip-algorithm co-design: Fortell IJA paper (May 2026)
