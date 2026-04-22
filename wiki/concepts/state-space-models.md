---
title: State Space Models (SSMs) for Hearing AI
type: concept
created: 2026-04-22
updated: 2026-04-22
sources: [michigan-compute-in-memory-rram-ssm-nature-2026.md, applied-brain-research-ssm-edge-audio-2026.md]
related: [dnn-architectures-hearing-aids.md, compute-in-memory.md, on-device-ml-hearing-aids.md, hearing-aid-chip-architectures.md, speech-enhancement-neural-networks.md, small-language-models-edge-ai.md]
tags: [state-space-models, ssm, mamba, s4, edge-ai, streaming-audio, hearing-aids, transformer-alternative]
---

# State Space Models (SSMs) for Hearing AI

State space models are a class of sequence models based on linear recurrence that offer an alternative to both transformers and traditional RNNs for processing sequential data. For hearing AI, SSMs are notable because they naturally handle streaming audio with O(n) complexity, are inherently causal, and map efficiently onto specialized hardware including compute-in-memory arrays.

## What Are State Space Models?

SSMs are rooted in classical control theory. They model a system as:
- **State update:** x(t+1) = A * x(t) + B * u(t)
- **Output:** y(t) = C * x(t) + D * u(t)

Where x is a hidden state, u is the input, and A/B/C/D are learned matrices. Key properties:

| Property | SSM | Transformer | RNN (LSTM/GRU) |
|----------|-----|-------------|----------------|
| Sequence complexity | O(n) | O(n^2) | O(n) |
| Parallelizable training | Yes (convolution mode) | Yes | No |
| Causal by default | Yes | No (requires masking) | Yes |
| Long-range dependencies | Excellent (structured A matrix) | Excellent (attention) | Poor (gradient issues) |
| Streaming inference | Natural (recurrence mode) | Difficult (KV cache grows) | Natural |
| Memory during inference | Fixed (hidden state size) | Grows with context | Fixed |

## Key SSM Architectures

### S4 (Structured State Spaces for Sequence Modeling)
- Introduced HiPPO initialization for the A matrix — enables very long-range memory
- Dual mode: convolutional (fast parallel training) and recurrent (fast sequential inference)
- Foundation architecture that spawned the SSM family

### Mamba
- Adds selective state space mechanism — input-dependent gating of which information to remember/forget
- Eliminates the rigid structure of S4's A matrix in favor of learned selectivity
- Competitive with transformers on language modeling benchmarks at fraction of compute
- Hardware-efficient implementation with selective scan

### Mamba-2 / State Space Duality
- Proves mathematical equivalence between SSMs and structured attention under certain conditions
- Enables hybrid architectures mixing SSM and attention layers

## Why SSMs Fit Hearing Aids

SSMs address multiple hearing aid constraints simultaneously:

1. **Streaming audio processing:** SSMs process input sample-by-sample in recurrence mode — no need to buffer audio frames or maintain growing context windows
2. **O(n) complexity:** Unlike transformers (O(n^2) attention), SSMs scale linearly with sequence length — critical for continuous 24/7 audio processing
3. **Fixed memory during inference:** Hidden state is a fixed-size vector regardless of how long the model has been running — unlike transformer KV caches that grow over time
4. **Inherently causal:** SSMs only use past information by construction — no need for causal masking or architectural modifications
5. **Temporal dynamics in hardware:** The A matrix decay rates can be physically implemented in analog hardware (see [[compute-in-memory]])

## SSMs on Compute-in-Memory Hardware

The University of Michigan team (Nature Communications 2026) demonstrated the first mapping of SSMs onto RRAM crossbar arrays:

- **Vector-matrix multiplication** (the core SSM operation) maps directly to crossbar physics
- **Decay rates** (A matrix diagonal entries) implemented as tungsten oxide memristors with different thicknesses — the physics of the material encodes the temporal dynamics
- **4.6-bit accuracy** gap from ideal digital computation — sufficient for many audio processing tasks
- **Dramatic power and latency reduction** compared to running the same SSM on conventional digital hardware
- The paper explicitly names hearing aids as a target application

This CIM+SSM combination is particularly elegant: both the hardware (analog in-memory computation) and the model (linear recurrence) avoid the von Neumann bottleneck that limits current hearing aid chips.

## Applied Brain Research: Production SSMs for Edge Audio

Applied Brain Research (ABR) builds SSM-based systems for streaming audio on edge devices:

- **Streaming speech processing:** SSMs treat speech as a continuous signal, not chunked frames
- **On-device capabilities:** Speech-to-text, text-to-speech, speech-to-intent — all on-device
- **TSP1 hardware accelerator:** Custom chip running at under 30mW, designed for SSM inference
- **Always-on processing:** Power budget enables continuous voice and biosignal processing for wearables

The TSP1 at 30mW is still ~6-30x above hearing aid total power budgets (1-5mW), but demonstrates the trajectory. ABR's work validates SSMs as production-ready for real-time audio, not just a research curiosity.

## SSMs vs Current Hearing Aid Architectures

| Dimension | CRN (Current Production) | SSM (Emerging) |
|-----------|-------------------------|----------------|
| Temporal modeling | RNN layers (LSTM/GRU) | Linear recurrence (S4/Mamba) |
| Spectral modeling | CNN layers | Can be combined with CNN front-end |
| Training parallelism | Limited (RNN sequential) | Full (convolution mode) |
| Long-range context | Limited by RNN memory | Excellent (HiPPO/structured A) |
| Hardware mapping | Digital DSP/NPU | Digital or analog CIM |
| Production maturity | Shipping in products | Research/prototype |
| Power on current chips | Optimized for existing NPUs | Not yet optimized for HA silicon |

SSMs are not yet ready to replace CRNs in production hearing aids, but they offer a compelling future path — especially when paired with CIM hardware that can implement the linear recurrence in analog domain.

## Open Questions

- **Accuracy on hearing-specific benchmarks:** SSMs have not yet been extensively evaluated on hearing aid speech enhancement benchmarks (STOI, SI-SNR on hearing aid noise conditions)
- **Sub-1ms latency feasibility:** Can SSMs achieve the emerging 1ms latency target for hearing aid DNN blocks?
- **CRN-SSM hybrids:** Could a CNN front-end + SSM temporal backbone replace CRN's CNN+RNN combination?
- **Selective state spaces for attention decoding:** Could Mamba's selective mechanism be adapted for auditory attention decoding (choosing which speaker to enhance)?

## Related Pages
- [[dnn-architectures-hearing-aids]] — CRN, SepFormer, and other architectures SSMs could complement or replace
- [[compute-in-memory]] — The hardware paradigm that makes SSM-on-chip particularly efficient
- [[on-device-ml-hearing-aids]] — The deployment constraints SSMs must satisfy
- [[hearing-aid-chip-architectures]] — Current chip designs and how CIM+SSM fits the future roadmap
- [[speech-enhancement-neural-networks]] — The primary application where SSMs could be deployed
- [[small-language-models-edge-ai]] — SSMs as an alternative architecture for compact edge models

## Sources
- [Michigan CIM RRAM + SSM (Nature Communications 2026)](../../sources/michigan-compute-in-memory-rram-ssm-nature-2026.md) — First SSM-on-CIM mapping
- [Applied Brain Research SSM Edge Audio](../../sources/applied-brain-research-ssm-edge-audio-2026.md) — Production SSMs for streaming audio, TSP1 hardware
