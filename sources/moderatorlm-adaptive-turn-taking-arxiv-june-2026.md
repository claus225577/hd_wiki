---
title: "ModeratorLM: Adaptive Turn-Taking for Real-time Multi-Party Voice Agents"
type: source
date: 2026-06-11
ingested: 2026-06-14
authors: [Soumyajit Mitra, Prabhat Pandey, Abhinav Jain, Shanmukha Sahith, K V Vijay Girish]
publication: arXiv:2606.13544 (cs.CL / eess.AS), accepted Interspeech 2026
url: https://arxiv.org/abs/2606.13544
institution: Amazon
tags: [turn-taking, multi-party-conversation, voice-agent, speech-llm, streaming, role-conditioning, chain-of-thought, interspeech-2026, conversational-ai, hearing-ai-implications]
---

# ModeratorLM: Adaptive Turn-Taking for Real-time Multi-Party Voice Agents

## Metadata
- **Title:** Adaptive Turn-Taking for Real-time Multi-Party Voice Agents
- **Authors:** Soumyajit Mitra, Prabhat Pandey, Abhinav Jain, Shanmukha Sahith, K V Vijay Girish (Amazon)
- **arXiv:** 2606.13544
- **Submitted:** June 11, 2026
- **Accepted:** Interspeech 2026

## Method

ModeratorLM is a **chunk-wise streaming speech-LLM** voice agent designed for multi-party (three-or-more-speaker) conversations. Core architectural decisions:

- **Streaming chunk-wise inference** — the LLM consumes short audio chunks as they arrive, emitting a turn-taking decision (assistant should speak / continue listening) per chunk rather than waiting for endpoint detection.
- **Role-conditioned turn-taking** — the agent is conditioned on an explicit assistant role token (e.g., moderator, expert, listener) that shifts its threshold for taking the floor. Different roles imply different floor-claiming pragmatics.
- **Reasoning-enhanced variant** — a chain-of-thought variant emits a brief written analysis ("Speaker A is finishing a thought; Speaker B has not been asked a direct question; my role is moderator → take floor") before the binary speak/listen decision.
- **RolePlayConv dataset** — a large-scale synthetic multi-party spoken conversation corpus with diverse assistant roles, built specifically to train the role-conditioned head.

## Results

- **+40% turn-taking precision** over the strongest non-role-conditioned baseline.
- **>+70% turn-taking recall** — the larger jump, indicating the prior systems were systematically missing legitimate floor-opportunities.
- **Substantially reduced false-positive interruptions** — the agent stops talking over humans mid-utterance.
- Reasoning variant gives further gains on the hardest multi-party scenarios at the cost of higher per-chunk latency.

## Why This Matters for Hearing AI

### Multi-party is the #1 unsolved wearer pain point
The dominant lived complaint is not "I cannot follow one speaker" — modern DNN-based SE handles that well — it is **"I cannot follow the dinner conversation."** That is a multi-party turn-taking problem, not a SNR problem.

### Predictive vs reactive scene control
Today's hearing-aid scene-control stack (beamforming, gain ramping, attention steering) is **reactive** — it adapts after the speaker has already started. A turn-taking *predictor* opens the door to **predictive** steering: ramp gain on speaker B half a second before they take the floor, not 200 ms after. This is the same architectural shift as RIR conditioning made for dereverberation (see [[../sources/arxiv-2606-09557-rir-encoder-dereverb-khanagha-gerkmann-jun-2026]]) — give the network the answer to a question it was solving implicitly.

### A new "pragmatic primitive" layer in the SE stack
Signal → lexical → neural attention → effort → interactional (Pichora-Fuller WCA 2026) — see [[../wiki/concepts/communication-accessibility-metric]]. ModeratorLM operationalizes a **pragmatic primitive** sitting at the interactional layer: who has the floor, who is about to take it, who has been ignored. The dyadic-interaction-preservation thread (arXiv:2606.02185, 1 June 2026) is the diagnostic cousin; ModeratorLM is the generative cousin — same construct, different operation.

### Role conditioning maps onto hearing-aid wearer roles
The role-token mechanism transfers naturally to wearer-side use: "wearer is host," "wearer is invited guest," "wearer is the listener tonight." Each role implies different attention-steering and gain-ramp pragmatics. The same conditioning machinery that lets a voice agent be a moderator vs an expert lets a hearing aid be tuned for the wearer's social position in tonight's conversation.

### Companion-phone substrate, not on-chip
At chunk-wise streaming LLM scale, this runs on the **companion phone** today, not on a hearing-aid SoC. Maps onto the [[../wiki/concepts/companion-phone-speech-pipeline]] thesis: pragmatic-layer reasoning lives on the phone, low-latency acoustic steering on the device, both talking to each other.

## Open Questions for Hearing AI

- Does the role-conditioning head transfer to wearer-side personalization (host vs guest vs listener) or does it require retraining on hearing-impaired conversational data?
- What is the prediction *horizon* — does the system predict floor-claims early enough (say 300-500 ms) to drive predictive beamforming, or only at the boundary?
- How does turn-taking precision/recall translate to a wearer-side outcome metric — listening effort? conversation duration? voluntary disengagement?
- The synthetic RolePlayConv dataset is monolingual and unimpaired-speaker — does the model survive aging voices, hearing-loss-affected speech, and code-switched dinner-table conversations?

## Used In
- [[../wiki/concepts/turn-taking-prediction-hearing-ai.md]]
- [[../wiki/concepts/dyadic-interaction-preservation.md]]
- [[../wiki/concepts/communication-accessibility-metric.md]]
- [[../wiki/concepts/companion-phone-speech-pipeline.md]]
