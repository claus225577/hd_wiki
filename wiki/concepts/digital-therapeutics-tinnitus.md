---
title: Digital Therapeutics for Tinnitus
type: concept
created: 2026-05-11
updated: 2026-06-07
sources: [silentcloud-tinnitus-rwd-frontiers-may-2026.md, sonova-silentcloud-acquisition-2026.md, qvac-medpsy-edge-medical-llm-may-2026.md, musicians-tinnitus-meta-analysis-2026.md, tinnitus-app-rct-jama-wasano-may-2026.md, cilcare-cil001-massgeneral-tinnitus-may-2026.md]
related: [care-partner-dyad-models.md, hearing-loss-dementia-link.md, ../entities/sonova-ag.md, longitudinal-hearing-phenotyping.md, medical-domain-edge-llms.md]
tags: [tinnitus, digital-therapeutics, dtx, icbt, cbt, adherence, silentcloud, sonova, real-world-data, thi, digital-health, rct]
---

# Digital Therapeutics for Tinnitus

Software-as-medical-device (SaMD) interventions delivering structured therapy — most commonly internet-based cognitive behavioural therapy (iCBT) and sound therapy — for chronic tinnitus distress. Distinct from hearing aids: the device is the app, the active ingredient is the protocol.

## Why Tinnitus Is a Natural DTx Indication

- **High prevalence:** 10–15% of adults experience some chronic tinnitus
- **Occupational cohorts dwarf the general-population rate.** A 2026 meta-analysis (67 studies, 28,000+ musicians, 21 countries; *Otolaryngology – Head and Neck Surgery*) found **42.6% of musicians** experience tinnitus (vs 13.2% controls), 25.7% hearing loss, 37.3% hyperacusis. **Genre-neutral** — no significant classical-vs-rock/pop difference; instrument, ensemble seating, room acoustics, and protection-adherence matter more than genre. Quantifies and citably sources the musician-tier addressable market for tinnitus DTx + custom IEM-tier hearing protection. See [[../sources/musicians-tinnitus-meta-analysis-2026]].
- **No reliable pharmacotherapy:** evidence-based interventions are predominantly behavioural (CBT)
- **Audiologist scarcity:** see [[audiologist-workforce-shortage]] — most chronic tinnitus patients never see a specialist
- **Under-served by hardware:** hearing aids treat associated hearing loss but not tinnitus distress itself; a software lane fills the gap

## Regulatory Status (2026)

- **CE mark** under EU MDR for several products
- **FDA 510(k) clearance** required for US distribution as SaMD
- SilentCloud holds both — making it one of the first dual-cleared digital tinnitus therapeutics

## The Wasano RCT — Controlled Efficacy Signal (May 2026)

A second pillar of 2026 evidence: **Wasano et al., JAMA Otolaryngology–Head & Neck Surgery (May 2026)** — a **double-blind, sham-controlled RCT** of a prototype CBT + educational-counseling app in 60 patients with chronic tinnitus (Tokai University, Japan). See [[../sources/tinnitus-app-rct-jama-wasano-may-2026]].

- **Between-group THI improvement: −20.4 points at week 16, −18.3 at week 24** (effect persisted 8 weeks after therapeutic functions were disabled)
- No serious adverse events
- Effect size ~3× the canonical 7-point THI MCID

**Why this matters separately from the SilentCloud RWD:** Wasano supplies *controlled efficacy* (does the protocol work?); SilentCloud supplies *real-world effectiveness + adherence* (does it reach people?). They are complementary evidence layers — efficacy under control, attrition at scale — and adherence is the bridge between them. Reimbursement decisions in 2026–27 will require both.

## The SilentCloud Real-World Evidence Result (May 2026)

Sonova R&D published the first peer-reviewed real-world outcomes paper for SilentCloud in *Frontiers in Audiology and Otology* (Schmitt & Stropahl, May 7, 2026).

### Efficacy signal (in completers)
- **Mean THI reduction:** −14.7 points (p < 0.001)
- **Cohen's d:** ~0.69 (medium-to-large)
- **Clinically meaningful improvement (≥7 pts):** 63.5% of completers
- Effect size is consistent with the broader iCBT-for-tinnitus literature

### The adherence problem (the more important number)
- **17,271 registered users** across five European countries
- **63 iCBT completers**
- **Completion rate: ~0.4%**

This is **the central data-science problem** in the field. Efficacy among completers is established; the open question is how to keep more people engaged long enough for the protocol to work.

## Why Adherence Is the ML Problem

Once efficacy is shown for those who complete, marginal investment in iCBT content improvement is low-leverage. High-leverage research questions:

- **Dropout-time survival modelling** — when do users disengage, and which features predict it?
- **Sequence-aware nudges** — which message at which moment recovers engagement?
- **Content-ordering personalization** — sound therapy first vs psycho-education first vs counselling first, conditioned on user phenotype
- **Symptom-day–contingent triggers** — using ESM-style ratings as engagement signals
- **Dyadic onboarding** — see [[care-partner-dyad-models]]; the spouse / care partner is rarely modelled but reliably predicts adherence in chronic-condition self-management
- **Predictive triage** — identifying at registration which users are unlikely to complete, and routing them to lower-intensity entry points

## Reference Architecture (Open)

A digital therapeutic for tinnitus that takes the adherence problem seriously would need:

1. **Engagement telemetry** — per-screen dwell time, session abandonment points, return latency
2. **Outcome instrumentation** — short-form ESM symptom ratings beyond the THI checkpoint
3. **Multi-user data schema** — care partner enrolment as a first-class entity
4. **A/B-testable nudge inventory** — sequence-aware, not blast-cadence
5. **Survival-time models** with calibrated dropout probabilities feeding the nudge selector
6. **Hearing-aid bridge** — for users who wear hearing aids, app-side data can fuse with wear-time / acoustic-environment telemetry from the device

## Competitive Landscape

- **SilentCloud** (Sonova; CE + FDA-cleared; iCBT + sound therapy + education)
- **Tinnitracks** — music-based notched-amplification therapy (Germany)
- **Lenire** — bimodal neuromodulation (Neuromod Devices; FDA-cleared device, not pure software)
- **Audiocure** — pharmacotherapy (not DTx, included for landscape)
- **Cilcare (CIL001)** — investigational pharmacotherapy targeting cochlear synaptopathy; US trial in preparation at Mass General with Maison's group (announced May 2026; SelectUSA Summit). Disease-modifying lane, complementary to DTx adherence problem. See [[../sources/cilcare-cil001-massgeneral-tinnitus-may-2026]].
- **MindEar**, **Oto** — emerging app-based tinnitus management products

## Open Research Questions

- Does fused HA-telemetry + DTx-app telemetry produce a better adherence model than either alone?
- Can large audio language models (see [[audio-reasoning-chain-of-thought]]) classify symptom-day audio diary entries to enrich engagement features?
- Is dyadic onboarding (spouse/care-partner co-enrolled) a clinically reportable outcome moderator?
- Does precision-triage at registration (route low-completion-probability users to a lighter entry point) raise effective completion rates without sacrificing fidelity?
- **Does an on-device medical LLM in the companion app (see [[medical-domain-edge-llms]]) shift the adherence curve by removing the cloud-data trust barrier and enabling personalized, conversational protocol delivery?** QVAC MedPsy (May 2026) makes the substrate available; the open empirical question is whether iCBT delivered via on-device conversational counselling out-completes form-based delivery.

## Related Pages
- [[care-partner-dyad-models]] — Dyadic onboarding as adherence lever
- [[hearing-loss-dementia-link]] — Tinnitus and untreated hearing loss often co-occur; intervention rationale stacks
- [[longitudinal-hearing-phenotyping]] — Telemetry substrate for joint device+app outcomes
- [[../entities/sonova-ag]] — SilentCloud is now Sonova IP after the 2026 acquisition
- [[audiologist-workforce-shortage]] — DTx scales where audiology workforce can't

## Sources
- [Wasano RCT — JAMA Otolaryngology (May 2026)](../sources/tinnitus-app-rct-jama-wasano-may-2026.md) — Double-blind sham-controlled RCT, n=60; between-group THI −20.4 at week 16, durable to week 24
- [SilentCloud RWD — Frontiers (May 2026)](../sources/silentcloud-tinnitus-rwd-frontiers-may-2026.md) — First peer-reviewed RWD; THI −14.7 in completers; 17,271 → 63 funnel
- [Sonova SilentCloud Acquisition (2026)](../sources/sonova-silentcloud-acquisition-2026.md) — Strategic context: tinnitus DTx as Sonova's non-hardware lane
- [QVAC MedPsy edge medical LLM (May 2026)](../sources/qvac-medpsy-edge-medical-llm-may-2026.md) — On-device medical LLMs as a possible adherence lever for tinnitus iCBT delivery
- [Cilcare CIL001 Mass General US trial prep (May 2026)](../sources/cilcare-cil001-massgeneral-tinnitus-may-2026.md) — Pharma lane targeting cochlear synaptopathy; complementary to behavioural DTx
