---
title: Active Noise Cancellation (ANC) in Hearing Devices
type: concept
created: 2026-04-23
updated: 2026-05-06
sources: [orka-o1-pro-bose-anc-awe-2026.md, anc-open-ear-smart-glasses-cmu-2026.md, qualcomm-s5-s3-gen3-sound-platforms-2026.md, e2e-cfg-transformer-anc-yang-arxiv-2026.md]
related: [speech-enhancement-neural-networks.md, dnn-in-hearing-aids.md, on-device-ml-hearing-aids.md, ../entities/orka-bose-partnership.md, hearing-aid-market-dynamics.md, hearing-aid-chip-architectures.md]
tags: [active-noise-cancellation, anc, smart-glasses, hearing-aids, dual-layer-noise-management, open-ear, end-to-end-control-filter]
---

# Active Noise Cancellation (ANC) in Hearing Devices

Active noise cancellation uses anti-phase audio signals to physically cancel environmental noise before it reaches the listener. ANC is entering the hearing aid and hearables space as a complement to computational (DNN-based) noise reduction, creating a **dual-layer noise management paradigm**.

## How ANC Works

1. **Reference microphone(s)** capture environmental noise
2. **Signal processing** generates an anti-phase (inverted) copy of the noise
3. **Speaker/receiver** plays the anti-phase signal, destructively interfering with incoming noise
4. Result: reduced perceived noise level, especially in low frequencies (100–1000 Hz)

ANC is most effective for:
- **Stationary, low-frequency noise:** Traffic, HVAC, airplane cabin, crowd rumble
- **Predictable spectral content:** Steady-state noise is easier to cancel than transient sounds

ANC is less effective for:
- **High-frequency noise:** Wavelengths too short for reliable cancellation
- **Transient sounds:** Sudden noises arrive before the cancellation signal can be generated
- **Open-ear form factors:** Without a sealed ear canal, cancellation must occur in free-field conditions

## ANC in Hearing Aids: Dual-Layer Paradigm

### Orka O1 Pro: First ANC RIC Hearing Aid (April 2026)

The Orka O1 Pro, powered by Bose QuietControl ANC technology, introduced the first RIC hearing aid with active noise cancellation (AWE 2026):

- **Physical layer (ANC):** Cancels low-frequency environmental noise
- **Computational layer (DNN):** Neural network handles mid/high-frequency noise reduction, speech enhancement, scene classification
- **Result:** Two complementary noise reduction mechanisms working simultaneously

This dual-layer approach is significant because:
- ANC handles noise that DNN struggles with (very low frequencies, steady-state broadband)
- DNN handles noise that ANC struggles with (non-stationary, speech-shaped, high-frequency)
- Combined, they could achieve noise reduction levels neither achieves alone

## ANC on Open-Ear Smart Glasses (April 2026)

Yuan, Liu et al. (CMU, arXiv:2604.05519) demonstrated the **first real-time ANC for open-ear smart glasses**:

- **9.6 dB noise reduction** in the 100–1000 Hz range
- **8 distributed microphones** around the glasses frame for spatial noise estimation
- **Open-ear form factor:** No ear canal occlusion — fundamentally harder than in-ear ANC
- Effective band: 100–1000 Hz (low-frequency environmental noise)

### Why Open-Ear ANC Matters for Hearing

- **Alternative to occluding devices:** Many hearing aid users dislike the "plugged ear" feeling (occlusion effect); open-ear ANC could provide noise reduction without occlusion
- **Smart glasses as hearing platform:** Extends hearing assistance to a new form factor — glasses with spatial audio, ANC, and potentially DNN enhancement
- **Distributed mic array:** 8 microphones enable spatial filtering impossible with hearing aid mic configurations (typically 2 per ear)
- **Complements hearing aid wear:** Users could wear open-ear smart glasses with ANC alongside hearing aids for additional environmental noise reduction

## ANC vs DNN Noise Reduction

| Dimension | ANC (Physical) | DNN (Computational) |
|-----------|---------------|-------------------|
| Mechanism | Anti-phase cancellation | Neural mask/reconstruction |
| Best for | Low-frequency, stationary noise | Non-stationary, speech-shaped noise |
| Latency | Sub-millisecond (analog circuits) | 1–10 ms (inference time) |
| Frequency range | 100–1000 Hz typical | Broadband (up to Nyquist) |
| Power cost | Moderate (analog + DSP) | Moderate-high (neural inference) |
| Adaptability | Limited (noise path must be stable) | High (learned from diverse training data) |
| Form factor | Requires sealed cavity (in-ear) or distributed mics (open-ear) | Works with any mic configuration |

## E2E-CFG: Unsupervised Transformer ANC (May 2026)

Yang et al. (arXiv:2605.00494, 1 May 2026) propose **End-to-End Control-Filter Generation (E2E-CFG)**: a transformer that **directly generates the time-domain ANC control filter** in an **unsupervised** manner, trained on accumulated error signals in a fully differentiable loop.

- **Departure from GFANC.** Generative Fixed-Filter ANC predicts weights for a bank of sub-filters, then reconstructs a control filter — a decomposition–reconstruction pipeline that accumulates error. E2E-CFG removes the decomposition entirely.
- **No labeled data required.** The unsupervised objective is the running ANC error itself, eliminating the dependence on (noise, ideal-filter) supervision pairs that hampers many ML-ANC approaches.
- **Better adaptability across noise types** validated on real-recorded noise in simulation.
- **Hearing-device implication:** Adaptive feedback cancellation, occlusion compensation, and in-canal active noise control are all members of the ANC family. An unsupervised end-to-end approach is a candidate for the next generation of feedback-management algorithms in vented hearing-aid fits.
- **Caveat:** Hearing-aid ANC needs sub-millisecond loops at the analog/digital boundary. The transformer must be aggressively distilled (or replaced with linear-attention / SSM surrogates) to ship on a hearing-aid SoC.

## Qualcomm S5/S3 Gen 3: Transformer-Based ANC (April 2026)

Qualcomm's S5 and S3 Gen 3 Sound Platforms represent a milestone for neural ANC in consumer devices:
- **Transformer-based noise cancellation** at **sub-3ms latency** — first commercial deployment of transformer architecture for real-time ANC
- Shipping in premium TWS (true wireless stereo) earbuds from multiple OEMs
- **Sub-3ms inference** in a battery-powered earbud demonstrates that transformer architectures can meet hearing aid latency constraints — previously considered too compute-heavy
- Qualcomm is the dominant chipmaker for Android TWS earbuds, giving this platform broad market reach
- **Technology transfer implications:** Compression techniques used to fit transformers on TWS platforms could be applied to hearing aid DNN systems
- Consumer TWS at sub-3ms sets a performance baseline that hearing aid users will increasingly expect

## Market Implications

- **Consumer expectation transfer:** AirPods Pro and consumer earbuds have made ANC an expected feature; hearing aid users may increasingly expect similar noise reduction
- **Bose partnership model:** Orka licensing Bose ANC technology shows consumer audio companies bringing ANC expertise to hearing aids — a technology partnership path
- **Competitive pressure:** As ANC becomes available in $200 consumer earbuds, prescription hearing aids at $4,000+ need to match or exceed noise management capabilities

## Open Questions

- Can ANC and DNN inference share the same compute/power budget on a hearing aid chip?
- Does ANC introduce artifacts (anti-noise residuals) that interfere with speech enhancement DNN?
- Will open-ear ANC (smart glasses, open-fit hearing aids) achieve sufficient reduction to be clinically meaningful?
- How does ANC interact with hearing loss compensation (frequency-dependent gain)?

## Related Pages
- [[speech-enhancement-neural-networks]] — DNN-based noise reduction, the computational complement to physical ANC
- [[dnn-in-hearing-aids]] — How DNN and ANC form the dual-layer paradigm
- [[on-device-ml-hearing-aids]] — Hardware constraints for running both ANC and DNN inference
- [[orka-bose-partnership]] — First ANC RIC hearing aid (Orka O1 Pro with Bose)
- [[hearing-aid-market-dynamics]] — Consumer expectation transfer from ANC earbuds to hearing aids

## Sources
- [Orka O1 Pro Bose ANC](../../sources/orka-o1-pro-bose-anc-awe-2026.md) — First ANC RIC hearing aid
- [Real-Time ANC for Open-Ear Smart Glasses (CMU)](../../sources/anc-open-ear-smart-glasses-cmu-2026.md) — 9.6 dB reduction, 8 distributed mics
- [Qualcomm S5/S3 Gen 3 Sound Platforms](../../sources/qualcomm-s5-s3-gen3-sound-platforms-2026.md) — Transformer-based ANC at sub-3ms, shipping in premium TWS
- [E2E-CFG: Transformer End-to-End Control Filter Generation for ANC (Yang et al., 2026)](../../sources/e2e-cfg-transformer-anc-yang-arxiv-2026.md) — Unsupervised transformer that generates control filters directly from accumulated error
