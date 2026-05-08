---
title: A TinyML Device for Risk Identification and Speech Enhancement for People with Hearing Loss (STM32)
type: research-paper
date: 2025-2026
journal: Internet of Things (Elsevier)
url: https://www.sciencedirect.com/science/article/pii/S2542660525003543
tags: [tinyml, stm32, microcontroller, speech-enhancement, edge-ai, hearing-aid, model-compression, pruning, latency]
---

# TinyML Speech Enhancement on STM32

## Key Extractions

### Approach
- Implements speech-enhancement DNN on an **STM32 microcontroller** for hearing-aid-class hardware.
- Uses pruning to compress the model to fit microcontroller memory and compute budgets.
- Auxiliary use case: identifying hazardous environmental sounds and providing haptic feedback to alert hearing-impaired users.

### Headline Numbers
- **Memory size reduced by 47%** via pruning.
- **Computational latency: 4.26 ms** — well below the **10 ms** real-time benchmark for hearing aids.
- Demonstrates feasibility of meaningful neural speech enhancement on a commodity microcontroller, not a phone or proprietary DSP.

## Relevance
- Adds a concrete, reproducible 2025–2026 data point that hearing-aid-grade speech enhancement is now within the latency and power envelope of microcontrollers.
- Implications:
  - **OTC and budget hearing aid feasibility** — neural SE no longer requires Sonova/Demant-class proprietary chips.
  - **Standalone inference** — no need for phone-based offload, preserving privacy and battery.
  - **Sub-10 ms latency** is the bar; this paper clears it with substantial headroom.
- Connects to the broader trajectory in `wiki/concepts/on-device-ml-hearing-aids.md` and the Phonak DeepSonic / Starkey Genesis-AI proprietary-chip narrative.
