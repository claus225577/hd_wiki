---
title: Own-Voice Processing — OVD, OVP, OVC
type: concept
created: 2026-06-23
updated: 2026-06-23
sources:
  - arxiv-2606-23332-ovc-own-voice-cancellation-jun-2026.md
  - arxiv-2603-02724-own-voice-detection-simulated-tfs.md
related:
  - speech-enhancement-neural-networks.md
  - dnn-architectures-hearing-aids.md
  - mamba-architecture.md
  - state-space-models.md
  - on-device-ml-hearing-aids.md
  - companion-phone-speech-pipeline.md
  - ../entities/phonak.md
  - ../entities/demant-oticon.md
  - ../entities/ws-audiology-signia.md
tags: [own-voice, ovd, ovp, ovc, occlusion, speaker-extraction, td-speakerbeam, mamba, mingru, hearing-aid-fundamentals, biometric-template]
---

# Own-Voice Processing — OVD, OVP, OVC

The cluster of hearing-aid algorithms that operate specifically on the wearer's own voice. Three related but architecturally distinct primitives sit on a single axis from binary classification → state-machine control → continuous SE conditioning.

## The Three Primitives

| Acronym | What it does | Output | Typical implementation |
|---|---|---|---|
| **OVD — Own-Voice Detection** | Detects whether the wearer is currently speaking | Binary flag (with confidence) | Single- or multi-mic classifier |
| **OVP — Own-Voice Processing** | Re-routes gain / program / streaming when wearer is speaking | Categorical program switch + per-band gain changes | State machine driven by OVD |
| **OVC — Own-Voice Cancellation** | Continuously cancels the wearer's voice from the far-field stream | Enhanced audio with wearer suppressed | Speaker-extraction-style masker conditioned on enrolled-voice embedding |

## Why It Matters
- **Occlusion management.** When the wearer speaks, bone-conducted self-voice combined with vent-leaked amplified self-voice produces the "barrel-in-head" complaint that drives a large fraction of OEM dissatisfaction. OVP suppresses or re-shapes the amplified component; OVC offers the same intervention from the SE side.
- **Telephony / call routing.** OVD triggers phone-call programs, mic-switching for outbound audio, and Auracast pickup decisions.
- **Conversational AI in hearables.** Knowing whether the wearer or an interlocutor is speaking gates transcription, intent capture, and assistant invocation.
- **Privacy / biometric.** OVC requires a stored enrolled-voice embedding — a biometric template subject to consent and regulatory framing.

## OEM Implementations
- **Phonak / Sonova — Own Voice Processing (OVP).** Shipped 2018+ on Marvel/Paradise/Lumity/Sphere generations. Two-microphone classifier feeds a dedicated own-voice program. See `wiki/entities/phonak.md`.
- **Oticon — Own Voice Detection (OVD).** Analogous classifier in the Demant / Oticon product stack. See `wiki/entities/demant-oticon.md`.
- **Signia / WS Audiology — Own Voice Processing.** ML classifier separating wearer's voice from environmental sound in real time. See `wiki/entities/ws-audiology-signia.md`.
- **GN / Starkey** — analogous own-voice handling under different product names.

All shipping OEM implementations to date are **OVD + OVP**: binary classifier + state machine. OVC as a continuous SE conditioning primitive is research-stage as of mid-2026.

## OVD — Sim-to-Real Single Mic (Mar 2026)
[arxiv-2603-02724-own-voice-detection-simulated-tfs.md](../../sources/arxiv-2603-02724-own-voice-detection-simulated-tfs.md) — March 2026 arXiv preprint. Trains an OVD classifier on **simulated own-voice transfer functions**; deploys on real hearing-aid recordings with a lightweight test-time feature-compensation step. Headline: **80% accuracy on real HA recordings with no fine-tuning**, using a **single in-canal microphone**. The one-mic constraint matters because it opens OVD to OTC / in-ear earbud form factors that don't have outward-facing mics.

## OVC — From Flag to Conditioning Signal (Jun 2026)
[arxiv-2606-23332-ovc-own-voice-cancellation-jun-2026.md](../../sources/arxiv-2606-23332-ovc-own-voice-cancellation-jun-2026.md) — Østergaard, Neergaard Zahid, Ulbæk, Hansen Bagge, Falkær Olsen, Lindrup, **22 June 2026**. Introduces **Own-Voice Cancellation (OVC)** as a first-class enhancement objective: remove an enrolled speaker from noisy multi-speaker far-field audio while preserving other speech.

**Architecture:**
- **Baseline:** TD-SpeakerBeam (Delcroix et al., 2020) — the canonical target-speaker-extraction backbone. OVC inverts the TSE objective: instead of *keep* the enrolled speaker, *cancel* them.
- **Masker:** Mamba-MinGRU variant — Mamba blocks for state-space temporal modelling combined with MinGRU temporal mixing for a complementary recurrent context profile.
- **Auxiliary encoder:** **Linear-RNN aux network** replaces the original ConvTasNet-based aux used in TD-SpeakerBeam for producing the enrolled-voice embedding. Linear-RNN aux matches the linear-time complexity profile of the Mamba masker.

**Metrics:** SDR + predicted MOS.

**Headline operational constraint: 2 ms algorithmic latency** — inside the streaming and hearing-aid latency budgets.

### The conceptual shift
OVD/OVP treat own-voice as a **discrete categorical** the device handles via a hand-designed state machine. OVC treats it as a **continuous conditioning embedding** that an SE masker reads sample-by-sample. The same enrolled-voice signature drives both, but the consumer architecture differs:

- **OVP (today):** wearer-voice classifier → state-machine branch → program change.
- **OVC (this paper):** wearer-voice embedding → SE masker → continuous suppression.

This is the same move that differentiable RIR encoders made for the room (Khanagha & Gerkmann, June 2026, `room-aware-dereverberation.md`): stop treating an obvious axis as an internal categorical, expose it as an explicit input the rest of the pipeline can read.

## The OVD → OVP → OVC Progression

| Stage | Question answered | Output type | Plumbing |
|---|---|---|---|
| OVD | Is the wearer speaking? | Binary | Single classifier |
| OVP | Re-process when wearer speaks | Program switch + gain rules | State machine on OVD output |
| OVC | Continuously cancel wearer from far-field | Sample-by-sample masked audio | SE masker conditioned on enrolled embedding |

OVC subsumes OVD in the sense that an OVC masker conditioned on a confident enrolled-voice embedding implicitly contains the OVD signal. In practice the three primitives are likely to coexist on-device: OVD as a cheap upstream gate, OVP for fast program-level intervention, OVC for fine-grained continuous suppression in streaming pipelines.

## Open Questions
- **On-chip cost for OVC.** The Østergaard et al. paper reports 2 ms algorithmic latency but not the parameter / GMACs envelope. Mamba + linear-RNN aux is favourable in principle but the deployable footprint is the open number.
- **Enrolment workflow.** OVC requires an enrolled-voice embedding. Does the fitting workflow include a voice-capture step? Re-enrolment cadence? Cross-device portability?
- **Biometric / privacy regulation.** A stored voiceprint is a biometric template under GDPR / HIPAA / CCPA framings. On-device only? Encrypted at rest? Right-to-delete?
- **Multi-mic vs single-mic.** OVD has a sim-to-real single-mic result (Mar 2026); OVC as published is far-field-mic-array-flavored. Single-mic OVC is the OTC-relevant variant.
- **Interaction with band-axis SE.** BASENet-style band-axis encoding (BASENet, Jun 10 2026) and OVC conditioning are stackable in principle — band-axis tokens conditioned on enrolled-voice embedding. Not built.
- **Interaction with FxLMS-stage DSP.** OVC sits downstream of feedback cancellation and vent EQ. Both stages now have differentiable formulations (DDSP-EQ for FxLMS, neural DFC-IL for feedback). Joint training across the stack is the unbuilt move.

## Related Pages
- [[speech-enhancement-neural-networks]] — OVC is the SE-side framing of own-voice
- [[dnn-architectures-hearing-aids]] — TD-SpeakerBeam, Mamba, MinGRU, linear-RNN architecture family
- [[mamba-architecture]] — state-space primitive used in the OVC masker
- [[state-space-models]] — broader SSM family
- [[on-device-ml-hearing-aids]] — deployment substrate
- [[companion-phone-speech-pipeline]] — likely first home for OVC in production
- [[../entities/phonak]] — Phonak OVP
- [[../entities/demant-oticon]] — Oticon OVD
- [[../entities/ws-audiology-signia]] — Signia OVP

## Sources
- [Østergaard et al. — Don't Listen to Me: OVC (arXiv:2606.23332, Jun 2026)](../../sources/arxiv-2606-23332-ovc-own-voice-cancellation-jun-2026.md) — introduces OVC as a first-class objective; 2 ms algorithmic latency; Mamba-MinGRU masker; linear-RNN aux encoder
- [Single-Mic OVD via Simulated Transfer Functions (arXiv:2603.02724, Mar 2026)](../../sources/arxiv-2603-02724-own-voice-detection-simulated-tfs.md) — 80% accuracy on real HA recordings, no fine-tuning, single in-canal mic
