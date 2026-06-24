---
title: "Mellow: A Small Audio Language Model for Reasoning (CMU, 167M params)"
type: source
source_type: research-paper
publisher: arXiv / Carnegie Mellon University
published: 2025-03-11
ingested: 2026-06-24
url: https://arxiv.org/abs/2503.08540
code: https://github.com/soham97/mellow
weights: https://huggingface.co/soham97/mellow
tags: [audio-language-model, small-language-model, slm, edge-ai, on-device, reasoning, htsat, smollm2, audio-reasoning, cmu, soham-deshmukh]
---

# Mellow — Small Audio Language Model for Reasoning (CMU)

## What

**Mellow** is a **167M-parameter audio language model** developed at Carnegie Mellon University (Soham Deshmukh et al., arXiv 2503.08540, March 2025). Architecturally it pairs **HTSAT** (Hierarchical Token Semantic Audio Transformer) as the audio encoder with **SmolLM2** as the language backbone, trained on the **ReasonAQA** dataset of audio-question-answer triples.

## Key Numbers

- **167M total parameters** — roughly **50× smaller** than typical audio-LMs in its peer set (Qwen2-Audio, SALMONN, LTU).
- **~155 hours of training audio** (AudioCaps + Clotho) — about **60× less** training audio than comparable models.
- **Matches Qwen2-Audio** on MMAU benchmark.
- **Outperforms larger models** on deductive and comparative reasoning sub-tasks.

## Functional Interface

Takes **two audio inputs + a text prompt**, produces **free-form text output**. Designed for audio-grounded reasoning (compare two clips, answer questions about temporal/causal/comparative relationships) rather than transcription.

## Why It Matters for Hearing AI

- **Architectural precedent for sub-200M audio reasoners on consumer silicon.** The hearing-aid industry has been doing "SLM" since before the term existed — Mellow externally validates that 100M-class audio reasoning is competitive with billion-class peers, which compresses the credible upper bound for on-HA / on-companion-phone audio LMs.
- **HTSAT + SmolLM2 stack is shippable on phones today.** Both component models are open-weight. SmolLM2 (Hugging Face) already runs in-browser via WebGPU; HTSAT is light enough to quantize to INT8 on Snapdragon-class DSPs. The full Mellow stack is a **companion-phone candidate** rather than an in-ear HA-chip candidate (167M is still too big for current HA SoCs), but it sits squarely in the companion-phone speech pipeline tier alongside QVAC MedPsy.
- **Audio reasoning is the missing layer above scene classification.** Today's HA pipelines do scene classification (which scene am I in?) and speech enhancement (clean this signal). Audio reasoning ("compare these two clips" / "is the speaker the same person?" / "did the alarm just go off?") sits one abstraction layer up and is currently absent from shipping products. Mellow shows the recipe is feasible at edge-friendly sizes.
- **ReasonAQA dataset is open** — meaningful for the closed-loop-data-flywheel concept: HA OEMs that want to bootstrap audio-reasoning capability can fine-tune on ReasonAQA without licensing concerns.

## Carry-Forward Flags

- Whether any HA OEM ships a Mellow-derived (or Mellow-style) companion-phone audio reasoner before mid-2027 — would be the first commercial proof of the 100M-class audio-LM thesis on consumer hardware.
- Whether the HTSAT encoder gets a quantization-friendly successor — HTSAT's transformer block is the limiting factor for fitting the encoder side onto HA-class chips.
- Whether ReasonAQA becomes a citation magnet (proxy for whether audio-reasoning evaluation has stable benchmarks; right now it competes with MMAU).

## Related Wiki Pages

- [[../wiki/concepts/small-language-models-edge-ai.md]] — Mellow joins the SLM roster as the **smallest credible audio-LM** in the wiki.
- [[../wiki/concepts/on-device-ml-hearing-aids.md]] — Companion-phone tier, not in-ear tier.
- [[../wiki/concepts/audio-reasoning-chain-of-thought.md]] — Closest existing concept page for audio reasoning above scene classification.
- [[../wiki/concepts/companion-phone-speech-pipeline.md]] — Where a Mellow-class model would sit in a hearing-aid product architecture.
- [[../wiki/concepts/closed-loop-data-flywheel.md]] — Open dataset (ReasonAQA) lowers the bar for OEM bootstrapping.
