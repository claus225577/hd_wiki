---
title: Turn-Taking Prediction as a Pragmatic Primitive for Hearing AI
type: concept
created: 2026-06-14
updated: 2026-06-14
sources:
  - moderatorlm-adaptive-turn-taking-arxiv-june-2026.md
  - breaking-the-pair-speaker-switching-arxiv-june-2026.md
  - wca-2026-pichora-fuller-aram-glorig-may-26-2026.md
related:
  - dyadic-interaction-preservation.md
  - communication-accessibility-metric.md
  - companion-phone-speech-pipeline.md
  - auditory-attention-decoding.md
  - care-partner-dyad-models.md
  - listening-effort-evaluation.md
  - ../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md
tags: [turn-taking, multi-party-conversation, pragmatic-primitive, predictive-beamforming, voice-agents, speech-llm, role-conditioning, conversation, dyadic-interaction, interactional-layer]
---

# Turn-Taking Prediction as a Pragmatic Primitive for Hearing AI

A new processing/evaluation layer for hearing AI: **predicting who is about to take the conversational floor**, conditioned on roles, history, and acoustic signal. Distinct from voice-activity detection (binary, retrospective) and from auditory attention decoding (which voice the brain is locked onto). Operates at the **pragmatic** layer — the rules of conversation as a multi-party, role-structured social activity.

Catalysed by ModeratorLM (Mitra et al., arXiv:2606.13544, June 2026), a chunk-wise streaming speech-LLM voice agent that achieved +40% turn-taking precision and >70% recall using **role-conditioned** turn-taking on multi-party conversations.

## Why Hearing AI Needs This

### The unsolved wearer complaint
Modern DNN-based speech enhancement handles single-speaker-in-noise well. The dominant remaining complaint — **"I can hear the words but I can't follow the dinner"** — is fundamentally a multi-party turn-taking problem, not a SNR problem. The wearer is failing to track who is talking next, who deferred to whom, who got cut off.

### The reactive-to-predictive shift
| Today | Tomorrow |
|---|---|
| Beamforming locks on **after** the speaker has begun | Beamforming pre-ramps **before** the speaker begins |
| Gain ramps respond to detected onset | Gain ramps anticipate predicted onset |
| Attention steering follows the wearer's gaze + AAD | Attention steering predicts the likely next floor-claimant |

The same architectural shift that RIR-conditioning made for dereverberation (give the network the answer to a question it was solving implicitly — see [[room-aware-dereverberation]]) is available here: give the scene-control stack an explicit prediction of the next turn boundary, instead of letting it absorb that prediction silently into its weights.

## Where It Sits in the Evaluation / Processing Stack

Building on [[communication-accessibility-metric]]'s five-axis frame (signal × lexical × neural × effort × interactional), turn-taking prediction is a **subprimitive** of the interactional layer:

| Sub-layer | Primitive | Status |
|---|---|---|
| Dyadic structure preservation | Speaker-switch test / DDM | Diagnostic — see [[dyadic-interaction-preservation]] |
| **Turn-taking prediction** | **Role-conditioned next-floor classifier** | **Generative — ModeratorLM, June 2026** |
| Repair detection | Repair-token classifier | Not yet built |
| Conversation duration | Voluntary disengagement telemetry | Not yet built |

The dyadic-interaction-preservation thread is a *diagnostic* of whether a system has internalized interactional structure. Turn-taking prediction is the *generative* counterpart — the same construct, used to act rather than to evaluate.

## Role Conditioning

ModeratorLM's role token (moderator / expert / listener / etc.) is the architecturally interesting move. The same mechanism transfers naturally to wearer-side hearing AI:

- **Wearer as host:** higher floor-claim sensitivity, more aggressive predictive gain to inbound speakers
- **Wearer as invited guest:** more conservative steering, smaller gain ramps until directly addressed
- **Wearer as quiet listener:** prioritize comprehension over interaction, longer dwell on each speaker

Role can be set explicitly by the wearer ("dinner with strangers / dinner with family / work meeting") or inferred from the conversation history and the companion phone's calendar/contacts context. This is the natural locus for personalization at the interactional layer.

## Substrate: Where It Runs

At chunk-wise streaming speech-LLM scale, ModeratorLM-class systems run on the **companion phone**, not on the hearing-aid SoC. This fits the existing [[companion-phone-speech-pipeline]] architecture:

- **On phone:** speech-LLM, turn-taking predictor, role conditioning, conversation memory
- **On device:** low-latency beamforming, gain ramping, attention steering — driven by predictions arriving from phone
- **Bidirectional link:** Auracast / LE Audio carrying both audio and the metadata of "next-turn probability over identified speakers"

The latency budget for a *prediction* is meaningfully looser than for an acoustic decision — predictions are useful even at 300-500 ms, where reactive decisions need <30 ms. That gap is exactly what makes companion-phone-side prediction practically deployable today.

## Open Research Questions

- What is the **horizon** of next-turn prediction in real multi-party conversation, and how much of that horizon needs to be ≥300 ms for the predictions to drive predictive beamforming usefully?
- Does role-conditioned turn-taking transfer to wearer-side personalization with little retraining, or are wearer roles (host/guest/listener) a different distribution from voice-agent roles (moderator/expert)?
- Synthetic-data effect: ModeratorLM is trained on RolePlayConv, a synthetic monolingual unimpaired-voice corpus. Does it survive aging voices, hearing-impaired speech, and code-switched conversation?
- What is the **outcome metric** for "good turn-taking" from the wearer's side? Listening effort delta? Conversation duration? Voluntary disengagement frequency? The interactional-layer evaluation primitive for this is still open — see [[communication-accessibility-metric]].
- Does combining a turn-taking *predictor* on the phone with an attention *decoder* on the device (AAD; see [[auditory-attention-decoding]]) yield additive benefit, or do they encode redundant signal?

## Related Pages
- [[dyadic-interaction-preservation]] — diagnostic cousin; same interactional construct, evaluative rather than generative
- [[communication-accessibility-metric]] — the five-axis frame; turn-taking prediction sits inside the interactional axis
- [[companion-phone-speech-pipeline]] — substrate this runs on; predictions feed the on-device acoustic stack
- [[auditory-attention-decoding]] — adjacent primitive on the brain-side; turn-taking is on the conversation-side
- [[care-partner-dyad-models]] — dyad-level modeling is the two-party limit case of multi-party turn-taking
- [[listening-effort-evaluation]] — candidate downstream outcome metric for turn-taking-driven steering
- [[../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026]] — the umbrella synthesis the pragmatic primitive plugs into as the generative side of the interactional axis

## Sources
- [ModeratorLM: Adaptive Turn-Taking for Real-time Multi-Party Voice Agents (arXiv:2606.13544, June 2026)](../../sources/moderatorlm-adaptive-turn-taking-arxiv-june-2026.md) — primary source; the +40% precision / >70% recall result, role-conditioning mechanism, RolePlayConv dataset.
- [Nilabh & Sharma — Breaking the Pair (arXiv:2606.02185, June 2026)](../../sources/breaking-the-pair-speaker-switching-arxiv-june-2026.md) — diagnostic counterpart at the same interactional layer.
- [WCA 2026 Pichora-Fuller Aram Glorig Award Lecture (May 2026)](../../sources/wca-2026-pichora-fuller-aram-glorig-may-26-2026.md) — the interactional layer is named.
