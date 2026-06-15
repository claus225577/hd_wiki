---
title: "Endpoint Anticipation for Low-Latency Spoken Dialogue"
type: source
source_type: arxiv-paper
arxiv_id: 2606.13450
authors: [Udupa et al.]
date_published: 2026-06-11
ingested: 2026-06-15
url: https://arxiv.org/abs/2606.13450
tags: [endpoint-detection, turn-taking, voice-agents, low-latency, conversational-ai, on-aid-assistants, auracast-coupled]
---

# Endpoint Anticipation for Spoken Dialogue (Udupa et al., June 2026)

## Bibliographic
- **Authors:** Udupa et al.
- **Posted:** 11 June 2026 (arXiv:2606.13450)
- **URL:** https://arxiv.org/abs/2606.13450

## Problem
Spoken-dialogue systems have a fixed budget between "user stops speaking" and "system responds." Most of that budget is consumed by endpoint detection waiting for silence to confirm the user is done. Anticipating the endpoint earlier reduces perceived latency without forcing the user to talk over an overeager bot.

## Contribution
Predicts speech endpoints from acoustic and lexical cues *before* the silence threshold elapses, allowing the response pipeline to start earlier and shave hundreds of milliseconds from turn-taking latency.

## Why It Matters for Hearing Aids
- The same latency math applies to **on-aid conversational assistants** (Apple AirPods + Siri, Phonak with companion app voice control, future Auracast-coupled "ask the room a question" UX).
- For hearing-aid wearers, turn-taking latency is doubly important: they already have audio-pipeline latency from DSP and from any DNN-based enhancement; adding conversational-AI latency on top pushes total round-trip out of natural-conversation range.
- Sits in the same low-latency-floor family as SB-RF, HALO, and the FPGA SE work — the field is converging on "every 10-50 ms matters" as the constraint.

## Open Questions
- Tradeoff curve: endpoint anticipation that fires too early creates barge-ins; too late wastes the gain. The user-perceived sweet spot is task-dependent.
- Composition with diarization and AAD — in multi-party scenes the "user stopped speaking" signal needs speaker disambiguation.

## Related Wiki Pages
- [[../wiki/concepts/turn-taking.md]]
- [[../wiki/concepts/low-latency-speech-enhancement.md]]
- [[../wiki/concepts/companion-phone-speech-pipeline.md]]
