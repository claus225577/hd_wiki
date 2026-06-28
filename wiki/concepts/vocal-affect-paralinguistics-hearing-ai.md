---
title: Vocal Affect and Paralinguistics in Hearing AI
type: concept
created: 2026-06-28
updated: 2026-06-28
sources: [arxiv-2606-26083-voice-ai-hears-not-listens-jun-2026.md]
related: [salience-aware-gain.md, turn-taking-prediction-hearing-ai.md, listening-effort-evaluation.md, large-sensor-models.md, ai-understanding-gap-hearing-industry.md]
tags: [paralinguistics, vocal-affect, emotion, perception-action-gap, voice-ai, hearing-aid-policy]
---

# Vocal Affect and Paralinguistics in Hearing AI

The channel of vocal communication that lives **above** the words — pitch, breathiness, prosody, vocal effort, breath rate — and conveys emotional state, urgency, sincerity, and intent. Vocal-affect processing is the dimension hearing aids have studiously ignored while the rest of the audio AI field moved into it.

## The Bartelds Result (Jun 2026)

Bartelds, Bianchi & Zou (arXiv:2606.26083) tested four production voice-AI systems on tasks where vocal delivery should change the action. The finding:

- The systems privilege lexical content over paralinguistic delivery.
- They approve wire transfers from frightened callers and end calls with distressed users.
- **3 of 4 systems**, when asked, *correctly name* the emotional state they had just ignored.
- The gap is between **perception and action**, not between perception and ignorance.

## Mapping the Gap to Hearing Aids

Hearing aids today amplify, compress, transmit. The action policy of an HA — *what it does with what it hears* — has barely moved in a decade, even as perception has accelerated.

The same perception-action gap shows up in:

- A spousal frightened question and a polite stranger's question receive identical gain.
- A distressed customer-service call and a calm one receive identical compression.
- An angry argument and a heated debate receive identical noise reduction.

In every case, the device's perception layer can almost certainly extract the affect signal (Whisper-style encoders capture it; smaller in-the-loop models can too). The device's action policy throws it away.

## Three Concrete HA Implications

1. **Salience-aware gain** as a next compression rule. See [[salience-aware-gain]].
2. **Vocal-affect wellness monitoring.** Cortisol-correlated vocal features are already extractable from the standard HA microphone signal. The wellness story for HAs has been step-count, heart-rate, fall-detection; affect is a larger signal sitting unused.
3. **Regulatory categorisation.** "Heard but did not act" is the kind of failure mode that becomes a regulatory category once a voice-AI agent gets sued for it in fintech. HAs that route, amplify, or summarise calls inherit the same standard.

## Why This Has Been Hard for Hearing Aids

- **On-device compute.** Paralinguistic feature extraction has been heavier than the spectral-shaping HAs traditionally do.
- **Privacy.** Affect inference at the device level is regulatorily sensitive.
- **Wearer-control surface.** A "salience-aware" device demands an interface for the wearer to say *what counts as salient* — an HCI problem the field has not seriously confronted.
- **Clinical validation.** No accepted outcome instrument yet measures "the device responded appropriately to the speaker's emotional state."

The Bartelds paper makes the first two harder to use as excuses. Voice-AI systems are deploying paralinguistic perception today; the latency advantages are not what they used to be.

## Open Research Questions

- What is the minimal set of paralinguistic features that meaningfully changes an HA action policy?
- How should an HA degrade gracefully when the wearer disagrees with the device's affect inference?
- How does hearing impairment couple back to the wearer's own vocal-affect production (own-voice monitoring loss)?
- What is the right unit of evaluation — per-utterance, per-conversation, per-day?

## Related Pages
- [[salience-aware-gain]] — the downstream policy that operationalises vocal-affect.
- [[turn-taking-prediction-hearing-ai]] — affect is the dimension turn-taking models miss.
- [[listening-effort-evaluation]] — speaker affect and listener effort are coupled.
- [[large-sensor-models]] — voice-AI agents are the upstream technology that will enter ear-worn form factors.
- [[ai-understanding-gap-hearing-industry]] — synthesis page where this concept extends the argument.

## Sources
- [Bartelds, Bianchi & Zou, "Real-Time Voice AI Hears but Does Not Listen", arXiv:2606.26083 (Jun 2026)](../sources/arxiv-2606-26083-voice-ai-hears-not-listens-jun-2026.md) — the cleanest published statement of the perception-action gap.
