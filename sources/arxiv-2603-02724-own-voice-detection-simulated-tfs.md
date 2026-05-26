---
title: "Single Microphone Own Voice Detection based on Simulated Transfer Functions for Hearing Aids"
url: https://arxiv.org/abs/2603.02724
date: 2026-03
type: research-paper
venue: arXiv
arxiv_id: 2603.02724
tags: [own-voice-detection, ovpl, occlusion, hearing-aid, single-microphone, simulated-transfer-functions, sim-to-real, test-time-adaptation, deployment]
---

# arXiv:2603.02724 — Single Microphone Own Voice Detection via Simulated Transfer Functions

## Key Facts

- **Venue:** arXiv preprint (eess.AS), March 2026
- **ID:** 2603.02724
- **Problem:** Detecting when the hearing-aid wearer is the one speaking, from a single in-canal microphone signal
- **Method:** Train on simulated own-voice transfer functions, deploy on real HA recordings; add a lightweight test-time feature-compensation step to close the sim-to-real gap
- **Headline number:** **80% accuracy on real HA recordings with no fine-tuning**
- **Why one mic matters:** Multi-mic own-voice detection is established; doing it with a single mic opens the door to in-ear / OTC form factors that don't have outward-facing mics.

## Why It Matters

Own-voice detection (OVD) sits underneath three OEM-critical features:

1. **Own Voice Processing (OVPL)** — the algorithm that suppresses the wearer's voice from amplification to combat the occlusion effect. Sonova/Phonak built a whole differentiator around this; Oticon, Starkey, GN have analogues.
2. **Conversational AI in hearings aids** — figuring out when to trigger "you are speaking, don't transcribe / route differently."
3. **Telephony / Bluetooth voice pickup** — wearer-vs-environment discrimination for call quality.

The historical blocker for high-quality OVD has been **labeled data on real devices**. This paper proposes a sim-to-real path: simulate the transfer functions of speech reaching the in-canal mic, train on the simulation, then patch the gap at deployment with lightweight test-time feature compensation. The 80% no-fine-tune number is the contribution worth tracking.

## Architectural Position in the Wiki

Lands cleanly in the **own-voice-processing** / **occlusion-management** neighborhood. Companion to existing OVPL coverage on Sonova / Phonak product pages.

Pairs naturally with `arxiv-2603-07471-lightweight-se-adaptation.md` (low-rank SE adaptation, ingested today): both share the architectural philosophy that the shipping model is fixed and the gap to real-world performance is closed by a lightweight test-time delta. Worth a future synthesis page on "test-time adaptation patterns for hearing-aid ML."

## Quoted Numbers

- Real-device accuracy: **80%** with **no fine-tuning**
- Microphone count: **1** (single in-canal)
- Released: **March 2026**

## Open Questions for Wiki Follow-Up

- Accuracy vs. SNR and wearer (the abstract's 80% is presumably a single headline number)
- Latency / compute cost of the test-time feature compensation step
- Whether the simulated transfer functions transfer across HA form factors (RIC vs ITE vs OTC earbud) without retraining

## Sources

- arXiv abstract: https://arxiv.org/abs/2603.02724
- PDF: https://arxiv.org/pdf/2603.02724
