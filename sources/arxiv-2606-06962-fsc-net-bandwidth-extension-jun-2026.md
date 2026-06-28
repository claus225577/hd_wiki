---
title: "FSC-Net: Integrating Fast Fourier Convolutions and Progressive Learning for Speech Bandwidth Extension"
type: source
source_type: paper-preprint
venue: arXiv eess.AS
arxiv_id: 2606.06962
authors: ["Xinan Chen", "et al."]
created: 2026-06-28
date: 2026-06
url: https://arxiv.org/abs/2606.06962
tags: [speech-enhancement, bandwidth-extension, fft-convolution, on-device-audio, june-2026]
---

# FSC-Net: Fast Fourier Convolutions + Progressive Learning for Speech Bandwidth Extension

## Citation
Chen, X. et al. (2026). *FSC-Net: Integrating Fast Fourier Convolutions and Progressive Learning for Speech Bandwidth Extension.* arXiv:2606.06962 [eess.AS]. https://arxiv.org/abs/2606.06962

## Key Idea
A lightweight neural model that reconstructs missing high-frequency content in narrow-band speech signals. Two architectural choices:
- **Fast Fourier Convolutions (FFC)** in the convolutional stack, giving each layer an implicit global receptive field across the frequency axis without inflating parameter count.
- **Progressive learning** schedule that grows the target bandwidth gradually during training, stabilising optimisation when extrapolating to unseen high-frequency bands.

## Why It Matters for Hearing AI
- **Telephony / streaming chain into hearing aids:** much of the speech a hearing-aid user receives is already band-limited (8 kHz codec, Bluetooth SCO/HFP, voice-over-IP). Restoring HF content *before* amplification is preferable to amplifying lost cues.
- **Dead-region masking:** for users with high-frequency sensorineural loss, bandwidth extension can be paired with frequency-lowering algorithms (linear frequency translation, non-linear frequency compression) to put restored content into audible bands.
- **Compute envelope:** FFC keeps the receptive-field-vs-parameter-count tradeoff favourable for on-device deployment, which is the binding constraint for in-ear DSPs (cf. `wiki/concepts/on-device-ml-hearing-aids.md`, `wiki/concepts/hearing-aid-chip-architectures.md`).

## Open Questions / Things to Watch
- Real-time latency and stability on streamed input (the paper's setup vs. a hearing-aid frame-rate budget of <10 ms).
- Interaction with downstream wide-dynamic-range compression (WDRC) — overly aggressive HF reconstruction can artefactually drive AGC.
- Hallucination risk in the HF band — same concern Shetu et al. 2606.02913 raise for generative SE.

## Cross-references
- `wiki/concepts/speech-enhancement-neural-networks.md`
- `wiki/concepts/companion-phone-speech-pipeline.md`
- `wiki/concepts/on-device-ml-hearing-aids.md`
- Related arXiv: `arxiv-2606-02913-generative-vs-discriminative-se-jun-2026.md` (hallucination tradeoff in generative SE)
