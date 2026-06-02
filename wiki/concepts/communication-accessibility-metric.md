---
title: Communication Accessibility — The Missing Interactional Metric
type: concept
created: 2026-05-26
updated: 2026-06-02
sources: [wca-2026-pichora-fuller-aram-glorig-may-26-2026.md, codec-intelligibility-se-behringer-arxiv-2026.md, l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md, asr-too-good-to-be-true-arxiv-may-2026.md, brain-controlled-hearing-nature-neuroscience-may-2026.md, gijbels-ecological-validity-fauot-mar-2026.md, breaking-the-pair-speaker-switching-arxiv-june-2026.md]
related: [listening-effort-evaluation.md, subjective-objective-hearing-gap.md, multimodal-hearing-assessment.md, auditory-attention-decoding.md, linguistic-hallucination-speech-enhancement.md, closed-loop-data-flywheel.md, longitudinal-hearing-phenotyping.md, ../entities/kathy-pichora-fuller.md, ../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md, dyadic-interaction-preservation.md]
tags: [communication-accessibility, fuel-framework, evaluation-metrics, outcome-measurement, interactional, conversation, audiology-metrics, telemetry, regulatory, dyadic-interaction]
---

# Communication Accessibility — The Missing Interactional Metric

The fifth axis of hearing-aid evaluation, named at the field's flagship congress in May 2026 by Kathy Pichora-Fuller's Aram Glorig Award lecture "Hearing and Healthy Aging: The Imperative for Communication Accessibility." Captures whether a wearer can participate in real conversations across speakers, turns, and environments — not whether a signal was clean, a word was recognized, or a brain was locked on a stream. **No standardized metric exists today.** See [[../entities/kathy-pichora-fuller]].

## Where It Sits in the Stack

| Layer | Metric | What it captures | Status |
|---|---|---|---|
| Signal | PESQ / STOI / HASPI / HASQI / DNS-MOS | Acoustic fidelity / intelligibility proxy | Mature; cracks identified May 2026 — see [[../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026]] |
| Lexical | WER (often via modern ASR) | Words correctly recognized | Mature; structurally too forgiving when modern noise-robust ASR is the evaluator — see [[../sources/asr-too-good-to-be-true-arxiv-may-2026]] |
| Neural attention | AAD | The voice the brain is locked onto | Reached first closed-loop human demo May 2026 (Mesgarani, Columbia) — see [[auditory-attention-decoding]] |
| Effort | Pupillometry / NASA-TLX / SSQ-effort / ASR-derived effort proxies | Cognitive cost paid to extract meaning | Live research front; no HASPI-equivalent yet — see [[listening-effort-evaluation]] |
| **Communication accessibility** | **None standardized** | **Whether the wearer can participate in the conversation** | **Named in 2026; not built** |

The Pichora-Fuller argument is that the field has been optimizing four layers below the construct that actually drives real-world adoption, abandonment, healthspan outcomes, and policy reimbursement decisions.

## The FUEL Operationalization

Pichora-Fuller et al. (2016, *Ear and Hearing*, Eriksholm Workshop) operationalized the listening experience as the interaction of:

- **Demand** — acoustic + linguistic + cognitive task load
- **Resources** — sensory + cognitive + executive capacity
- **Motivation** — effort the listener is willing to expend

Communication accessibility is what FUEL produces when integrated over a real day of real interactions. The framework already exists. The **telemetry stack that estimates motivation × demand × resources continuously on a real wearer** does not.

## Why It Cannot Be Reduced to Existing Metrics

### Why not intelligibility?
Two systems that score identically on STOI / HASPI can produce wildly different conversational success — one keeps the wearer engaged through a 90-minute dinner, the other drives them home in 20 minutes. The signal metric is silent on the question that matters.

### Why not WER?
WER is single-talker, single-turn, single-environment. Real conversations are multi-talker, multi-turn, code-switched, interrupted, repaired, multimodal. WER also flatters generative SE that hallucinates plausible-but-wrong words — see [[linguistic-hallucination-speech-enhancement]].

### Why not AAD?
AAD measures which stream the wearer's attention is locked on. It does not measure whether they are getting enough out of that stream to participate, whether they are still motivated to allocate attention an hour from now, or whether they can switch streams when the conversation pivots.

### Why not listening effort?
Effort is the closest existing primitive — and is the input that goes into the motivation × demand × resources calculus. But effort is a moment-level cognitive cost; communication accessibility is the longitudinal aggregate that determines whether the wearer keeps showing up for the conversation tomorrow.

## What "Built" Would Look Like

1. **A standardized scoring framework** — comparable across studies, OEMs, regulatory submissions. Multi-axis: turn-taking success, repair frequency, conversation duration, voluntary disengagement, partner-side perceived effort.
2. **Wearable telemetry primitives** estimating FUEL components continuously:
   - Demand: SNR, talker count, reverberation, switching rate, semantic complexity
   - Resources: pupillometry surrogates, end-of-day fatigue, cognitive screen scores
   - Motivation: dwell time in noisy environments, voluntary social exposure, adherence
3. **Conversation as the unit of evaluation**, not the utterance. Datasets need turns, partners, environments, and outcomes — not isolated clean-vs-noisy clips.
4. **An objective HASPI-equivalent for communication accessibility** — a model-side predictor validated against ecological diary data, runnable on a dev workstation.
5. **Regulatory acceptance** — FDA / EU MDR pathways for hearing devices that include communication-accessibility outcomes alongside intelligibility.

## Why This Is a Data-Science Problem, Not Just an Audiology Problem

Three of the five required pieces are squarely in the AI/ML wheelhouse:

- **Continuous telemetry inference** from on-device sensors and paired-phone audio — large sensor models territory, see [[../concepts/large-sensor-models]] (companion-tier substrate; HA SoC alone is too power-budgeted).
- **Multi-speaker conversation parsing** at scale — modern diarization (cross-lifespan, USC, May 2026), turn detection, repair detection — the same models being built for meeting transcription, repurposed.
- **Longitudinal outcome modeling** — survival analysis on conversation engagement, propensity modeling of adherence — the same toolkit deployed in [[hearing-care-funnel-attribution]] applied at the post-fit layer.

The fitting and validation pieces stay with audiologists; the measurement substrate is an ML build.

## Competitive Implication

The May 2026 alignment is structural:

- **Mesgarani / Columbia (11 May)** — neural attention reached closed-loop demonstration
- **Behringer (5 May)** — listening effort reveals what intelligibility hides at the codec layer
- **Wang et al. L3-SE (9 May)** — word-level faithfulness named as a failure mode no current metric catches
- **de Oliveira / Peer / Gerkmann (12 May)** — ASR as evaluator broken from the opposite direction
- **Gijbels (March 2026, resurfaced May)** — multimodal assessment recovers normal-audiogram cases
- **Pichora-Fuller (26 May)** — interactional layer named at WCA 2026

Together these point at a **five-axis evaluation reframe**: signal × lexical × neural × effort × **interactional**. The OEM (or platform) that ships the missing fifth axis first will own the next decade's outcome conversation — including the reimbursement codes that follow.

## Open Questions

- Is communication accessibility a single composite score or an irreducible multi-axis vector? Audiology will resist any single score; ML pipelines require one for training loss.
- How much of FUEL's "motivation" axis can be inferred from device telemetry alone vs. requiring patient-reported in-app prompts?
- Does the metric need partner-side instrumentation (the other speaker's audio, their reactions) or can it be wearer-side only?
- Where does this sit in the regulatory taxonomy — is "communication accessibility" a Patient-Reported Outcome (PRO), a Real-World Evidence (RWE) measure, or a new category?
- For LMIC populations where audiologist-supervised verification is unavailable (see Apple India launch, May 2026), is communication accessibility a *better* candidate primary outcome than the audiogram because it can be measured on the device itself?

## Related Pages
- [[../entities/kathy-pichora-fuller]] — Architect of the FUEL framework that operationalizes the metric layer
- [[listening-effort-evaluation]] — Adjacent measurement primitive; the cognitive-cost input to motivation × demand × resources
- [[subjective-objective-hearing-gap]] — Companion gap on the perception/threshold side
- [[multimodal-hearing-assessment]] — Companion recovery pathway — audiovisual + comprehension + dyadic measurement
- [[auditory-attention-decoding]] — The neural-attention layer in the five-axis stack
- [[linguistic-hallucination-speech-enhancement]] — The lexical-faithfulness failure mode the metric must catch
- [[closed-loop-data-flywheel]] — Substrate for collecting the longitudinal data the metric requires
- [[longitudinal-hearing-phenotyping]] — Measurement framework that absorbs interactional signal
- [[../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026]] — Co-located argument that the current stack systematically flatters models the wearer will struggle with

## Sources
- [WCA 2026 Seoul — Pichora-Fuller Aram Glorig Award Lecture (26 May 2026)](../../sources/wca-2026-pichora-fuller-aram-glorig-may-26-2026.md) — Naming of the interactional metric layer at the field's flagship congress
- [Behringer et al. — Speech Codec Intelligibility & Effort (May 2026)](../../sources/codec-intelligibility-se-behringer-arxiv-2026.md) — Effort reveals what intelligibility hides; codec-level precedent
- [Wang et al. — L3-SE Linguistic Hallucination (May 2026)](../../sources/l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md) — Word-level faithfulness gap
- [de Oliveira, Peer & Gerkmann — ASR Too Good to Be True (May 2026)](../../sources/asr-too-good-to-be-true-arxiv-may-2026.md) — Why the standard fallback evaluator is structurally broken
- [Choudhari, Mesgarani et al. — Brain-Controlled Hearing (Nature Neuroscience, May 2026)](../../sources/brain-controlled-hearing-nature-neuroscience-may-2026.md) — Neural-attention layer reached closed-loop demonstration
- [Gijbels et al. — Ecological Validity in Hearing Science (March 2026)](../../sources/gijbels-ecological-validity-fauot-mar-2026.md) — Audiovisual + comprehension measurements recover what audio-only misses
- Pichora-Fuller et al. (2016) "Hearing impairment and cognitive energy: The Framework for Understanding Effortful Listening (FUEL)." *Ear and Hearing* 37 Suppl 1: 5S-27S.
