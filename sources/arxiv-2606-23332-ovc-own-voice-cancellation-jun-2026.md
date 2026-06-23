---
title: "Don't Listen to Me: A Lightweight, Low-Latency Model for Own-Voice Cancellation in Far-Field Speech Enhancement"
type: source
source_type: arxiv-paper
arxiv_id: 2606.23332
authors: [Mads Østergaard, Alexander Neergaard Zahid, Karl Ulbæk, Andreas Hansen Bagge, Kenny Falkær Olsen, Rasmus Malik Høegh Lindrup]
date_published: 2026-06-22
ingested: 2026-06-23
url: https://arxiv.org/abs/2606.23332
tags: [own-voice-cancellation, ovc, own-voice-processing, ovp, ovd, speaker-extraction, td-speakerbeam, mamba, mingru, linear-rnn, far-field-speech-enhancement, low-latency, 2ms-algorithmic-latency, hearing-aids]
---

# arXiv:2606.23332 — Own-Voice Cancellation for Far-Field Speech Enhancement (Østergaard et al., Jun 2026)

## Bibliographic
- **Authors:** Mads Østergaard, Alexander Neergaard Zahid, Karl Ulbæk, Andreas Hansen Bagge, Kenny Falkær Olsen, Rasmus Malik Høegh Lindrup
- **Posted:** 22 June 2026 (arXiv:2606.23332, eess.AS)
- **URL:** https://arxiv.org/abs/2606.23332

## Problem
Far-field speech enhancement in conversational settings is repeatedly contaminated by the wearer's / device user's **own voice** — close-talking, high-SNR, structurally dominant, and almost always unwanted in the output stream (think transcript pipelines, conference-call audio, hearing-aid forward processing where the wearer's own voice is independently handled). Generic SE models trained on multi-talker corpora suppress *whichever* speaker the loss happens to penalize, not specifically the enrolled user. The complementary problem to **target speaker extraction (TSE)** is **target speaker removal** — given an enrolled-speaker embedding, the model must cancel that speaker while preserving everything else.

## Contribution
The paper introduces **Own-Voice Cancellation (OVC)** as a first-class enhancement objective:
- **Algorithmic latency: 2 ms.** Designed for streaming pipelines under hearing-aid-grade delay budgets.
- **Architecture: TD-SpeakerBeam baseline + Mamba-MinGRU masker variant.** The masker uses **Mamba blocks** for state-space temporal modelling combined with **MinGRU temporal mixing** — a lightweight recurrent companion that gives a different temporal-context profile from Mamba alone.
- **Linear-RNN auxiliary encoder.** Replaces the original ConvTasNet-based aux network used in TD-SpeakerBeam for producing the **enrolled-voice embedding** that conditions the masker. Linear-RNN aux is structurally cheaper and pairs naturally with the linear-time Mamba masker.
- **Metrics:** SDR (signal-domain) + predicted MOS (perceptual surrogate). The OVC framing is what's novel; the metrics are the standard SE evaluation pair.

## Why It Matters for Hearing AI

### From OVD/OVP state-machine flag to continuous SE conditioning signal
The Phonak / Sonova OVP feature and Oticon's analog OVD line are essentially **binary classifiers** wired to a state machine: detect that the wearer is speaking, then re-route processing (lower own-voice gain, switch to a phone-call program, etc.). OVC reframes the same enrolled-voice signature as **a continuous conditioning embedding** that drives a masker — the binary flag becomes a vector that an SE network can attend to, sample-by-sample.

This is the same move differentiable RIR encoders made for the room (Khanagha & Gerkmann, Jun 2026): stop treating an obvious axis as a discrete categorical that the network handles internally, and expose it as an explicit input the rest of the pipeline can read.

### Bridges existing hearing-aid OVP/OVD work to modern speaker-extraction architectures
- **Phonak OVP** (Sonova) and **Oticon OVD** have shipped for years as proprietary classifiers tied to product-specific state machines.
- **arXiv:2603.02724** (Single Microphone Own Voice Detection via Simulated Transfer Functions, March 2026) hit 80% real-device accuracy with a single in-canal mic and a sim-to-real bridge — pushing OVD into OTC / in-ear form factors.
- OVC (this paper) is the SE-stage counterpart: assuming an OVD-style enrolled-voice signature, run a Mamba-MinGRU masker conditioned on it to actively cancel rather than just flag.

The three points together form the natural OVP/OVD/OVC progression:
- **OVD** — *Is the wearer speaking?* (binary)
- **OVP** — *Re-process when wearer is speaking* (state machine + gain rules)
- **OVC** — *Continuously cancel the wearer from the far-field stream* (SE masker conditioned on enrolled embedding)

### 2 ms algorithmic latency is in HA territory
Most far-field speech enhancement and TSE work reports latency in the 20-50 ms range or ignores it. 2 ms algorithmic delay puts OVC in plausible reach of the same on-chip processing window as a hearing-aid forward path — well below the 10 ms clinical threshold and inside the streaming-pipeline budget for assistant-style applications.

### Linear-RNN aux encoder is the deployment-relevant detail
The original TD-SpeakerBeam used a ConvTasNet-based aux network for the embedding. Swapping in a **linear RNN** matches the Mamba masker's linear-time complexity profile and shrinks the aux-encoder footprint. The same architectural compression argument that made Mamba/SSMs interesting for hearing-aid SE in 2024-2025 now extends to the speaker-embedding extraction stage.

## Open Questions
- Real-device evaluation on hearing-aid mic geometries (the paper is far-field SE-framed, not HA-framed).
- Robustness to enrollment quality (does the embedding survive in-canal mic SNR conditions?).
- Param count / GMACs — the paper emphasises latency; on-chip deployment also needs the parameter envelope.
- Interaction with downstream room-aware processing (RIR-encoder conditioning) and band-axis SE (BASENet) — these are stackable in principle.
- Privacy framing: an enrolled-voice embedding stored on-device is a biometric template. Regulatory treatment of "voiceprint" for OVC processing is open.

## Cross-References
- **Prior OVD work:** [arxiv-2603-02724-own-voice-detection-simulated-tfs.md](arxiv-2603-02724-own-voice-detection-simulated-tfs.md) — Single-microphone OVD via simulated transfer functions; 80% accuracy on real HA recordings, March 2026
- **OEM OVP products:** Phonak Own Voice Processing (Sonova); Oticon Own Voice Detection — see entity pages `wiki/entities/phonak.md`, `wiki/entities/demant-oticon.md`, `wiki/entities/ws-audiology-signia.md` (Signia OVP)
- **Architectural neighbours:** TD-SpeakerBeam (Delcroix et al., 2020) — TSE baseline this paper inverts; Mamba family — see `wiki/concepts/mamba-architecture.md`; state-space models — see `wiki/concepts/state-space-models.md`
- **Related concept pages:** `wiki/concepts/speech-enhancement-neural-networks.md` (SE container); `wiki/concepts/dnn-architectures-hearing-aids.md` (architecture family); new candidate page `wiki/concepts/own-voice-processing.md` (consolidates OVD / OVP / OVC under a single concept)
- **Latency-floor companions:** [target-speaker-extraction-ultra-low-latency-2026.md](target-speaker-extraction-ultra-low-latency-2026.md) — sub-5 ms TSE (the dual to OVC); SB-RF one-step generative SE; HALO half-frame-rate SE
