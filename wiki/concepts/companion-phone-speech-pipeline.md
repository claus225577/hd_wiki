---
title: Companion-Phone Speech Pipeline
type: concept
created: 2026-05-17
updated: 2026-05-17
sources: [diffvqe-diffusion-aec-arxiv-may-2026.md, qvac-medpsy-edge-medical-llm-may-2026.md, samsung-galaxy-s26-audio-eraser-realtime-2026.md, adobe-speechmatics-on-device-stt-april-2026.md, airpods-hearing-aid-country-expansion-may-2026.md]
related: [speech-enhancement-neural-networks.md, llm-based-speech-enhancement.md, on-device-ml-hearing-aids.md, medical-domain-edge-llms.md, auracast-bluetooth-le-audio.md, linguistic-hallucination-speech-enhancement.md, ../entities/apple-hearing-features.md]
tags: [companion-phone, le-audio, auracast, voip, speech-enhancement, generative-se, trust-calibration, off-device-ai, edge-ai, telephony]
---

# Companion-Phone Speech Pipeline

The audio pipeline running on the listener's paired smartphone (or, increasingly, a paired watch/wearable companion) that **delivers cleaned, enhanced, or generated audio to the hearing aid** over Bluetooth LE Audio. Distinct from on-chip hearing-aid processing, which is bounded by HA SoC power budgets. The companion-phone tier has roughly **four orders of magnitude more compute** available, and that ratio is widening.

## Why This Matters

For decades the canonical hearing-aid signal path was: microphone → DSP/DNN on hearing-aid SoC → receiver. The companion phone was a passive accessory for fitting controls and program switching.

That assumption no longer holds:

1. **Phone-side audio enhancement is shipping.** Microsoft Teams runs DeepVQE-class AEC + denoising on its desktop/mobile pipelines. iOS-VoIP and Android telephony stacks invoke increasingly sophisticated speech enhancement. Samsung Galaxy S26's Audio Eraser performs real-time generative SE on consumer audio.
2. **LE Audio delivers the cleaned bitstream to the hearing aid.** Once a phone has produced cleaned speech, low-energy Bluetooth audio (and Auracast) makes the handoff to a HA receiver routine.
3. **Generative SE is leaving the lab.** DiffVQE (May 2026), DriftSE (May 2026), predictive-generative drift decomposition (May 2026), and the broader single-step generative-SE wave have collapsed the inference-cost gap that previously kept diffusion off-line.

When the audio arriving at the hearing aid has already been generatively cleaned upstream, **the on-chip DSP's role changes**.

## The Trust-Calibration Layer (Unbuilt)

Today the hearing aid treats its analog mic input as ground truth. With a companion-phone pipeline delivering generatively enhanced audio, the on-chip DSP is processing a signal that may have been **synthetically reconstructed** at the phoneme level.

This raises a hearing-aid-specific problem the audio-research community has not framed:

- **Faithfulness.** L3-SE (Wang et al., May 2026) showed LM-based SE can produce "perceptually plausible yet linguistically incorrect" outputs. A hearing-aided listener has no acoustic reference signal to verify.
- **Modality drift.** Phone-pipeline enhancement is optimized for VoIP and content quality, not for the specific acoustic-spectral targets a hearing-impaired listener's prescription expects.
- **Mode arbitration.** When the same audio is partially captured by the HA's own mics (e.g., a face-to-face conversation accidentally being live-streamed via a phone in front of the speaker) and partially delivered via LE Audio, the on-chip DSP must decide which source to trust at the millisecond level.

A **trust-calibration metric** for upstream-cleaned audio is currently undefined. PESQ / STOI / HASPI evaluate intelligibility of a single signal but do not score the *fidelity-to-truth* of a generative reconstruction.

## Workload Map

| Layer | Hardware | Workload examples | Latency budget |
|-------|----------|--------------------|----------------|
| HA SoC | µW DSP + small DNN | Beamforming, gain shaping, scene classification, noise reduction | 1–10 ms |
| Phone | A-series / Snapdragon-class | VoIP AEC, generative SE, voice isolation, LLM transcription | 20–200 ms |
| Cloud | Server | Reference batch jobs, fitting telemetry analytics | seconds |

The middle tier is where DiffVQE-class systems will deploy. The hearing aid is downstream of it.

## Implications for HA OEM R&D

1. **Two-tier evaluation.** Outcome metrics need to specify whether the audio reaching the aid was enhanced upstream. Per-tier metrics will diverge.
2. **Pipeline-mode awareness.** The HA must know whether incoming audio is raw, lightly cleaned, or generatively reconstructed — and adjust its own compensation accordingly.
3. **Companion app as an SE host.** OEM companion apps have historically been thin shells (fitting controls + scene labels). The next product-strategy frontier is whether to run OEM-controlled SE on the phone (controlling the prior distribution) or accept platform-supplied SE (Teams, Zoom, iOS) and arbitrate at the aid.
4. **OEM-vs-platform divide.** Apple controls the AirPods Pro 2/3 phone-pipeline path end-to-end; medical-device OEMs do not. This is structurally analogous to the Apple-Health-vs-third-party-wearable dynamic.

## Related Pages
- [[speech-enhancement-neural-networks]] — the SE architectures running upstream
- [[llm-based-speech-enhancement]] — LM-based variants and their failure modes
- [[linguistic-hallucination-speech-enhancement]] — the faithfulness gap
- [[medical-domain-edge-llms]] — non-SE companion-phone workloads (counseling, triage)
- [[on-device-ml-hearing-aids]] — the on-chip tier this concept contrasts with
- [[auracast-bluetooth-le-audio]] — the handoff substrate
- [[../entities/apple-hearing-features]] — Apple's end-to-end-controlled instance of this pipeline

## Sources
- [DiffVQE — Hybrid Diffusion Voice Quality Enhancement (arXiv:2605.08189, May 2026)](../../sources/diffvqe-diffusion-aec-arxiv-may-2026.md) — flagship example of next-gen companion-tier SE
- [QVAC MedPsy on-device medical LLM (Tether, May 2026)](../../sources/qvac-medpsy-edge-medical-llm-may-2026.md) — non-SE workload on the same substrate
- [Samsung Galaxy S26 Audio Eraser real-time SE (2026)](../../sources/samsung-galaxy-s26-audio-eraser-realtime-2026.md) — consumer-grade generative SE shipping at phone tier
- [Adobe + Speechmatics on-device STT (April 2026)](../../sources/adobe-speechmatics-on-device-stt-april-2026.md) — adjacent workload on the same tier
- [Apple AirPods hearing-aid country expansion (May 2026)](../../sources/airpods-hearing-aid-country-expansion-may-2026.md) — vertically-integrated instance of the pipeline
