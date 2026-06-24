---
title: Anu Sharma
type: entity
created: 2026-06-24
updated: 2026-06-24
sources: [vcca-2026-main-programme-june-2026.md, vcca2026-conference.md]
related: [../concepts/cortical-reorganization-hearing-aids.md, ../concepts/hearing-loss-dementia-link.md, ../concepts/cochlear-implant-ai.md, ../concepts/hidden-hearing-loss.md, vcca-computational-audiology.md]
tags: [person, researcher, audiologist, university-of-colorado-boulder, cross-modal-neuroplasticity, cortical-reorganization, age-related-hearing-loss, p1-cortical-response, vcca-2026-invited]
---

# Anu Sharma

Professor at the **University of Colorado Boulder**, Department of Speech, Language and Hearing Sciences. Senior researcher on **cross-modal neuroplasticity** — the changes in cortical organisation that follow sensory deprivation, especially the recruitment of auditory cortex by visual and somatosensory input in untreated hearing loss.

## 2026 Recognition

**VCCA 2026 Day 2 Invited Speaker (Jun 26, 2026):** *"The Changing Brain: Cross-Modal Neuroplasticity in Hearing loss."*

## Structural Contributions to the Field

### 1. Cross-modal cortical reorganisation as a measurable consequence of untreated hearing loss

Sharma's lab has been the most consistent voice for the claim that untreated hearing loss does not leave the brain unchanged — that auditory cortex undergoes cross-modal reorganisation (recruitment by visual / somatosensory input) on the order of months to years, and that this reorganisation is at least partially reversible with appropriate auditory intervention (hearing aids, cochlear implants).

The framework provides a neural-substrate explanation for several outcomes other lines of work have measured behaviourally:
- Better outcomes for early-implanted pediatric CI recipients (less cross-modal reorganisation to reverse).
- Cognitive-load / dementia-link findings (cross-modal reorganisation is one neural pathway by which untreated hearing loss may accelerate cognitive decline).
- The slow improvement of speech-in-noise scores in adult hearing-aid wearers over months (cortical reorganisation back toward acoustic-dominant processing).

### 2. The P1 cortical auditory evoked response as a clinical biomarker

Sharma's lab pioneered the use of the **P1 cortical auditory evoked response** (CAEP) as a biomarker for cortical maturation and reorganisation in deaf children fitted with cochlear implants. P1 latency is one of the few clinically tractable measures of how well the auditory cortex has adapted to the implanted input — and is one of the early-warning signals for suboptimal CI outcomes.

### 3. Adult age-related hearing loss as a brain-plasticity problem

Extension of the cross-modal-reorganisation framework to adult-onset hearing loss. Sharma's argument: the same plasticity that helps deaf children adapt to a CI works *against* untreated adults, where auditory cortex starts losing acoustic specialisation if not stimulated. The framing is a neural-side argument for treating mild-to-moderate hearing loss earlier rather than waiting until it is severe — an argument that aligns with the hearing-loss → dementia evidence chain ([[../concepts/hearing-loss-dementia-link]]).

## Why This Matters for Hearing AI / Data Science

### Neural reorganisation is a slow-feedback loop the ML side has not yet modeled

Most hearing-AI personalisation operates on acoustic / behavioural timescales (seconds to days). Sharma's framework introduces a months-to-years feedback loop: the cortex changes in response to whether and how the listener is hearing. A truly long-horizon personalisation model would need to account for cortical reorganisation as a state variable. None of the currently shipping personalisation engines does this.

### The dementia-link mechanism candidate

Cross-modal reorganisation is one of the leading candidate mechanisms by which untreated hearing loss may causally accelerate cognitive decline (the others being listening-effort allocation, social-engagement-decline, and direct neurodegenerative co-pathology). Sharma's work provides the most neurally specific version of the mechanism. See [[../concepts/hearing-loss-dementia-link]] and [[../concepts/cortical-reorganization-hearing-aids]].

### Pediatric CI outcomes pipeline

Sharma's P1-CAEP biomarker is one of the few clinically validated objective measures of how well a pediatric CI is "fitting" the cortex over time. As CI-side ML (Nucleus Nexa, AI-based programming) moves toward more frequent and more automated remapping, P1-CAEP becomes a candidate objective fitness function — a neural-side outcome the ML pipeline could optimise against.

### Adjacency to the Hidden HL programme

Sharma's neuroplasticity framework is *not* synaptopathy / hidden HL per se, but it provides the brain-side answer to the same question: "what does untreated hearing loss do that the audiogram doesn't capture?" Where Kujawa and Dillon argue for peripheral mechanisms, Sharma argues for cortical mechanisms — and the two are likely complementary rather than competing.

## Related Pages

- [[../concepts/cortical-reorganization-hearing-aids]] — The phenomenon Sharma's lab pioneered the clinical measurement of.
- [[../concepts/hearing-loss-dementia-link]] — Cross-modal reorganisation as a candidate mechanism in the dementia link.
- [[../concepts/cochlear-implant-ai]] — P1-CAEP as a candidate objective fitness function for CI fitting.
- [[../concepts/hidden-hearing-loss]] — The cortical-side counterpart to the peripheral HHL mechanisms.
- [[vcca-computational-audiology]] — VCCA 2026 invited speaker context.

## Sources

- [VCCA 2026 Main Programme](../../sources/vcca-2026-main-programme-june-2026.md) — Day 2 invited talk.
- [VCCA 2026 Conference Overview](../../sources/vcca2026-conference.md) — Programme structure.
