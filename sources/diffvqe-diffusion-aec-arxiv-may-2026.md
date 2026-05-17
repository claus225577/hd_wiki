---
title: "DiffVQE: Hybrid Diffusion Voice Quality Enhancement Under Acoustic Echo and Noise"
url: https://arxiv.org/abs/2605.08189
date: 2026-05-12
type: paper
authors: [Haljan Lugo Girao, Ernst Seidel, Pejman Mowlaee, Ziyue Zhao, Tim Fingscheidt]
venue: arXiv (submitted to Interspeech 2026)
arxiv_id: 2605.08189
tags: [diffusion, speech-enhancement, acoustic-echo-cancellation, aec, voice-quality, generative-se, companion-phone-pipeline, deep-vqe, single-step-diffusion]
---

# DiffVQE: Hybrid Diffusion Voice Quality Enhancement Under Acoustic Echo and Noise

## Summary
First reproducible diffusion-based **acoustic echo control (AEC)** system. Hybrid score-based diffusion topology adapted for joint AEC + denoising. Outperforms Microsoft's DeepVQE — the prior SOTA — on both echo and noise control benchmarks while being **smaller, less complex, and faster** (single-step inference). Trained on publicly accessible Interspeech 2025 URGENT Challenge data with full topology and training-framework disclosure.

## Key Claims
- First diffusion-based AEC system designed for reproducibility (topology, data, framework all public).
- Beats DeepVQE on echo control AND noise control simultaneously — not a trade-off.
- Single-step inference removes the inference-cost penalty that has limited diffusion deployment in real-time speech.
- Smaller model and lower compute than DeepVQE.

## Methods
- Score-based hybrid diffusion topology adapted from speech-enhancement diffusion work, restructured for AEC.
- Public dataset (Interspeech 2025 URGENT Challenge) ensures benchmark reproducibility — historically a weak point of large-vendor SE / AEC publications.
- Compared head-to-head with DeepVQE (Microsoft's prior reproducible-claim AEC baseline).

## Why It Matters for Hearing Aids
- **Not an on-chip story.** Hearing-aid SoC power budgets remain incompatible with diffusion-style inference even at single-step latency.
- **It's a companion-phone-pipeline story.** Teams, Zoom, iOS-VoIP, and Android telephony stacks are progressively delivering cleaned audio to the aid over Bluetooth LE Audio / Auracast. Microsoft's DeepVQE lineage feeds Teams; DiffVQE represents the next-generation alternative for the same call-quality pipeline.
- The hearing aid's role shifts when upstream audio is generatively cleaned: **"clean the signal" → "decide how much to trust what arrived."** That trust-calibration layer is currently unbuilt at the OEM level.

## Pattern: Single-Step Generative SE Latency Wall Breaking
DiffVQE is now the third 2026 paper extending single-step / efficient generative SE:
- **Predictive-generative drift decomposition** (early May 2026)
- **DriftSE** (arXiv 2604.24199) — single-step equilibrium SE matches multi-step diffusion baselines on VoiceBank+DEMAND
- **DiffVQE** (arXiv 2605.08189) — single-step diffusion AEC + denoising

The categorical assumption that "generative SE = too slow for real-time speech" is breaking.

## Caveats
- "Outperforms DeepVQE" is on the benchmarks the authors chose; DeepVQE has not had a public update in the same window.
- Hearing-impaired listener evaluation (PESQ-HI / HASPI / actual HA-in-loop) is not part of the paper — speech-quality metrics only.
- Reproducibility framing is a research-community virtue but does not, alone, indicate productizability.

## Related
- `wiki/concepts/speech-enhancement-neural-networks.md` — single-step generative branch
- `wiki/concepts/llm-based-speech-enhancement.md` — distinct generative-SE failure mode (hallucination)
- `wiki/concepts/companion-phone-speech-pipeline.md` (new)
- `wiki/entities/sonova-ag.md` — Sonova companion-app context
- `wiki/concepts/auracast-bluetooth-le-audio.md` — LE Audio handoff substrate
