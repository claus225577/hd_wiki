---
title: Care Partners and Dyad-Level Models for Hearing AI
type: concept
created: 2026-05-10
updated: 2026-05-10
sources: [asha-nslhm-2026-care-partners.md]
related: [closed-loop-data-flywheel.md, hearing-loss-dementia-link.md, digital-phenotyping-cognitive-decline.md, longitudinal-hearing-phenotyping.md, on-device-ml-hearing-aids.md, ../syntheses/ai-understanding-gap-hearing-industry.md]
tags: [care-partners, dyad, multi-user-modeling, adherence, patient-centered-care, telemetry, family, asha]
---

# Care Partners and Dyad-Level Models for Hearing AI

A design and data gap. Hearing-aid AI architecture is overwhelmingly **n=1** (the wearer), while a decade of adherence and outcome research says the **dyad** — wearer plus primary care partner — is the unit of adoption.

## The Gap

### Single-User Architecture (Today)
- Own-voice detectors trained against one speaker.
- Personalization optimizes one wearer's preferences.
- Telemetry attributes events to one device-user.
- Speech enhancement targets the wearer's intelligibility.
- Fitting workflow has one slider for one ear pair.
- Outcome metrics measure the wearer's word recognition (HINT, AzBio, COSI as wearer-self-report).

### Dyad-Level Architecture (Implied by Evidence)
- Conversation partners as a first-class entity in the device's world model.
- Telemetry of repair requests, repetitions, and breakdowns — events visible to the microphone array but currently aggregated only as wearer signals.
- Fitting feedback collected from both members of the dyad, not only the wearer.
- Outcome metrics that include the care partner's listening effort and satisfaction (e.g., Significant Other Scale of Hearing Disability variants, third-party COSI).

## Why It Matters

ASHA's National Speech-Language-Hearing Month 2026 resource set leans heavily into care-partner content (see [[../../sources/asha-nslhm-2026-care-partners]]) — articles for spouses of adults with hearing loss, adult children of parents with dementia, families navigating swallowing/communication disorders. ASHA is acknowledging at the public-awareness level what adherence research has shown for years:

- **Wear time** correlates with care-partner involvement.
- **Continuation of use** correlates with social/family context.
- **Conversational success** is a property of the dyad, not of one ear.
- The **third-party disability** literature (Hickson, Scarinci, Worrall) has documented care-partner burden as a measurable outcome since the 2000s.

Yet none of these signals are first-class in hearing-aid telemetry, fitting tools, or AI personalization.

## What the Hardware Already Sees

Modern hearing aids capture, today, in the wearer's ear:
- The acoustic environment (scene classification, SNR estimation).
- The wearer's own voice (own-voice detection).
- Conversational structure (turn-taking, voice activity, pauses).
- Repetitions — when the wearer's interlocutor speaks again at higher level after a previous utterance, the microphone array sees a repair signature.
- Listening effort proxies (head motion patterns from IMU, time-in-noise).

The dyad signal is **already in the data stream**. It's collected, then thrown away, because the data model assumes one user.

## Concrete Multi-User Schema Pieces

1. **Conversation partner enrollment** — an opt-in process to identify recurring interlocutors via short voice samples, with cryptographic consent management.
2. **Dyad-level telemetry** — repetition events, repair signatures, conversation breakdown frequency aggregated against (wearer, partner) pairs.
3. **Bilateral fitting feedback** — partner-side rating apps that capture comfort, intelligibility, and listening effort *as experienced by the partner*.
4. **Joint outcome metrics** — composite scores including third-party listening effort, partner-reported wearer engagement, partner-reported repair burden.
5. **AI personalization on dyad signals** — speech enhancement targets that include the wearer's *partner's* speech as a high-priority enhancement target, not only the foreground talker by SNR.

## Adjacent Frameworks

- [[closed-loop-data-flywheel]] — extending the flywheel to two-person feedback rather than one.
- [[hearing-loss-dementia-link]] — care-partner role is most acute in cognitive-decline contexts; AAA's MCI screening from HA telemetry is relevant.
- [[digital-phenotyping-cognitive-decline]] — passive continuous signals from hearing aids could become preclinical biomarkers; the dyad is the natural experimental unit.
- [[longitudinal-hearing-phenotyping]] — outcome measurement on a dyad timeline rather than individual.

## Open Questions

- **Consent and privacy.** Multi-user schemas raise immediate consent issues — does the conversation partner consent to having their voice fingerprint enrolled? How does GDPR / HIPAA / state-law biometric consent apply?
- **Telemetry granularity vs privacy.** Repair-event telemetry is relatively benign in aggregate; per-conversation logs are highly sensitive.
- **Workflow integration.** Audiology fitting visits are typically wearer-only. Dyad-aware fitting would require a second person in the appointment or a remote partner-side interface.
- **Reimbursement.** Outcome metrics that include partner burden are not currently reimbursable endpoints. Until they are, manufacturers have weak incentives to instrument them.
- **Regulatory.** A device that "models" a care partner crosses into multi-subject SaMD territory with implications under FDA AI/ML lifecycle guidance and EU MDR.

## Related Pages
- [[closed-loop-data-flywheel]] — Multi-user extension of feedback architecture
- [[hearing-loss-dementia-link]] — Care-partner role most acute in dementia
- [[digital-phenotyping-cognitive-decline]] — Adjacent measurement frontier
- [[longitudinal-hearing-phenotyping]] — Outcome-measurement layer
- [[../syntheses/ai-understanding-gap-hearing-industry]] — Industry's n=1 default is itself an "AI understanding gap"

## Sources
- [ASHA NSLHM 2026 — Care-Partner Resource Push](../sources/asha-nslhm-2026-care-partners.md) — May 2026
