---
title: Model Compression for Hearing AI
type: concept
created: 2026-04-18
updated: 2026-04-22
sources: [google-turboquant-iclr-2026.md, prismml-ternary-bonsai-158bit-april-2026.md, wireless-hearables-programmable-speech-ai-accelerators-arxiv-2025.md, aizip-tiny-ai-hearing-devices-2026.md, michigan-compute-in-memory-rram-ssm-nature-2026.md, open-source-speech-ai-edge-native-april-2026.md, adobe-speechmatics-on-device-stt-april-2026.md]
related: [small-language-models-edge-ai.md, on-device-ml-hearing-aids.md, dnn-architectures-hearing-aids.md, ../comparisons/on-device-vs-cloud-ml.md, ../entities/google-research.md, mixture-of-experts.md, compute-in-memory.md, state-space-models.md]
tags: [quantization, compression, pruning, distillation, edge-ai, efficiency, compute-in-memory]
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
- **Ternary (1.58-bit)** — Weights restricted to {-1, 0, +1}; PrismML Ternary Bonsai (April 2026) achieves 75.5 avg benchmark at 1.75 GB for an 8B model — 9x smaller than FP16. Eliminates multiplications entirely (additions/subtractions only). See below.
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

## Frontier: PrismML Ternary Bonsai (April 2026)

PrismML released Ternary Bonsai, a family of **1.58-bit** language models using ternary weights {-1, 0, +1}:
- **Model family:** 8B, 4B, 1.7B parameter variants
- **8B model:** 75.5 avg benchmark at only **1.75 GB memory** — 9x smaller than 16-bit equivalent
- **82 tokens/sec on M4 Pro** (Apple Silicon); runs on **iPhone via MLX**
- **No multiplications:** Ternary arithmetic reduces inference to additions and subtractions only — multipliers are the most power-hungry ALU components
- **Hearing aid relevance:** The constraints Ternary Bonsai addresses — minimize memory, eliminate multiplications, maximize throughput per watt — are identical to hearing aid chip constraints. If hearing aid NPUs adopted ternary-native compute units:
  - A model currently requiring 2 MB SRAM could fit in ~220 KB
  - Power consumption drops significantly by eliminating multiplier circuits
  - Inference throughput increases with simpler arithmetic operations
- **Apple Silicon pipeline:** The fact that Ternary Bonsai runs on iPhone via MLX (Apple's ML framework) is notable — the same company making AirPods Pro hearing aids is also optimizing for extreme quantization
- Complements TurboQuant (3-bit KV cache) — Ternary Bonsai goes further to 1.58-bit weights, suggesting a convergent trend toward sub-2-bit inference

## Compression Pipeline for Hearing Aids

A typical hearing aid model development pipeline applies multiple compression techniques in sequence:

1. **Train large teacher model** in the cloud (Transformer-based, millions of parameters)
2. **Knowledge distillation** into compact CRN architecture (< 1M parameters)
3. **Pruning** to remove redundant weights (50-80% sparsity)
4. **Quantization** to INT8 or INT4 for deployment
5. **NAS** may be used at step 2 to find the optimal student architecture

Each step trades some accuracy for deployment efficiency. The art is in sequencing and tuning these steps to minimize cumulative accuracy loss.

## The CIM Alternative: Don't Compress — Redesign the Hardware

Compute-in-memory (CIM) offers a fundamentally different approach to the deployment problem (see [[compute-in-memory]]):

**Compression paradigm:** Make the model smaller to fit the hardware.
**CIM paradigm:** Redesign the hardware so the computation happens where the data lives.

The University of Michigan (Nature Communications 2026) demonstrated SSMs running on RRAM crossbar arrays with accuracy within 4.6 bits of ideal — achieving real-time inference by eliminating the memory bandwidth bottleneck rather than shrinking the model. This does not make compression obsolete (a CIM chip still benefits from smaller models), but it shifts the optimization target from "how small can we make the model" to "how efficiently can the hardware execute computation."

For hearing aids, the two approaches are complementary:
- **Short-term (2026-2028):** Compression remains essential — current chips are digital, and models must be compressed to fit
- **Medium-term (2028+):** CIM hardware could relax compression requirements, enabling larger/more accurate models within the same power budget
- **Distillation remains valuable regardless:** Even with CIM, distilling knowledge from large teacher models into compact student models captures architectural efficiency, not just numerical compression

### Open-Source Speech Models as Distillation Teachers (April 2026)

The open-source speech model ecosystem now provides production-quality teacher models for hearing aid distillation:
- **Distil-Whisper** demonstrates **6.3x speedup** over Whisper Large V3 via knowledge distillation — a direct proof point that aggressive distillation preserves speech quality
- **Qwen3-ASR** (0.6B and 1.7B params, 52 languages) provides multilingual teacher models at scales amenable to further distillation
- **Mistral Voxtral 3B** (Apache 2.0) offers a permissively-licensed edge-native speech model as a distillation source
- These models are designed for edge deployment from inception, making them better distillation sources than cloud-first models squeezed down

## Related Pages
- [[small-language-models-edge-ai]] — The model paradigm that benefits from compression
- [[on-device-ml-hearing-aids]] — The deployment target for compressed models
- [[dnn-architectures-hearing-aids]] — Architectures being compressed (CRN, SepFormer distillation)
- [[on-device-vs-cloud-ml]] — The training-deployment gap that compression bridges
- [[google-research]] — TurboQuant and other Google contributions
- [[compute-in-memory]] — The alternative paradigm: redesign hardware instead of compressing models
- [[state-space-models]] — SSMs as efficient model architecture reducing compression needs

## Sources
- [Google TurboQuant (ICLR 2026)](../../sources/google-turboquant-iclr-2026.md) — 6x KV cache compression, 3-bit quantization, zero accuracy loss
- [PrismML Ternary Bonsai (April 2026)](../../sources/prismml-ternary-bonsai-158bit-april-2026.md) — 1.58-bit ternary models, 9x memory reduction, no-multiply inference
- [Michigan CIM RRAM + SSM (Nature Communications 2026)](../../sources/michigan-compute-in-memory-rram-ssm-nature-2026.md) — CIM alternative to compression
- [Open-Source Speech AI Edge-Native (April 2026)](../../sources/open-source-speech-ai-edge-native-april-2026.md) — Distil-Whisper, Voxtral, Qwen3-ASR/TTS as distillation sources
