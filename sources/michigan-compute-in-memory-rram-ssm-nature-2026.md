---
title: "A hardware-software co-design to efficiently run AI on edge devices"
type: academic-paper
date_published: 2026-04-01
date_ingested: 2026-04-22
journal: Nature Communications
doi: 10.1038/s41467-025-68227-w
url: https://techxplore.com/news/2026-04-hardware-software-efficiently-ai-edge.html
authors: [Wei Lu, Xiaoyu Zhang, Mingtao Hu]
institution: University of Michigan
tags: [compute-in-memory, rram, memristor, state-space-models, edge-ai, hearing-aids, hardware-software-codesign]
---

# Michigan Compute-in-Memory RRAM + State Space Models (Nature Communications 2026)

## Summary

University of Michigan researchers demonstrate the first mapping of state space models (SSMs) onto compute-in-memory (CIM) hardware using RRAM (resistive RAM) crossbar arrays. This is a hardware-software co-design that moves AI computation into memory itself, eliminating the data movement bottleneck that dominates power consumption in conventional digital processors.

## Key Findings

- **First SSM-on-CIM mapping:** State space models mapped onto RRAM crossbar arrays — a novel combination of an efficient model architecture with an efficient hardware paradigm
- **Memristor tuning via material thickness:** Tungsten oxide memristors at different thicknesses achieve different decay rates, enabling analog representation of SSM temporal dynamics directly in hardware
- **Vector-matrix multiplication accuracy:** Within 4.6 bits of ideal computation — sufficient for many audio/sensor AI tasks
- **Real-time processing:** Dramatically reduced latency and power consumption compared to conventional digital hardware running the same models
- **Explicit target applications:** Hearing aids, phones, autonomous vehicle cameras — the paper directly names hearing aids as a deployment target

## Significance for Hearing AI

This paper bridges two paradigms simultaneously:
1. **Model paradigm:** SSMs as an alternative to transformers/RNNs — inherently suited to streaming temporal data like audio
2. **Hardware paradigm:** Compute-in-memory eliminates the memory bandwidth bottleneck that limits current hearing aid chips

For hearing aids, CIM+SSM could enable:
- Models that process audio as a continuous stream (SSM natural fit) on hardware where computation happens in-memory (no weight-read bottleneck)
- Dramatic power reduction — no data movement between memory and compute units
- Analog computation matching the inherently analog nature of audio signals

## Key Technical Details

- **RRAM crossbar arrays:** Matrix of memristive devices where vector-matrix multiplication happens by applying voltages to rows and reading currents from columns — computation is a physical property of the array, not sequential digital operations
- **State space models:** Linear recurrence models (S4, Mamba family) that process sequences with O(n) complexity vs O(n²) for transformers. Naturally causal and streaming-compatible.
- **4.6-bit accuracy gap:** The analog computation is not perfect — there's a ~4.6 bit gap from ideal digital computation. For hearing aid tasks (noise reduction, scene classification), this level of precision may be sufficient.
