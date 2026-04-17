---
title: Small Language Models for Edge AI
type: concept
created: 2026-04-15
updated: 2026-04-17
sources: [small-language-models-edge-2026.md, qwen3-6-35b-a3b-open-source-april-2026.md]
related: [on-device-ml-hearing-aids.md, large-sensor-models.md]
tags: [slm, edge-ai, tinyml, on-device, efficiency, mixture-of-experts, open-source]
---

# Small Language Models for Edge AI

Small Language Models (SLMs) are compact, task-specific neural networks designed to run on resource-constrained devices. They represent the practical path for AI in hearing aids and other wearables.

## Why Small Beats Big for Hearing Aids

| Constraint | Implication |
|-----------|-------------|
| Battery < fingernail size | Energy per inference must be minimal |
| 16,000+ samples/sec | Real-time processing, no batching |
| No cloud connectivity | All inference on-device |
| < 10ms latency | User perceives delay above this threshold |
| Chip area ~5mm² | Model must fit in tiny memory footprint |

## Notable Small Models (2026)
- **SmolLM2** (135M params) — Hugging Face, strong performance at fraction of compute
- **Gemma 3** (270M params) — Google's efficient small model family
- **Phi-3 Mini** (3.8B) — Microsoft, too large for hearing aids but relevant for mobile audiology apps
- **Qwen3.6-35B-A3B** (35B total / 3B active, April 2026) — Alibaba; mixture-of-experts architecture runs on laptop, beats frontier models on some tasks. The MoE paradigm (large model, sparse activation) is conceptually relevant to hearing aids: train a large model, deploy only relevant expert sub-networks per acoustic scene
- **Custom DSP nets** — Manufacturer-specific models, often < 1M parameters, running on dedicated audio DSPs

## Gartner Prediction
By 2027, organizations will use small, task-specific AI models 3x more than general-purpose LLMs. This is already reality in hearing aids — the industry has been doing "SLM" since before the term existed.

## Techniques for Making Models Small
- Knowledge distillation (train small student from large teacher)
- Quantization (INT8, INT4, binary in extreme cases)
- Pruning (remove unnecessary weights)
- Neural architecture search (NAS) for efficient topologies
- Task-specific training vs. general-purpose
- **Mixture-of-Experts (MoE)** — Train a large model with many expert sub-networks, activate only a subset per input. Qwen3.6-35B-A3B (35B total params, 3B active) demonstrates this at scale. For hearing aids, MoE could enable scene-specific expert networks (restaurant expert, music expert, quiet expert) while keeping active compute within chip budgets

## Open-Source Trajectory
The open-source model ecosystem (Qwen, Llama, Gemma, SmolLM) is converging toward efficient models that could serve as teacher models for hearing-specific distillation. Qwen3.6 running on a laptop (April 2026) is still ~1000x too large for hearing aid chips, but the compression trajectory (175B GPT-3 in 2020 to 3B active in 2026) suggests hearing-aid-scale foundation models within the decade.

## Related Pages
- [[on-device-ml-hearing-aids]] — The deployment environment for SLMs in hearing
- [[large-sensor-models]] — LSMs must be distilled to SLM-scale for wearable deployment
