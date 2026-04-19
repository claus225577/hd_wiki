---
title: Model Compression for Hearing AI
type: concept
created: 2026-04-18
updated: 2026-04-18
sources: [google-turboquant-iclr-2026.md]
related: [small-language-models-edge-ai.md, on-device-ml-hearing-aids.md, dnn-architectures-hearing-aids.md, ../comparisons/on-device-vs-cloud-ml.md, ../entities/google-research.md]
tags: [quantization, compression, pruning, distillation, edge-ai, efficiency]
---

# Model Compression for Hearing AI

Techniques for reducing model size, memory footprint, and compute requirements to enable deployment on resource-constrained hearing devices. Model compression is the critical bridge between large, accurate models trained in the cloud and the tiny, efficient models that must run on hearing aid chips.

## Why Compression Matters for Hearing Aids

| Resource | Typical Hearing Aid Budget | Cloud Training Budget |
|----------|--------------------------|----------------------|
| Memory | 256KB–2MB SRAM | Hundreds of GB |
| Power | < 1mW for ML block | Kilowatts |
| Compute | < 10 GOps/sec | Trillions of Ops/sec |
| Latency | < 10ms (1ms target) | Seconds acceptable |

The gap between training and deployment environments is ~6 orders of magnitude. Compression techniques bridge this gap.

## Core Techniques

### Quantization
Reducing the numerical precision of model weights and activations:
- **INT8** — 8-bit integer; standard for many edge deployments, ~4x memory reduction from FP32
- **INT4** — 4-bit; used in aggressive compression, some accuracy loss
- **3-bit** — Frontier compression; Google's TurboQuant (ICLR 2026) achieves 3-bit quantization of KV cache with zero accuracy loss
- **Binary / ternary** — Extreme cases for the smallest models; significant accuracy tradeoffs
- **Post-training quantization (PTQ)** — Applied after training, no retraining needed (e.g., TurboQuant)
- **Quantization-aware training (QAT)** — Model trained with quantization in the loop; better accuracy but requires full retraining

### Knowledge Distillation
Training a small "student" model to mimic a large "teacher" model:
- Teacher: large Transformer (SepFormer, etc.) with state-of-the-art accuracy
- Student: compact CRN or CNN fitting hearing aid constraints
- The student learns the teacher's soft outputs, not just hard labels — captures nuance
- Widely used in hearing aid DNN development (see [[dnn-architectures-hearing-aids]])

### Pruning
Removing unnecessary weights or structures from a trained model:
- **Unstructured pruning** — Zero out individual weights; requires sparse hardware support
- **Structured pruning** — Remove entire channels/layers; hardware-friendly but coarser
- Can achieve 50-90% sparsity with minimal accuracy loss on speech enhancement tasks

### Neural Architecture Search (NAS)
Automated search for Pareto-optimal architectures:
- Defines a search space of possible architectures
- Optimizes for multiple objectives: accuracy, latency, power, model size
- Produces architectures that humans would not design intuitively
- Used by major hearing aid manufacturers to find optimal CRN configurations

## Frontier: Google TurboQuant (ICLR 2026)

Google's TurboQuant represents a significant advance in training-free compression:
- **6x KV cache compression** via 3-bit quantization
- **Zero accuracy loss** across multiple benchmarks (LongBench, Needle-in-a-Haystack, ZeroSCROLLS, RULER, L-Eval)
- **No retraining required** — critical for production deployment workflows
- Uses **PolarQuant** (for key vectors) and **QJL** (Quantized Johnson-Lindenstrauss, for value vectors)
- Tested on Gemma and Mistral model families
- **Hearing aid relevance:** While TurboQuant targets LLM KV caches (much larger than hearing aid models), the zero-accuracy-loss-at-3-bit result pushes the theoretical floor for quantization. If similar techniques can be applied to audio DNNs, hearing aid models could fit more parameters within fixed memory budgets.

## Compression Pipeline for Hearing Aids

A typical hearing aid model development pipeline applies multiple compression techniques in sequence:

1. **Train large teacher model** in the cloud (Transformer-based, millions of parameters)
2. **Knowledge distillation** into compact CRN architecture (< 1M parameters)
3. **Pruning** to remove redundant weights (50-80% sparsity)
4. **Quantization** to INT8 or INT4 for deployment
5. **NAS** may be used at step 2 to find the optimal student architecture

Each step trades some accuracy for deployment efficiency. The art is in sequencing and tuning these steps to minimize cumulative accuracy loss.

## Related Pages
- [[small-language-models-edge-ai]] — The model paradigm that benefits from compression
- [[on-device-ml-hearing-aids]] — The deployment target for compressed models
- [[dnn-architectures-hearing-aids]] — Architectures being compressed (CRN, SepFormer distillation)
- [[on-device-vs-cloud-ml]] — The training-deployment gap that compression bridges
- [[google-research]] — TurboQuant and other Google contributions

## Sources
- [Google TurboQuant (ICLR 2026)](../../sources/google-turboquant-iclr-2026.md) — 6x KV cache compression, 3-bit quantization, zero accuracy loss
