---
title: "QVAC MedPsy: State-of-the-Art Medical and Healthcare Language Models for Edge Devices"
type: source
source_type: model-release
authors: [Tether AI Research Group / QVAC]
publisher: Hugging Face Blog (qvac/medpsy)
publication_date: 2026-05-07
url_primary: https://huggingface.co/blog/qvac/medpsy
url_secondary: https://tether.io/news/tether-unveils-medical-ai-that-runs-on-phones-outperforms-much-larger-sota-models-and-can-cut-the-cloud-out-entirely/
license: Apache-2.0
ingested: 2026-05-15
tags: [edge-ai, on-device-llm, medical-llm, smartphone-ai, healthcare-ai, llm-quantization]
---

# QVAC MedPsy — On-Device Medical Language Models

## Citation
QVAC / Tether AI Research Group. "QVAC MedPsy: State-of-the-Art Medical and Healthcare Language Models for Edge Devices." Hugging Face Blog, May 7, 2026. https://huggingface.co/blog/qvac/medpsy

## Key Facts

- **Release date:** May 7, 2026
- **Models:** QVAC MedPsy-1.7B and QVAC MedPsy-4B
- **License:** Apache 2.0 (research and educational use)
- **Backbone:** Qwen3 family, text-only, medical-specialized
- **Post-training pipeline:** SFT (broad medical adaptation) → SFT (reasoning specialization) → RL on AlphaMedQA → RL on hard-enriched dataset with failure-case mining
- **Training data:** ~30M synthetic rows, teacher model Baichuan-M3-235B
- **Quantization:** GGUF formats (7 quantized variants per model); recommended Q4_K_M ≈ 1.28 GB (1.7B) and 2.72 GB (4B); IQ3_M for 4B (76% reduction) matches BF16 on HealthBench Hard
- **Runtime:** llama.cpp; QVAC SDK for on-device inference

## Benchmark Headlines

| Model | Avg closed-ended (7 tasks) | HealthBench |
|---|---|---|
| QVAC MedPsy-1.7B | 62.62 (+11.42 vs MedGemma-1.5-4B-it) | matches Qwen3-4B |
| QVAC MedPsy-4B | 70.54 | 74.00 |
| Google MedGemma-27B | 69.95 (4B beats it at 7× smaller) | — |

Closed-ended benchmarks: MedQA-USMLE, MedMCQA, MMLU Health, MMLU-Pro Health, MedXpertQA, AfriMedQA, PubMedQA. Open-ended: HealthBench / HealthBench Hard with 3 judge models (CompassJudger-2-32B, Llama-3.3-70B, GPT-OSS-120B).

## Token Efficiency

- 4B model: 909 tokens vs 2,953 for Qwen3-4B (3.2× reduction)
- 1.7B model: 1,110 tokens vs 1,901 for Qwen3-1.7B (1.7× reduction)

## Intended Use Cases

- Edge deployment: smartphones, tablets, wearables, low-bandwidth healthcare settings
- Privacy-sensitive workflows: on-device inference, no data leaves device
- Clinical decision support, medical Q&A, diagnostic assistance, health literacy
- Low-bandwidth / disconnected environments

## Notable Gap

Despite the "MedPsy" name, the documentation focuses on general medical reasoning rather than psychiatric specialization. Mental-health-specific evaluation is not detailed in the release blog.

## Hearing Industry Relevance

- The hearing aid SoC remains too small (sub-100 MB working memory typical) to host a 1.3 GB model. The relevant deployment target is the **paired smartphone**, where companion apps already run.
- Reframes the hearing-care companion app from a thin shell (fitting controls + self-tests) to a substrate for richer interaction: tinnitus iCBT counselling, plain-language audiogram explanation, post-fit Q&A, conversational triage.
- Addresses the cloud-LLM regulatory and privacy friction that has slowed digital therapeutics in EU MDR / FDA SaMD environments.
- The bottleneck shifts from compute to **hearing-care domain alignment** — audiology training corpora are an order of magnitude sparser than general medicine.

## Related Wiki Pages

- [[../wiki/concepts/small-language-models-edge-ai]] — General SLM landscape
- [[../wiki/concepts/on-device-ml-hearing-aids]] — On-device deployment for hearing aids vs companion phones
- [[../wiki/concepts/digital-therapeutics-tinnitus]] — Adherence problem in SilentCloud
- [[../wiki/concepts/medical-domain-edge-llms]] — New concept page
- [[../wiki/entities/sonova-ag]] — Owns SilentCloud; companion-app substrate relevant
