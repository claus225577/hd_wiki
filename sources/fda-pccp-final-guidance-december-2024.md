---
title: "FDA Final Guidance — Predetermined Change Control Plans for AI-Enabled Device Software Functions (December 2024)"
source_type: regulatory-guidance
date: 2024-12-04
url: https://www.fda.gov/regulatory-information/search-fda-guidance-documents/predetermined-change-control-plans-artificial-intelligence-enabled-device-software-functions
publisher: U.S. Food and Drug Administration (FDA), Center for Devices and Radiological Health (CDRH)
tags: [fda, regulation, pccp, ai-ml, samd, ai-dsf, tplc, change-control, hearing-aids, cochlear-implants]
---

# FDA Final Guidance — Predetermined Change Control Plans for AI-Enabled Devices

## Key Facts
- **Publisher:** FDA / CDRH
- **Type:** Final Guidance (replaces / formalises the April 2019 discussion paper and the January 2021 AI/ML SaMD Action Plan, draft guidance April 2023)
- **Issued:** December 2024
- **Scope:** AI-enabled device software functions (AI-DSF) — both software-as-medical-device (SaMD) and software in a device (SiMD), including implanted hardware running AI/ML
- **Counts to date:** 1,350+ AI-enabled medical devices authorised by FDA as of Q1 2026 — roughly double the 2022 count

## What a PCCP Is
A **Predetermined Change Control Plan (PCCP)** is a document filed in the original marketing submission that pre-specifies:
1. **The Description of Modifications** — the types of post-market changes the manufacturer anticipates (e.g., updates to the model architecture, retraining cadence, expansion of training data, performance-threshold tuning).
2. **The Modification Protocol** — the validation, testing, and quality-control procedures that each anticipated change must pass before deployment.
3. **The Impact Assessment** — analysis of how the anticipated changes affect device performance, safety, effectiveness, and the existing risk control measures.

Approved PCCP changes can be made post-market **without requiring a new 510(k), De Novo, or PMA supplement**, provided the changes stay within the pre-specified envelope.

## Regulatory Logic
PCCPs move the change-control burden from the back end of the lifecycle (re-submission for every iteration) to the front end (pre-specify what iteration looks like). The economic effect: faster post-market improvement cycles for AI devices, conditional on rigorous up-front validation infrastructure.

This is the regulatory operationalisation of the **Total Product Life Cycle (TPLC)** framing FDA has pushed for AI devices since 2019.

## What's New in the Final Guidance vs. April 2023 Draft
- Final guidance applies to a broader range of AI-DSF, not just AI/ML SaMD
- More explicit treatment of post-market performance monitoring requirements
- Clearer alignment with FDA's broader AI/ML lifecycle framework

## Significance for Hearing / Implant Devices

### Hearing Aids
Modern OEM hearing aids (Phonak Sphere Infinio, ReSound Vivia, Starkey Edge AI, Oticon platforms) already ship firmware updates to paired-smartphone-mediated devices. PCCP is the regulatory vehicle that makes the AI-update layer above firmware tractable.

### Cochlear Implants
Until now, PCCP-authorised devices have been dominated by SaMD — diagnostic AI running on cloud or PC. The launch of the **Cochlear Nucleus Nexa System** in 2025 — the first medical-grade implantable device with post-implant firmware updateability — drags PCCP into Class III implantables.

See [[cochlear-nucleus-nexa-smart-implant-2026]] for the device-side story.

## Open Questions for Hearing / CI Manufacturers
1. **Allocation:** When updates ship, who is on which version, when, with what consent and evidence?
2. **Cohort stationarity:** Long-term outcome studies (e.g., 5-year speech-in-noise outcomes) become firmware-versioned multi-cohort analyses rather than single trajectories.
3. **Plasticity costs:** For implants, the auditory cortex has adapted to v1; v2 updates may carry plasticity costs the original trial protocol did not price.
4. **Liability:** Who is liable when a firmware update introduces a regression — the manufacturer, the fitting clinician, the regulator?

## Related
- [[software-defined-medical-implants]] — concept-level framing
- [[cochlear-implant-ai]] — algorithmic landscape
- [[on-device-ml-hearing-aids]] — hearing-aid analog
- [[eu-ai-act-medical-devices]] — European parallel framework
