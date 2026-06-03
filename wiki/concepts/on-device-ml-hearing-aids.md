---
title: On-Device ML in Hearing Aids
type: concept
created: 2026-04-15
updated: 2026-05-17
sources: [small-language-models-edge-2026.md, large-sensor-models-arxiv-2026.md, world-models-continual-learning-2026.md, interspeech-2026-audio-reasoning-challenge.md, google-turboquant-iclr-2026.md, prismml-ternary-bonsai-158bit-april-2026.md, wireless-hearables-programmable-speech-ai-accelerators-arxiv-2025.md, aizip-tiny-ai-hearing-devices-2026.md, michigan-compute-in-memory-rram-ssm-nature-2026.md, applied-brain-research-ssm-edge-audio-2026.md, adobe-speechmatics-on-device-stt-april-2026.md, completely-implantable-cochlear-implants-april-2026.md, multi-stage-low-latency-enhancement-ha-arxiv-2026.md, edge-ai-audio-embedded-world-2026.md, hhtm-convergence-ai-audio-hearing-devices-2026.md, tinyml-speech-recognition-arduino-2025.md, anc-open-ear-smart-glasses-cmu-2026.md, meta-synthetic-data-distillation-april-2026.md, google-gemma-4-open-models-april-2026.md, target-speaker-extraction-ultra-low-latency-2026.md, samsung-galaxy-buds-health-monitoring-ppg-2026.md, efficient-on-device-speech-enhancement-qat-2026.md, qualcomm-s5-s3-gen3-sound-platforms-2026.md, l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md, aondevices-edge-ai-ces-2026.md, tiny-ml-to-tiny-dl-survey-acm-2026.md, tf-mlpnet-tiny-speech-separation-arxiv-2026.md]
related: [small-language-models-edge-ai.md, large-sensor-models.md, speech-enhancement-neural-networks.md, dnn-architectures-hearing-aids.md, auditory-attention-decoding.md, cochlear-implant-ai.md, world-models-hearing-ai.md, audio-reasoning-chain-of-thought.md, model-compression.md, ../entities/google-research.md, model-context-protocol.md, mixture-of-experts.md, compute-in-memory.md, state-space-models.md, ../entities/envoy-medical.md, tinyml-edge-ai.md, active-noise-cancellation.md, mamba-architecture.md, synthetic-data-for-hearing-ai.md, llm-based-speech-enhancement.md, linguistic-hallucination-speech-enhancement.md, training-deployment-distribution-gap.md, acoustic-feedback-cancellation.md]
tags: [edge-ai, hearing-aids, inference, dsp, chips, deepsonic, neural-processing, quantization, compute-in-memory, state-space-models, hearable-intelligence, convergence, synthetic-data, llm-based-se]
---

# On-Device ML in Hearing Aids

Machine learning inference running directly on hearing aid hardware, without cloud connectivity. This is the dominant paradigm for hearing aid AI due to latency, privacy, and connectivity constraints.

## Current ML Tasks Running On-Device
1. **Noise reduction** — Separating speech from background noise in real-time
2. **Acoustic scene classification** — Identifying environment (restaurant, outdoors, music, quiet) to select processing programs
3. **Speech enhancement** — Boosting speech clarity, especially in multi-talker scenarios
4. **Feedback cancellation** — Detecting and suppressing acoustic feedback loops
5. **Wind noise reduction** — Identifying and attenuating wind artifacts
6. **Directional processing** — Beamforming steered by ML-based source localization
7. **Health monitoring** — Heart rate from in-ear PPG sensors + ML classification
8. **Fall detection** — Accelerometer + ML (Starkey, others)

## Hardware Landscape
- **Dedicated audio DSPs** — Most hearing aids use custom or semi-custom DSP chips
- **ARM Cortex-M class** — Some newer designs use general-purpose microcontrollers alongside DSPs
- **NPUs** — Emerging: dedicated neural processing units on hearing aid SoCs
- Power budgets: typically 1-5 mW total for the entire device
- Memory: typically 256KB-2MB SRAM, flash for model weights

## Key Players & Their Chips
- **Sonova:** PRISM platform (Phonak Lumity, Infinio) — dual-chip approach separating DSP and ML processing
- **Demant:** Polaris platform (Oticon Real, Intent) — single-chip approach integrating DSP and DNN
- **Starkey:** Custom Starkey chips with "Edge AI" branding
- **WS Audiology:** TwinLink platform
- **GN Hearing:** Organic Hearing platform (ReSound Nexia, Vivia)

### DEEPSONIC Chip (Emerging)
A notable academic/startup chip demonstrating the frontier: **7.7 billion operations per second** with **4.5 million neural connections**, purpose-built for ultra-low-power DNN inference in hearing instruments. Benchmarks this against current commercial chips to show the trajectory of on-device neural compute.

### Programmable Speech AI Accelerators (arXiv 2025)
Custom silicon with **hardware-software co-design** specifically for wireless hearables (arXiv:2503.18698v2):
- **Programmable accelerator** — silicon can be updated with new models post-deployment, unlike fixed-function DNN blocks
- **Mixed-precision quantization** — different bit widths for different layers/operations; more nuanced than uniform INT8
- **28-participant human evaluation** — validated speech enhancement quality with perceptual (not just objective) metrics
- Represents the frontier of co-designed hardware+model for hearing/audio AI

### TF-MLPNet — Accelerator-Opcode-Driven Design (Itani et al., 2025/2026)
arXiv:2508.03047. First on-device real-time neural speech-separation network for low-power hearables that explicitly designs around what current HA NPUs can execute:
- **Why it matters here:** The paper names the silicon-architecture gap as a first-class constraint rather than a deployment afterthought. **Transformer and Mamba blocks are not supported by today's low-power audio accelerators** in hearables and hearing aids.
- **Pure MLP + depthwise-conv** stacks alternating along channel/frequency axes; quantization-friendly, streamable, beats prior streaming separation and target-speaker-extraction baselines within the hearable power envelope.
- **Deployable-envelope reaffirmed:** in 2026 the on-chip envelope is MLP / depthwise-conv / quantized-CRN; INT8 / INT4 quantization is table stakes. Transformer-on-hearing-aid remains a 2027+ story pending silicon refresh.
- **Design-workflow inversion:** architecture is built around the accelerator's supported opcodes first, then the math is optimized — inverse of the standard ML-research workflow but the only practical path through the HA SoC bottleneck.
- See [[../sources/tf-mlpnet-tiny-speech-separation-arxiv-2026]] and [[speech-enhancement-neural-networks]].

### Aizip: TinyML Platform for Hearing Devices (2026)
- Platform approach to running **AI noise reduction on standard hearing device hardware** — no custom NPU required
- Targets the "long tail" of devices that lack dedicated DNN accelerators
- Enables AI capabilities on commodity DSP chips through aggressive model optimization
- If successful, could democratize AI hearing features beyond Big 6 flagship products
- Relevant to OTC and lower-tier devices that use off-the-shelf processors

### Sonova Dual-Chip vs Demant Single-Chip
| Approach | Sonova (dual-chip) | Demant (single-chip) |
|----------|-------------------|---------------------|
| Architecture | Separate DSP + ML processor | Unified SoC |
| Advantage | Each chip optimized for its task | Simpler design, lower total power |
| Disadvantage | Higher component count, more power | ML and DSP compete for resources |
| Flexibility | Can upgrade one chip independently | Requires full chip revision for change |

## Latency Constraints
- Users perceive processing delay above ~10ms
- **1ms latency DNN** targets are being pursued for noise reduction blocks
- Causal (non-lookahead) architectures are required — no future audio frames
- This rules out most standard Transformer architectures without modification

## Training Data Scales
On-device models are typically trained in the cloud on massive datasets:
- **13.5M–22M sound scenes** reported by leading manufacturers
- Synthetic mixing of speech + noise to cover rare acoustic conditions
- Hearing aid microphone simulation to bridge lab-to-device gap
- **Emerging: AI-generated synthetic data** — Meta's April 2026 synthetic data distillation pipeline uses large models to generate training data for smaller edge models via a recursive improvement loop. This approach could dramatically expand hearing aid training corpora beyond the current 22M ceiling while sidestepping privacy constraints of real patient audio. See [[synthetic-data-for-hearing-ai]].

## Model Compression for On-Device Deployment

Getting capable models onto hearing aid chips requires aggressive compression (see [[model-compression]]):
- **Quantization:** INT8/INT4 standard; Google's TurboQuant (ICLR 2026) achieves 3-bit with zero accuracy loss — pushes the theoretical floor
- **Ternary (1.58-bit):** PrismML Ternary Bonsai (April 2026) demonstrates {-1, 0, +1} weight models — 9x memory reduction, eliminates multiplications entirely. An 8B model fits in 1.75 GB. If applied to hearing aid DNNs, could enable models in <250 KB with no-multiply inference. See [[model-compression]].
- **Knowledge distillation:** Large Transformer teachers compressed into compact CRN students
- **Pruning:** 50-90% weight sparsity achievable on speech enhancement tasks
- **NAS:** Automated architecture search for Pareto-optimal latency/accuracy/power tradeoffs

The combination of these techniques bridges the ~6 orders of magnitude gap between cloud training environments and hearing aid deployment targets. The trajectory from 3-bit (TurboQuant) to 1.58-bit (Ternary Bonsai) in the same month (April 2026) suggests sub-2-bit inference is converging rapidly.

### Compute-in-Memory + State Space Models (April 2026)
University of Michigan researchers (Nature Communications, DOI:10.1038/s41467-025-68227-w) demonstrated the **first mapping of state space models onto RRAM crossbar arrays** — compute-in-memory hardware where vector-matrix multiplication happens in the memory itself:
- **Eliminates the memory bandwidth bottleneck** that limits current hearing aid NPUs and DSPs
- Tungsten oxide memristors at different thicknesses encode different temporal decay rates
- Vector-matrix multiplication accuracy within **4.6 bits of ideal** — sufficient for audio tasks
- **Real-time processing** with dramatically reduced latency and power vs. conventional digital hardware
- Paper explicitly names **hearing aids** as a target application
- See [[compute-in-memory]] and [[state-space-models]] for detailed concept pages

Applied Brain Research validates SSMs in production with their TSP1 chip (under 30mW) running streaming speech-to-text, TTS, and speech-to-intent on-device. While 30mW exceeds hearing aid budgets, the trajectory points toward hearing-aid-compatible SSM hardware within the decade.

### On-Device Speech Recognition Approaching Cloud Parity (April 2026)
Adobe and Speechmatics demonstrated on-device speech-to-text for Premiere Pro that processes 1hr audio in 55 seconds (~65x real-time), within **5% of cloud accuracy**, and **12-16% better than Whisper** across 55+ languages. While running on laptop/desktop hardware (not hearing aid chips), this validates the trajectory: on-device models are closing the gap with cloud. The compression and optimization techniques used here are directly relevant to pushing speech models toward hearing aid deployment.

### Edge AI Audio Supply Chain Maturation (Embedded World 2026)
Three notable vendors showcased hearable-specific edge AI at Embedded World 2026:
- **Synaptics Astra SR80** — major semiconductor company (not a startup) entering hearable AI silicon
- **AONDevices** — always-on customizable edge AI speech enhancement
- **Aizip + PYOUR Audio** — tiny AI inference on standard microcontrollers without dedicated NPUs

This supply chain maturation means smaller OEMs can now ship AI-capable hearing devices without designing custom silicon, potentially democratizing AI hearing features beyond the Big 6. See also [[hearing-aid-chip-architectures]].

### Consumer-Medical Device Convergence (April 2026)
HHTM analysis documents the shrinking gap between consumer earbuds and medical hearing aids:
- Both categories now running on-device ML for noise reduction, scene classification, and adaptive processing
- Silicon capabilities converging: consumer audio chips and hearing aid SoCs approaching similar compute/power ratios
- Personalization algorithms represent the most defensible moat for hearing aid companies
- Supports the "middle squeeze" thesis in hearing aid pricing

### Fully Implantable CIs — Extreme Edge Constraint (April 2026)
Three companies are developing fully implantable cochlear implants with no external processor. Envoy Medical's Acclaim uses a piezoelectric incus sensor and a chest-implanted battery lasting 10-15 years. This represents the extreme frontier of edge AI: sub-microwatt inference budgets, no external update path, strict thermal limits under tissue, and novel input signals (ossicular vibration rather than acoustic microphone). CIM + SSM architectures are the most likely path to enabling AI in these devices. See [[envoy-medical]] and [[cochlear-implant-ai]].

## Emerging Capabilities
- **On-device learning / personalization:** Adapting to user preferences over time without cloud sync
- **Auditory attention decoding (AAD):** Using EEG/biosignals to steer beamforming toward attended speaker (see [[auditory-attention-decoding]])
- **Real-time translation:** Requires more compute than currently available on-chip
- **Target speaker extraction:** Identifying and extracting a specific speaker via pre-enrolled speaker embeddings — Hsu et al. (April 2026) achieved sub-5ms causal TSE for hearing assistive devices. Could be combined with AAD for brain-steered speaker selection.
- **Health monitoring:** Heart rate from in-ear sensors, stress detection — Apple AirPods Pro 3 now does PPG at 256 Hz. **Samsung Galaxy Buds** (April 2026) expanding to HRV and stress tracking via in-ear PPG — consumer earbuds converging on hearing aid health features.
- **Fall detection:** Via accelerometer + ML (shipping in some Starkey models)

## Related Pages
- [[dnn-architectures-hearing-aids]] — Detailed breakdown of DNN architectures used on these chips
- [[small-language-models-edge-ai]] — The model paradigm that makes on-device ML feasible
- [[speech-enhancement-neural-networks]] — Primary ML workload on hearing aid chips
- [[large-sensor-models]] — Future: pre-trained models distilled for on-device deployment
- [[auditory-attention-decoding]] — Next frontier for on-device intelligence
- [[cochlear-implant-ai]] — Parallel developments in cochlear implant processors; fully implantable CIs as extreme edge AI challenge
- [[envoy-medical]] — Acclaim fully implantable CI; sub-microwatt inference frontier
- [[world-models-hearing-ai]] — World models and continual learning for acoustic personalization
- [[audio-reasoning-chain-of-thought]] — Chain-of-thought reasoning for audio understanding
- [[model-compression]] — Quantization, distillation, pruning techniques for on-device deployment
- [[mixture-of-experts]] — MoE architecture for scene-specific expert routing on hearing aid chips
- [[compute-in-memory]] — CIM hardware paradigm eliminating memory bandwidth bottleneck
- [[state-space-models]] — SSMs as transformer/RNN alternative for streaming audio
- [[synthetic-data-for-hearing-ai]] — Synthetic data distillation for expanding training corpora

## Sources
- [Small Language Models Edge 2026](../../sources/small-language-models-edge-2026.md)
- [Large Sensor Models arXiv 2026](../../sources/large-sensor-models-arxiv-2026.md)
- [Wireless Hearables with Programmable Speech AI Accelerators](../../sources/wireless-hearables-programmable-speech-ai-accelerators-arxiv-2025.md) — Co-designed silicon for hearable speech AI
- [Aizip Tiny AI for Hearing Devices](../../sources/aizip-tiny-ai-hearing-devices-2026.md) — Platform approach for AI on standard hearing device hardware
- [Michigan CIM RRAM + SSM (Nature Communications 2026)](../../sources/michigan-compute-in-memory-rram-ssm-nature-2026.md) — First SSM-on-CIM mapping for edge AI
- [Applied Brain Research SSM Edge Audio](../../sources/applied-brain-research-ssm-edge-audio-2026.md) — Production SSMs for streaming audio on TSP1 hardware
- [Adobe + Speechmatics On-Device STT](../../sources/adobe-speechmatics-on-device-stt-april-2026.md) — Cloud-parity on-device speech recognition, 65x real-time, 55+ languages
- [Multi-Stage Low-Latency Enhancement for HAs](../../sources/multi-stage-low-latency-enhancement-ha-arxiv-2026.md) — Phase-aware multi-stage system within 5ms latency; head rotation integration
- [Edge AI Audio — Embedded World 2026](../../sources/edge-ai-audio-embedded-world-2026.md) — Synaptics SR80, AONDevices, Aizip+PYOUR supply chain maturation
- [HHTM: Convergence of AI, Audio, and Hearing Devices](../../sources/hhtm-convergence-ai-audio-hearing-devices-2026.md) — Consumer-medical device convergence analysis
