---
title: "TF-MLPNet: Tiny Real-Time Neural Speech Separation"
type: source
source_type: arxiv-paper
created: 2026-05-17
authors: [Itani, et al.]
venue: arXiv:2508.03047
date: 2025-08 (latest revision indexed 2026)
url: https://arxiv.org/html/2508.03047v1
tags: [speech-separation, target-speaker-extraction, on-device, mlp, hearables, low-power-accelerator, edge-ai]
---

# TF-MLPNet: Tiny Real-Time Neural Speech Separation for Low-Power Hearables

## Source Metadata
- **Authors:** Itani et al. (UW Computer Science)
- **Venue:** arXiv:2508.03047
- **URL:** https://arxiv.org/html/2508.03047v1
- **Ingested:** 2026-05-17

## Key Claim
First on-device, real-time neural speech-separation network designed for the hearable power envelope. Operates in the time-frequency domain by processing **frequency sequences with stacks of fully-connected (MLP) layers** that alternate along the channel and frequency dimensions. Beats prior streaming baselines on both **blind speech separation** and **target speaker extraction** while staying within the compute budget of current low-power audio NPUs.

## What's Different About the Design
Explicit design constraint that is the actual story: the authors **deliberately avoid transformers and state-space (Mamba) blocks** because today's low-power hardware accelerators in hearables and hearing aids do not support those operations. This is one of the few SE papers to name the silicon-architecture gap as a first-class design constraint rather than a deployment afterthought.

Architecture stack: depthwise-conv + alternating-axis MLPs over TF bins, quantization-aware-trainable, streamable.

## Why It Matters for Hearing Aids
- Reaffirms that **MLP / depthwise-conv / quantized-CRN remains the deployable envelope** for hearing-aid SoCs in 2026. Transformer-on-hearing-aid is still gated on the next silicon cycle.
- Target-speaker extraction is precisely the workload that pairs with auditory attention decoding (AAD) — TF-MLPNet provides one half of a brain-controlled-hearing pipeline that could fit a hearing aid's compute budget; the AAD side (per Columbia work, May 2026) is still ECoG-bound.
- Practical pattern: design the architecture around the accelerator opcode set first, then optimize the math — inverse of the standard ML-research workflow.

## Limitations / Caveats
- "Hearables" power budget is still 1–2 orders of magnitude above what's available on a hearing-aid SoC; gap remains but is closing.
- Benchmarks are LibriMix / WSJ0-2mix; ecological-validity question per Gijbels et al. applies.
- Paper does not address linguistic-hallucination failure-modes; relevant if the model is ever extended with generative re-synthesis.

## Related Wiki Pages
- [[speech-enhancement-neural-networks]] — TF-MLPNet as the on-chip-deployable separation reference
- [[on-device-ml-hearing-aids]] — silicon-opcode-driven design constraint
- [[hearing-aid-chip-architectures]] — argument for accelerator-aware model design
- [[auditory-attention-decoding]] — pairs with AAD as the target-speaker side of brain-controlled hearing
- [[mamba-architecture]] — contrast (Mamba is not deployable on current HA NPUs)
- [[tinyml-edge-ai]] — same deployable-envelope thesis
