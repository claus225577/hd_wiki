---
title: Dyadic Interaction Preservation — Speaker-Switch Diagnostics for Conversation-Level Evaluation
type: concept
created: 2026-06-02
updated: 2026-06-14
sources:
  - breaking-the-pair-speaker-switching-arxiv-june-2026.md
  - wca-2026-pichora-fuller-aram-glorig-may-26-2026.md
related:
  - turn-taking-prediction-hearing-ai.md
  - communication-accessibility-metric.md
  - listening-effort-evaluation.md
  - non-intrusive-intelligibility-prediction.md
  - linguistic-hallucination-speech-enhancement.md
  - speech-enhancement-neural-networks.md
  - cross-lifespan-speech-models.md
  - ../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md
tags: [evaluation-metrics, dyadic-interaction, conversational-entrainment, speaker-switch-test, dyadic-distance-matrix, hearing-aid-evaluation, conversation, dialogue-modelling, interaction-preservation]
---

# Dyadic Interaction Preservation — Speaker-Switch Diagnostics for Conversation-Level Evaluation

A class of evaluation methods that ask whether a speech/dialogue representation captures **genuine dyadic coadaptation** between two speakers — the entrainment that happens when two real people actually talk to each other — rather than just individual-speaker traits or per-turn statistics.

Introduced as a method family by Nilabh & Sharma (arXiv:2606.02185, 1 June 2026) under the umbrella of the **Dyadic Distance Matrix (DDM)** + **speaker-switch test**. The first methodologically clean diagnostic of interaction structure as a separable evaluation axis.

## Why This Matters for Hearing Aids

The dominant hearing-aid evaluation stack measures:

| Layer | Metric | What it captures |
|---|---|---|
| Signal | PESQ / STOI / HASPI / HASQI / DNS-MOS | Acoustic fidelity |
| Lexical | WER / CPC3-style intelligibility | Words recognized |
| Neural attention | AAD | Which voice the brain is locked onto |
| Effort | Pupillometry, ASR-derived proxies | Cognitive cost |
| **Interaction preservation** | **Speaker-switch / DDM (new, June 2026)** | **Whether the conversation as a two-person system is preserved** |

The wearer's lived complaint is not "I cannot follow read speech" — it is **"I cannot follow the conversation."** No metric above the new "interaction preservation" row directly tests for the interactional substrate of that complaint. See [[communication-accessibility-metric]] for the related construct.

## The Speaker-Switch Test

### Procedure
1. Take a two-speaker dialogue with speakers A and B.
2. Construct a swapped variant: replace B's turns with turns from an unrelated speaker B', drawn from a different conversation.
3. Preserve turn-level statistics (turn lengths, distributional features per speaker remain similar).
4. Train a classifier to discriminate real (A, B) dyads from switched (A, B') dyads, using the system's representations as input.

### What Is Preserved vs Destroyed
| Property | Real dyad | Switched dyad |
|---|---|---|
| Per-speaker statistics | ✓ | ≈ ✓ (B' chosen from similar pool) |
| Turn-length distribution | ✓ | ≈ ✓ |
| Lexical alignment | ✓ | ✗ |
| Prosodic entrainment | ✓ | ✗ |
| Turn-timing coadaptation | ✓ | ✗ |
| Topical coherence | ✓ | ✗ |

The discriminability gap is exactly the signal that the system has internalized **interaction structure**, not just speaker traits.

## The Dyadic Distance Matrix (DDM)

A representation of a two-speaker conversation that captures inter-speaker distance patterns over time, designed to make dyadic structure first-class:
- Off-diagonal structure encodes how the two speakers' representations co-evolve.
- The DDM is the substrate on which the speaker-switch classifier is trained.

## The Most Important Number in the Paper

Across four embedding types on **CANDOR** (naturalistic conversation) and **LibriSpeech** (read speech), real-vs-switched DDMs are discriminable — but discriminability is **higher on read speech than on naturalistic conversation**.

Read in context: current representations, including foundation-model speech embeddings, are *less* sensitive to genuine conversational entrainment than to spurious read-speech regularities. The metric reveals an inversion: today's models capture the wrong thing better than the right thing.

For hearing-aid evaluation that is exactly the wrong direction — wearers care about naturalistic dialogue, not read speech.

## Practical Application to Hearing-Aid SE Pipelines

The actionable use:

1. Take a benchmark of dyadic conversations recorded in realistic noise.
2. Compute DDM and speaker-switch discriminability **before** SE processing.
3. Compute DDM and speaker-switch discriminability **after** SE processing.
4. If the swap-discriminability signal collapses post-SE, the SE pipeline is destroying interactional structure even if it improves PESQ / STOI / WER.

This is functionally an interaction-preservation regression test. A new axis in CI for hearing-aid SE.

## Open Research Questions

- Does pre/post-SE swap-discriminability correlate with subjective conversation-following ratings in HI listeners?
- Can DDM features be computed online, on-device or on the companion phone, as a personalization signal?
- Behavior on 3+ speaker conversations — the regime where HA wearers struggle most — is untested.
- Does the diagnostic transfer to dyads where one speaker is hearing-impaired and using a hearing aid (asymmetric entrainment)?

## Related Pages
- [[turn-taking-prediction-hearing-ai]] — generative counterpart at the same interactional layer; ModeratorLM (arXiv:2606.13544, June 2026) operationalizes role-conditioned turn-taking prediction, where dyadic-interaction-preservation operationalizes the diagnostic.
- [[communication-accessibility-metric]] — the construct named at WCA 2026 Seoul by Pichora-Fuller; speaker-switch is one operationalization candidate.
- [[non-intrusive-intelligibility-prediction]] — what the field has been building at the lexical layer; this is the analog at the interactional layer.
- [[listening-effort-evaluation]] — adjacent but distinct; effort is about cost paid, interaction preservation is about whether the conversation as a system survives processing.
- [[linguistic-hallucination-speech-enhancement]] — both flag failure modes invisible to standard metrics.
- [[cross-lifespan-speech-models]] — dyadic structure is precisely what cross-lifespan and child-directed models need to preserve.
- [[../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026]] — the umbrella synthesis the speaker-switch diagnostic plugs into as a fifth axis.

## Sources
- [Nilabh & Sharma, "Breaking the Pair: Evaluating Dyadic Interaction via Speaker Switching," arXiv:2606.02185 (1 June 2026)](../../sources/breaking-the-pair-speaker-switching-arxiv-june-2026.md) — primary source for the method, DDM definition, speaker-switch test, and the read-vs-naturalistic discriminability finding.
- [Pichora-Fuller WCA 2026 Aram Glorig Award lecture (May 26 2026)](../../sources/wca-2026-pichora-fuller-aram-glorig-may-26-2026.md) — the construct (communication accessibility) that this method offers a first quantitative diagnostic for.
