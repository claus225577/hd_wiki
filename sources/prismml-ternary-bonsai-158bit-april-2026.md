---
title: "PrismML Ternary Bonsai: 1.58-bit Language Models"
url: https://prismml.com/news/ternary-bonsai
date: 2026-04-16
type: news
tags: [model-compression, ternary, quantization, edge-ai, on-device, mlx, apple-silicon]
---

# PrismML Ternary Bonsai — 1.58-bit Models

## Key Facts
- PrismML released **Ternary Bonsai**, a family of 1.58-bit language models
- Model sizes: **8B, 4B, 1.7B parameters**
- Uses **ternary weights: {-1, 0, +1}** — each weight encoded in ~1.58 bits
- 8B model: **75.5 average benchmark score** at only **1.75 GB memory**
- This is **9x smaller** than the equivalent 16-bit model
- Runs at **82 tokens/sec on M4 Pro** (Apple Silicon)
- Runs on **iPhone via MLX** (Apple's ML framework)

## Technical Details
- Ternary quantization: weights restricted to three values {-1, 0, +1}
- Eliminates multiplication entirely — inference becomes additions and subtractions only
- 1.58 bits per weight (log2(3) = 1.585 bits)
- Maintains competitive benchmark performance despite extreme compression
- Hardware-friendly: ternary operations map efficiently to simple logic gates

## Hearing Aid Relevance
- **Same efficiency constraints:** Hearing aid chips face identical pressure — minimize memory, eliminate multiplications, maximize throughput per milliwatt
- **Ternary arithmetic on hearing aid NPUs:** If hearing aid chip designers adopt ternary-native compute units, DNN inference could be dramatically more efficient
- **Memory reduction:** 9x memory reduction means a model that currently requires 2MB SRAM could potentially fit in ~220KB — within hearing aid chip budgets
- **No-multiply inference:** Removing multiplications from the critical path reduces power consumption (multipliers are the most power-hungry ALU components)
- **Apple Silicon pipeline:** MLX on iPhone demonstrates the Apple ecosystem path — same company making AirPods Pro hearing aids is also optimizing for ternary inference
- Complements Google TurboQuant (3-bit KV cache) — Ternary Bonsai goes further to 1.58-bit weights

## Benchmark Context
- 8B model at 1.75 GB vs. typical 8B at ~16 GB (FP16) or ~4 GB (INT4)
- 75.5 avg benchmark is competitive with many INT8 quantized models at 4-8x the memory
- 82 tok/sec on M4 Pro is practical for real-time applications
