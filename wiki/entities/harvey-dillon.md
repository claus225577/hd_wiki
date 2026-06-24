---
title: Harvey Dillon
type: entity
created: 2026-06-24
updated: 2026-06-24
sources: [vcca-2026-main-programme-june-2026.md, vcca2026-conference.md]
related: [../concepts/hidden-hearing-loss.md, ../concepts/subjective-objective-hearing-gap.md, ../concepts/hearing-aid-prescription-formulas.md, ../concepts/multimodal-hearing-assessment.md, vcca-computational-audiology.md, ../syntheses/hidden-hearing-loss-fullstack-june-2026.md]
tags: [person, researcher, audiologist, macquarie, nal, prescription-formula, hidden-hearing-loss, suprathreshold, vcca-2026-keynote, australia]
---

# Harvey Dillon

Professor at **Macquarie University** (Sydney), formerly long-time research director at the **National Acoustic Laboratories (NAL)** in Australia. One of the most senior figures in the field of audiology globally, with deep contributions across hearing-aid prescription, signal processing for amplification, and the diagnostic disambiguation of "listening difficulty when the audiogram is normal."

## 2026 Recognition

**VCCA 2026 Day 1 Keynote (Jun 25, 2026):** *"Separating the Causes of Listening Difficulties when Thresholds are Normal: Concepts and Data."*

The keynote is the field's current most direct framing of the hidden-hearing-loss problem from the diagnostic side: multiple distinct mechanisms (cochlear synaptopathy, EHF / suprathreshold OHC damage, central auditory processing deficits, cognitive contributors) sit underneath the single observable phenotype of "normal audiogram, impaired listener." Dillon's argument is that these mechanisms need to be disambiguated before any single intervention (drug, fitting algorithm, training protocol) can be evaluated.

Paired on the same VCCA 2026 programme with Sharon Kujawa's invited "Hidden Hearing Loss: From Animal Models to Human Translation" — the basic-science founder of synaptopathy (animal-model side) and the senior clinical-audiology disambiguator (translational side) on the same conference. See [[../concepts/hidden-hearing-loss]] and [[vcca-computational-audiology]].

## Structural Contributions to the Field

### 1. NAL prescription formulas

Dillon led the NAL research programme that produced **NAL-NL1** (1999) and **NAL-NL2** (2010) — the most widely used non-proprietary hearing-aid prescription formulas globally. The NAL formulas operationalised the loudness-equalisation / loudness-normalisation tradeoff in fitting and remain the default research-and-clinical baseline against which OEM proprietary formulas and the emerging NAL-NL3 (2026) are compared. See [[../concepts/hearing-aid-prescription-formulas]] and the GN Hearing NAL-NL3 launch context in [[gn-hearing-resound]].

### 2. *Hearing Aids* (textbook)

Dillon's textbook *Hearing Aids* (2001, 2nd ed. 2012) is the field's most-used reference text. The book frames the engineering pipeline (transducer → signal processing → fitting algorithm → wearer outcome) in a way that has informed two generations of HA researchers and clinicians.

### 3. Disambiguating "listening difficulty with normal audiogram"

Long-running line of research on the clinical phenotype of listeners who present with normal pure-tone audiograms but report substantial real-world hearing difficulty. The VCCA 2026 keynote is the most recent and most public formulation. The disambiguation question is the diagnostic-side precondition for everything downstream: if "hidden HL" is actually four distinct mechanisms, no single intervention will help all four populations.

## Why This Matters for Hearing AI / Data Science

The hearing-AI fitting and personalisation stack currently consumes a pure-tone audiogram and a small number of additional inputs as the substrate for personalisation. If Dillon's argument is right — that "normal audiogram with listening difficulty" hides 3–4 mechanistically distinct phenotypes that require distinct interventions — then:

1. The fitting target needs to expand beyond the audiogram (a point Pichora-Fuller's FUEL work approaches from the listening-effort side; see [[kathy-pichora-fuller]]).
2. ML personalisation that uses only the audiogram as input cannot, even in principle, deliver the right intervention to an HHL listener.
3. The substrate that *can* deliver disambiguation — speech-in-noise testing, EHF audiometry, listening-effort measurement, per-wearer simulated cochlear/perceptual models — is exactly the substrate the VCCA 2026 programme, the Acousia Phase 2a EHF outcome, and the Saddler / Lopez-Poveda differentiable-cochlea track are all building in parallel.

Dillon's keynote names the diagnostic problem the rest of the field is implicitly solving.

## Related Pages

- [[../concepts/hidden-hearing-loss]] — The diagnostic phenotype Dillon's keynote addresses.
- [[../concepts/subjective-objective-hearing-gap]] — Population-scale framing of the same gap.
- [[../concepts/hearing-aid-prescription-formulas]] — NAL formulas (NAL-NL1 / NAL-NL2 / NAL-NL3) lineage Dillon led at NAL.
- [[../concepts/multimodal-hearing-assessment]] — Recovery direction for the diagnostic side of HHL.
- [[vcca-computational-audiology]] — VCCA 2026 keynote context.
- [[../syntheses/hidden-hearing-loss-fullstack-june-2026]] — Where Dillon's diagnostic disambiguation sits in the full HHL stack.

## Sources

- [VCCA 2026 Main Programme](../../sources/vcca-2026-main-programme-june-2026.md) — Day 1 keynote.
- [VCCA 2026 Conference Overview](../../sources/vcca2026-conference.md) — Programme structure.
