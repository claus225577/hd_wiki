---
title: Hearing Aid Chip Architectures
type: concept
created: 2026-04-15
updated: 2026-04-22
sources: [hardware-software-codesign-edge-ai-2026.md, starkey-omega-ai-launch-2025.md, phonak-infinio-sphere-2024.md, resound-vivia-launch-2025.md, wireless-hearables-programmable-speech-ai-accelerators-arxiv-2025.md, aizip-tiny-ai-hearing-devices-2026.md, michigan-compute-in-memory-rram-ssm-nature-2026.md]
related: [on-device-ml-hearing-aids.md, dnn-in-hearing-aids.md, dnn-architectures-hearing-aids.md, small-language-models-edge-ai.md, mixture-of-experts.md, compute-in-memory.md, state-space-models.md]
tags: [chips, npu, edge-ai, hardware, dual-chip, integrated, power-efficiency, compute-in-memory, rram]
---

# Hearing Aid Chip Architectures

The silicon layer that makes real-time DNN processing possible inside a device smaller than a thumbnail. Two competing philosophies have emerged: integrated NPU designs and dual-chip architectures — each with distinct power, flexibility, and capability tradeoffs.

## The Challenge

Hearing aid chips must execute tens of billions of neural network operations per day while consuming less than 5 milliwatts total — often less than 1 mW for the ML block alone. The chip must also handle classical DSP, Bluetooth radio management, and increasingly health sensor processing. This is arguably the most constrained compute environment in consumer electronics.

Key edge AI constraints:
- **Power budget:** 1–5 mW total device; <1 mW for ML block
- **Memory:** 256 KB–2 MB SRAM on-chip; no DRAM
- **Latency:** <10 ms end-to-end algorithmic delay
- **Throughput:** 16,000+ audio samples per second, continuous
- **Connectivity:** no cloud; all inference on-chip
- **Form factor:** SoC must fit on a chip smaller than 5 mm²

## Two Competing Architectures

### Approach 1: Integrated NPU (Single-Chip)

A single SoC integrates the audio DSP, a dedicated Neural Processing Unit (NPU), radio, and power management in one die.

**Starkey Neuro Processor (G2/G3)**
- Starkey's custom chip family for Genesis AI and later devices
- On-chip NPU handles DNN inference alongside DSP pipeline
- "Neuro" branding reflects the NPU's role as the AI engine
- Third-generation (G3) chip in Starkey Omega (2025 launch) adds expanded AI capabilities including fall detection, health monitoring, and real-time translation
- Advantage: single-chip design simplifies power management and reduces inter-chip communication overhead

**Demant Polaris**
- Used in Oticon More, Real, Intent product lines
- Unified SoC with integrated neural processing
- First to market with DNN (Oticon More, 2021)
- Lower component count, simpler PCB layout, competitive power efficiency

### Approach 2: Dual-Chip (Separate AI Processor)

A classical audio DSP handles deterministic signal processing while a dedicated AI chip handles DNN inference. The two chips communicate over a low-power bus.

**Phonak DEEPSONIC Chip (Infinio Sphere, 2024)**
- Separate dedicated AI chip alongside the classical PRISM DSP
- The AI chip is specifically optimized for DNN matrix operations
- Allows each chip to be tuned for its workload — DSP chip optimized for low-latency filtering, AI chip optimized for neural inference throughput
- Phonak claims the dedicated AI chip enables more complex DNN models than integrated approaches allow at equivalent total power

**ReSound 360+DNN (Vivia, 2025)**
- Dual-chip architecture: existing Organic Hearing DSP + separate neural processing chip
- Reported processing capability: **4.9 trillion operations per day** (approximately 56.7 billion ops/second)
- Enables continuous DNN-based scene analysis, speech enhancement, and directional processing running simultaneously
- First ReSound device with dedicated on-chip DNN inference hardware

## Architecture Tradeoff Matrix

| Dimension | Integrated NPU | Dual-Chip |
|-----------|---------------|-----------|
| Power efficiency | Higher (single power domain) | Lower (two chips, two power rails) |
| DSP/ML resource contention | Yes — share compute resources | No — dedicated resources per task |
| Model complexity ceiling | Limited by shared memory/power | Higher — AI chip can be sized for the task |
| Component count | 1 SoC | 2+ chips on PCB |
| PCB design complexity | Simpler | More complex |
| Upgrade path | Full chip revision to change either | Can upgrade AI chip independently |
| Interconnect latency | None (on-chip) | Small but non-zero inter-chip bus latency |
| Design risk | Single point of failure | More resilient |

**Neither approach has definitively won.** Integrated NPU dominates in miniaturized ITC/CIC form factors where PCB space is minimal. Dual-chip is preferred for RIC/BTE devices where space allows larger PCBs.

## Processing Power Statistics

To put hearing aid AI compute in context:

| Device | Reported Processing Capability |
|--------|-------------------------------|
| ReSound Vivia (dual-chip) | 4.9 trillion operations/day |
| DEEPSONIC research chip | 7.7 billion ops/second (666T ops/day) |
| Starkey G3 Neuro Processor | Not publicly disclosed |
| Phonak PRISM (Infinio) | Not publicly disclosed |

Note: manufacturer-reported figures use different measurement conventions — direct comparisons are difficult.

## Edge AI Constraints Driving Research

### Hardware-Software Co-Design (Michigan 2026)
University of Michigan research published in early 2026 explicitly targets **hardware-software co-design** for edge AI in hearing instruments. Key themes:
- Jointly optimize DNN architecture and chip microarchitecture — instead of designing hardware for a fixed model, co-design both together
- Exploit sparse activation patterns in audio DNNs to skip zero-valued computations
- Mixed-precision quantization (different layers run at different bit widths based on sensitivity)
- Compile-time scheduling that maps DNN layers directly to chip resources without runtime overhead
- Results: 2–4x efficiency improvements over baseline chip designs with equal model accuracy

### Programmable Speech AI Accelerators (arXiv 2025)
arXiv:2503.18698v2 demonstrates a **programmable accelerator** co-designed with speech AI models for wireless hearables:
- Mixed-precision quantization (per-layer bit width selection) for optimal accuracy vs. efficiency
- Programmable silicon — firmware-updateable with new DNN models post-deployment
- 28-participant human perceptual evaluation validates the hardware-model co-design approach
- Represents an alternative to fixed-function NPUs: flexibility of a programmable core with the efficiency of custom datapath

### Aizip: Software-Only AI on Standard Chips (2026)
Aizip demonstrates that **AI noise reduction can run on standard hearing device hardware** without custom NPU:
- Platform approach: optimized tiny AI models + deployment tooling targeting commodity DSPs
- Could enable AI features on mid-tier and OTC devices that lack dedicated DNN accelerators
- Validates that software optimization (quantization, pruning, efficient architectures) can compensate for hardware limitations
- Strategic implication: custom NPU may not be required for all AI hearing use cases

### Memory Bandwidth as Primary Bottleneck
For hearing aid chips, the limiting factor is often memory bandwidth — reading model weights from SRAM — not raw compute. Architectures that reuse weights efficiently (e.g., depthwise separable convolutions, recurrent networks with small hidden states) are strongly favored over those with large, one-time-use weight matrices.

## Approach 3: Compute-in-Memory (CIM) — Emerging Paradigm

A fundamentally different architecture where computation happens inside the memory array itself, eliminating the data movement bottleneck that dominates power in conventional chips. See [[compute-in-memory]] for full concept page.

### RRAM Crossbar Arrays (Michigan, Nature Communications 2026)
University of Michigan researchers demonstrated the **first mapping of state space models onto RRAM crossbar arrays**:
- **Memristive devices** store model weights as analog conductance values
- **Vector-matrix multiplication** happens via physics (Ohm's law) — not sequential digital operations
- Tungsten oxide at different thicknesses achieves different decay rates for SSM temporal dynamics
- Accuracy within **4.6 bits of ideal** digital computation
- **Dramatically reduced latency and power** vs. conventional digital hardware
- Paper explicitly names hearing aids as a target application

### CIM vs Integrated NPU vs Dual-Chip

| Dimension | Integrated NPU | Dual-Chip | Compute-in-Memory |
|-----------|---------------|-----------|-------------------|
| Compute paradigm | Digital sequential | Digital sequential | Analog parallel |
| Memory bottleneck | Yes (SRAM reads) | Yes (SRAM reads) | Eliminated |
| Power for data movement | Dominant cost | Dominant cost | Near-zero |
| Programmability | Full (firmware update) | Full (firmware update) | Limited (reprogram RRAM) |
| Manufacturing maturity | Production | Production | Research/prototype |
| Model flexibility | Any model | Any model | Model encoded in hardware |

CIM does not replace integrated NPU or dual-chip for current products, but represents the trajectory for next-generation hearing aid silicon where memory bandwidth is the primary bottleneck.

## Future Directions

- **Analog neural networks:** Charge-domain computation for sub-milliwatt inference
- **Neuromorphic processing:** Spike-based neural computation matching the temporal sparsity of audio signals
- **Unified biometric + audio processing:** Single chip handling audio DNN, PPG health sensing, and IMU-based fall detection
- **Ternary-native compute units:** PrismML Ternary Bonsai (April 2026) demonstrates 1.58-bit {-1, 0, +1} weight models that eliminate multiplications entirely. If hearing aid NPUs adopted ternary-native logic, inference becomes additions/subtractions only — dramatically reducing power and area. A model requiring 2 MB at INT8 could fit in ~220 KB at 1.58-bit. See [[model-compression]].

## Related Pages
- [[on-device-ml-hearing-aids]] — Full ML task landscape and deployment constraints
- [[dnn-in-hearing-aids]] — DNN history, inference pipeline, and clinical metrics
- [[dnn-architectures-hearing-aids]] — Detailed CRN, transformer, and architecture analysis
- [[small-language-models-edge-ai]] — Model compression techniques that make DNN-on-chip feasible
- [[compute-in-memory]] — CIM paradigm: computation inside memory arrays
- [[state-space-models]] — SSMs as the natural model architecture for CIM hardware

## Sources
- [Hardware-Software Co-Design Edge AI 2026](../../sources/hardware-software-codesign-edge-ai-2026.md) — Michigan 2026 co-design research
- [Starkey Omega AI Launch 2025](../../sources/starkey-omega-ai-launch-2025.md) — G3 Neuro Processor details
- [Phonak Infinio Sphere 2024](../../sources/phonak-infinio-sphere-2024.md) — DEEPSONIC dual-chip architecture
- [ReSound Vivia Launch 2025](../../sources/resound-vivia-launch-2025.md) — 360+DNN dual-chip, 4.9T ops/day
- [Wireless Hearables Programmable Speech AI Accelerators](../../sources/wireless-hearables-programmable-speech-ai-accelerators-arxiv-2025.md) — Programmable co-designed silicon
- [Aizip Tiny AI for Hearing Devices](../../sources/aizip-tiny-ai-hearing-devices-2026.md) — Software-only AI on standard hardware
- [Michigan CIM RRAM + SSM (Nature Communications 2026)](../../sources/michigan-compute-in-memory-rram-ssm-nature-2026.md) — First SSM-on-CIM mapping, RRAM crossbar arrays
