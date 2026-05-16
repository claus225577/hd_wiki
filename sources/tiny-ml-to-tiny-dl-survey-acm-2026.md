---
title: "From Tiny Machine Learning to Tiny Deep Learning: A Survey"
authors: [multiple — ACM Computing Surveys 2026]
date_published: 2026
date_ingested: 2026-05-15
url: https://dl.acm.org/doi/10.1145/3776588
doi: 10.1145/3776588
type: academic-survey
venue: ACM Computing Surveys
tags: [tinyml, tiny-deep-learning, model-compression, quantization, on-device-training, edge-ai, embedded-ml-survey]
---

# From Tiny Machine Learning to Tiny Deep Learning — Survey

## Summary

ACM Computing Surveys taxonomy of the transition from classical TinyML (small classifiers on MCU-class hardware) to the emerging Tiny Deep Learning paradigm where compressed neural networks — including transformers and SSMs — run on resource-constrained edge devices. Catalogs compression, quantization, neural-architecture-search-for-edge, and emerging on-device-training techniques.

## Why It Matters for Hearing Aids

- **Reference for HA silicon roadmaps.** The <1 MB / sub-mW envelope that hearing-aid DSPs operate in is exactly the deployment target the survey systematizes. Useful as a sourcebook when scoping which compressed architectures (depthwise-separable CNNs, distilled transformers, low-rank SSMs) can plausibly fit a 2026–2027 HA chip generation.
- **On-device training as a near-term inflection.** The survey gives serious treatment to on-device training and adaptation — the structural prerequisite for hearing aids that personalize to a wearer's listening environments without cloud round-trips. This is the missing rung between "factory-trained DNN ships in the device" and "device adapts in situ."
- **Bridges TinyML literature ↔ HA literature.** Most HA-specific speech-enhancement papers cite computer-science compression literature loosely. A current survey collapses the gap.

## Key Thematic Areas Covered

- Quantization (post-training, quantization-aware training, mixed-precision)
- Pruning (structured / unstructured / movement)
- Knowledge distillation
- Neural architecture search constrained on memory / energy / latency
- Tiny transformers and tiny state-space models
- Federated and on-device training under MCU memory budgets
- Hardware-aware compiler tooling (TVM, microTVM, Edge Impulse)

## Significance for the Wiki

- Anchor reference for the [[../concepts/tinyml-edge-ai]] page going forward.
- Feeds [[../concepts/model-compression]] with a current literature spine.
- Useful primary-source pointer for [[../concepts/on-device-ml-hearing-aids]] and [[../concepts/hearing-aid-chip-architectures]].

## Coverage

- ACM Digital Library: https://dl.acm.org/doi/10.1145/3776588

## Related Wiki Pages
- [[../concepts/tinyml-edge-ai]]
- [[../concepts/model-compression]]
- [[../concepts/on-device-ml-hearing-aids]]
- [[../concepts/small-language-models-edge-ai]]
- [[../concepts/state-space-models]]
- [[../concepts/mamba-architecture]]
