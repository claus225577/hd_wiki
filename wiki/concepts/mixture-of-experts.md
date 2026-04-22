---
title: Mixture of Experts (MoE)
type: concept
created: 2026-04-20
updated: 2026-04-21
sources: [qwen3-6-35b-a3b-open-source-april-2026.md]
related: [small-language-models-edge-ai.md, on-device-ml-hearing-aids.md, model-compression.md, dnn-architectures-hearing-aids.md, hearing-aid-chip-architectures.md]
tags: [mixture-of-experts, moe, sparse-models, edge-ai, architecture, efficiency]
---

# Mixture of Experts (MoE)

Mixture of Experts is a neural network architecture where a large model is divided into specialized sub-networks ("experts"), and a gating mechanism routes each input to only a small subset of experts. This decouples total model capacity from inference cost.

## How It Works

1. **Expert networks:** Multiple parallel sub-networks, each specializing in different input patterns
2. **Gating/router:** A lightweight network that examines the input and selects which experts to activate
3. **Sparse activation:** Only a fraction of the total parameters are used per inference — e.g., 3B active out of 35B total
4. **Training:** All experts are trained jointly; the router learns which expert handles which input type

## Key Example: Qwen3.6-35B-A3B (April 2026)

- **35B total parameters, 3B active per inference** — ~10x sparsity ratio
- **~21GB quantized** — runs on a MacBook Pro M5 via LM Studio
- Competes with frontier models (Anthropic Claude Opus 4.6) on benchmarks
- Demonstrates that MoE enables frontier-quality reasoning at consumer hardware scale
- Open-source (Alibaba) — available for fine-tuning and research

## Why MoE Matters for Hearing Aid AI

The MoE paradigm maps naturally onto the hearing aid use case:

### Scene-Specific Expert Networks
Hearing aids already classify acoustic scenes (restaurant, quiet, music, outdoors, conversation). MoE formalizes this:
- **Restaurant expert:** Optimized for multi-talker speech separation with background noise
- **Music expert:** Optimized for preserving dynamic range and tonal quality
- **Quiet expert:** Optimized for amplification with minimal processing artifacts
- **Wind expert:** Specialized wind noise detection and suppression
- **Classroom expert:** Optimized for distant speech in reverberant environments

The gating network maps to the existing scene classifier — instead of switching "programs," the device routes audio through the appropriate expert sub-network.

### Capacity vs. Compute Tradeoff
- Train a large model with many experts (in the cloud, no power constraints)
- Deploy only the active expert subset on the hearing aid chip
- Total knowledge capacity of the model >> active compute per inference
- Fits the hearing aid constraint: tiny power budget, but needs to handle diverse scenarios

### Potential Deployment Approaches
1. **Full MoE on-chip:** All experts stored in flash, router selects per-frame — requires enough storage for all experts
2. **Expert selection at fitting:** Audiologist selects relevant experts based on patient lifestyle; unused experts pruned
3. **Dynamic expert download:** Cloud-stored experts downloaded to hearing aid based on learned usage patterns
4. **Distilled MoE:** Each expert distilled to an even smaller student network for on-chip deployment

## Current Gap: MoE at Hearing Aid Scale

| Level | Parameters | Hardware | Status |
|-------|-----------|----------|--------|
| Frontier MoE (Qwen3.6) | 35B total / 3B active | Laptop (~21GB) | Available now |
| Mobile MoE | ~1B total / 100M active | Smartphone | Emerging |
| Wearable MoE | ~10M total / 1M active | Hearing aid chip | Research stage |
| Current HA DNNs | <1M total / <1M active | Hearing aid chip | Deployed |

The compression trajectory (175B GPT-3 in 2020 to 3B active MoE in 2026) suggests hearing-aid-scale MoE models are plausible within the decade.

## Relationship to Other Compression Techniques

MoE is complementary to, not a replacement for, other model compression approaches:
- **Ternary quantization** (1.58-bit) — PrismML Ternary Bonsai (April 2026) achieves {-1, 0, +1} weights at 9x memory reduction. Applied to MoE experts, a ternary MoE model could have massive total capacity with each active expert at minimal memory cost
- **Quantization** (INT8/INT4) can be applied to each expert independently
- **Knowledge distillation** can compress individual experts from large teachers
- **Pruning** can thin each expert further
- A pipeline of MoE + quantization + distillation could compound the efficiency gains

## Open Questions

- What is the minimum useful number of experts for hearing aid acoustic scenes?
- Can the gating network be merged with existing scene classifiers to avoid additional compute overhead?
- Is per-frame expert switching fast enough for real-time audio (<10ms latency)?
- How should experts be trained — on scene-labeled hearing aid data or on general audio with emergent specialization?

## Related Pages
- [[small-language-models-edge-ai]] — SLMs as the deployment target; MoE as architecture for efficient SLMs
- [[on-device-ml-hearing-aids]] — The deployment environment and constraints
- [[model-compression]] — Complementary techniques (quantization, distillation, pruning)
- [[dnn-architectures-hearing-aids]] — Current DNN architectures that MoE could augment
- [[hearing-aid-chip-architectures]] — Hardware that would need to support MoE routing

## Sources
- [Qwen3.6-35B-A3B Open-Source Release](../../sources/qwen3-6-35b-a3b-open-source-april-2026.md) — Key MoE example demonstrating frontier performance at consumer hardware scale
