---
title: Small Language Models for Edge AI
type: concept
created: 2026-04-15
updated: 2026-04-22
sources: [small-language-models-edge-2026.md, qwen3-6-35b-a3b-open-source-april-2026.md, google-turboquant-iclr-2026.md, prismml-ternary-bonsai-158bit-april-2026.md, open-source-speech-ai-edge-native-april-2026.md]
related: [on-device-ml-hearing-aids.md, large-sensor-models.md, model-compression.md, ../entities/google-research.md, mixture-of-experts.md, state-space-models.md]
tags: [slm, edge-ai, tinyml, on-device, efficiency, mixture-of-experts, open-source, speech-models]
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
- **Qwen3.6-35B-A3B** (35B total / 3B active, April 2026) — Alibaba; mixture-of-experts architecture, ~21GB quantized, runs on MacBook Pro M5 via LM Studio. Competes with frontier models (per Simon Willison: "Qwen beats Opus"). See [[mixture-of-experts]] for detailed MoE concept analysis and hearing aid implications
- **Custom DSP nets** — Manufacturer-specific models, often < 1M parameters, running on dedicated audio DSPs

## Gartner Prediction
By 2027, organizations will use small, task-specific AI models 3x more than general-purpose LLMs. This is already reality in hearing aids — the industry has been doing "SLM" since before the term existed.

## Techniques for Making Models Small
- Knowledge distillation (train small student from large teacher)
- Quantization (INT8, INT4, and now sub-2-bit)
  - **3-bit:** Google TurboQuant (ICLR 2026) achieves 3-bit KV cache quantization with zero accuracy loss via PolarQuant + QJL — no retraining needed
  - **1.58-bit (ternary):** PrismML Ternary Bonsai (April 2026) uses {-1, 0, +1} weights — 8B model at 1.75 GB (9x smaller than FP16), 82 tok/sec on M4 Pro, runs on iPhone via MLX. Eliminates multiplications entirely. See [[model-compression]].
- Pruning (remove unnecessary weights)
- Neural architecture search (NAS) for efficient topologies
- Task-specific training vs. general-purpose
- **Mixture-of-Experts (MoE)** — Train a large model with many expert sub-networks, activate only a subset per input. Qwen3.6-35B-A3B (35B total params, 3B active) demonstrates this at scale. For hearing aids, MoE could enable scene-specific expert networks (restaurant expert, music expert, quiet expert) while keeping active compute within chip budgets

## Open-Source Speech Models Going Edge-Native (April 2026)

The open-source ecosystem has reached a critical mass of production-quality **speech-specific** models designed for edge deployment:

| Model | Params | Languages | Key Feature | License |
|-------|--------|-----------|-------------|---------|
| **Mistral Voxtral 3B** | 3B | 9 | Edge-native speech model from frontier lab | Apache 2.0 |
| **Qwen3-ASR** | 0.6B / 1.7B | 52 | Timestamp prediction, multilingual | Open |
| **Qwen3-TTS** | — | — | Zero-shot voice cloning (3s reference), 97ms TTFA | Open |
| **Distil-Whisper** | — | — | 6.3x faster than Whisper Large V3 | Open |

**Why this matters for hearing AI:**
- **Distillation teachers:** These models are 0.6B-3B params — vastly smaller than LLMs but still ~1000x larger than hearing aid models. They serve as high-quality teacher models for knowledge distillation into hearing-aid-scale (<1M param) student models.
- **Distil-Whisper proof point:** 6.3x speedup via distillation with minimal quality loss validates the entire compress-and-deploy pipeline for speech.
- **Multilingual at sub-1B:** Qwen3-ASR covers 52 languages in a 0.6B model, suggesting multilingual hearing aid speech processing without separate models per language is feasible.
- **Edge-first architecture:** These are designed for edge from inception, not cloud models squeezed down — architecturally better suited as hearing aid distillation sources.
- **Voice cloning for personalization:** Qwen3-TTS clones a voice from 3 seconds of audio — relevant for personalized hearing aid voice processing (e.g., enhancing a specific speaker's voice characteristics).

## Open-Source Trajectory
The open-source model ecosystem (Qwen, Llama, Gemma, SmolLM, Voxtral) is converging toward efficient models that could serve as teacher models for hearing-specific distillation. Qwen3.6 running on a laptop (April 2026) is still ~1000x too large for hearing aid chips, but the compression trajectory (175B GPT-3 in 2020 to 3B active in 2026) suggests hearing-aid-scale foundation models within the decade.

The ternary quantization trajectory is particularly notable: PrismML's 1.7B model at 1.58-bit is approaching mobile/wearable scale. Combined with MoE sparsity (3B active from 35B), a ternary MoE model could theoretically achieve frontier reasoning with active parameters small enough for aggressive distillation to hearing aid targets.

## Related Pages
- [[on-device-ml-hearing-aids]] — The deployment environment for SLMs in hearing
- [[large-sensor-models]] — LSMs must be distilled to SLM-scale for wearable deployment
- [[model-compression]] — Quantization, distillation, and pruning techniques for edge deployment
- [[google-research]] — Gemma models and TurboQuant compression research
- [[mixture-of-experts]] — MoE architecture enabling large model capacity at small inference cost
- [[state-space-models]] — SSMs as alternative architecture for efficient edge sequence modeling

## Sources
- [Open-Source Speech AI Edge-Native (April 2026)](../../sources/open-source-speech-ai-edge-native-april-2026.md) — Voxtral, Qwen3-ASR/TTS, Distil-Whisper landscape
