---
title: Salience-Aware Gain
type: concept
created: 2026-06-28
updated: 2026-06-28
sources: [arxiv-2606-26083-voice-ai-hears-not-listens-jun-2026.md]
related: [vocal-affect-paralinguistics-hearing-ai.md, joint-se-wdrc-end-to-end.md, dnn-architectures-hearing-aids.md, listening-effort-evaluation.md, user-controlled-on-demand-ai-hearing-aids.md]
tags: [compression, wdrc, salience, vocal-affect, hearing-aid-action-policy, perception-action-gap]
---

# Salience-Aware Gain

A class of hearing-aid compression/gain rules that **conditions the action policy on the perceived salience** of the incoming sound source — not just its spectral content. Today's HAs apply the same gain table to a frightened spousal question and a passing stranger's polite question. Salience-aware gain breaks that equivalence.

## Definition

A salience-aware gain stage is the composition of:

1. **Source attribution** — who or what is speaking (the wearer's spouse / known contact / stranger / non-human).
2. **Affect inference** — the speaker's emotional state on dimensions like fear, distress, urgency, calm.
3. **Wearer context** — what the wearer is doing (conversation, meeting, walking).
4. **A policy** — a learnable mapping from (source, affect, context, audiogram) → gain table.

Each component independently has shipping precedent (own-voice cancellation; voice-affect inference in voice assistants; activity classification in HA program switching; NAL-NL2 audiogram gain). The salience-aware gain idea is to **fuse them into a single action policy**.

## Why Now

Bartelds, Bianchi & Zou (arXiv:2606.26083, Jun 2026) showed that production voice-AI systems can *perceive* vocal affect but do not *act on it*. The hearing-aid version of the same gap is now visible at the engineering level:

- Modern HAs have DNN noise reduction, neural beamforming, and (in some products) foundation-model SE on the perception side.
- The action side — WDRC, NR depth, program switching — is still parameterised by SPL and SNR.
- Salience-aware gain is the obvious next interface between the perception and action stages.

## Engineering Sketch

A minimal shipping path:

- **Backbone:** small on-device encoder (Whisper-tiny class, or distilled audio LM).
- **Heads:** speaker identification (own / spouse-template / unknown), vocal-affect estimation (arousal/valence), conversation classification.
- **Policy:** light learned mapping to a gain offset / NR-depth offset on top of the prescribed fitting.
- **Audit interface:** wearer can override the salience-aware modifier at any time, and overrides go into a personalised continual-learning loop.

Latency budget: the perception heads need to run at conversation rate (1-2 Hz), not at the 1-5 ms audio frame rate. That keeps them compatible with current HA SoCs that have a dedicated AI accelerator (DEEPSONIC-class).

## Risks and Open Questions

- **False positives are dangerous.** A device that aggressively boosts what it (mis-)reads as a spousal distress signal can be worse than a flat gain table.
- **Discoverability and consent.** Wearers and conversational partners both need to understand what the device infers.
- **Continual personalisation.** A salience policy that does not adapt to the wearer's life is a worse product than no policy. The data-flywheel design is non-trivial.
- **Regulatory.** EU AI Act + FDA SaMD classifications likely apply once the device's action policy is conditioned on inferred emotional state.

## Related Pages
- [[vocal-affect-paralinguistics-hearing-ai]] — the perception side this concept consumes.
- [[joint-se-wdrc-end-to-end]] — same engineering pattern: collapse perception and action into a learnable joint stage.
- [[dnn-architectures-hearing-aids]] — the on-device backbones.
- [[listening-effort-evaluation]] — listener-side outcome the policy should improve.
- [[user-controlled-on-demand-ai-hearing-aids]] — the wearer-override surface.

## Sources
- [Bartelds, Bianchi & Zou, "Real-Time Voice AI Hears but Does Not Listen", arXiv:2606.26083 (Jun 2026)](../sources/arxiv-2606-26083-voice-ai-hears-not-listens-jun-2026.md) — names the perception-action gap that salience-aware gain is the engineering response to.
