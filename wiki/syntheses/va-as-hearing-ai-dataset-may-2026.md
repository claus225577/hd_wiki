---
title: The U.S. Department of Veterans Affairs as a Hearing-Aid AI Dataset — Three OEM Cluster, May 12–19, 2026
type: synthesis
created: 2026-05-19
updated: 2026-05-19
sources:
  - oticon-va-portfolio-zeal-intent-verit-may-2026.md
  - signia-active-mini-ix-may-2026.md
  - starkey-omega-ai-government-services-may-2026.md
related:
  - demant-oticon.md
  - ws-audiology-signia.md
  - starkey.md
  - hearing-aid-market-dynamics.md
  - closed-loop-data-flywheel.md
  - longitudinal-hearing-phenotyping.md
  - hearing-aid-ai-stack-2026.md
tags: [va, veterans-affairs, distribution-channel, dataset, telemetry, closed-loop, outcomes-data, oem-cluster, synthesis]
---

# The VA as a Hearing-Aid AI Dataset — Three OEM Cluster, May 12–19, 2026

## The Cluster

Within a single seven-day window in May 2026, three of the largest hearing-aid OEMs added premium AI platforms or platform updates to the U.S. Department of Veterans Affairs contract:

| OEM | Devices / Update | Date |
|-----|------------------|------|
| **Oticon (Demant)** | Zeal (rechargeable ITE, BrainHearing + new DNN sound processing), Intent miniBTE R (4D-sensor-driven, BLE Audio), Verit miniRITE T (value-tier) | early May 2026 |
| **Signia (WSA)** | Active Mini IX (instant-fit ITE on full Integrated Xperience platform), CIC Rechargeable Custom IX, Silk IX, Active Pro IX (Signia Assistant + RTCE) | week of May 12, 2026 |
| **Starkey** | Omega AI for Government Services with Auracast Assistant, Push to Talk, Google Fast Pair, StarLink Edge LE Adapter | May 1, 2026 (Government Services rollout); industry coverage week of May 12 |

These are not coordinated. They are three independent commercial decisions converging on the same channel within seven days. That convergence is the substrate for this synthesis.

## What the VA Actually Is, from a Data-Science Vantage

The VA is **the world's second-largest single hearing-aid dispenser**, after the UK's NHS. Public market commentary commonly states it accounted for ~18% of U.S. hearing-aid units in 2022. (Note: an earlier source file states "largest single hearing-aid purchaser globally" — this is consistent with US-only framing but inaccurate globally; NHS dispenses more units.)

Beneath the volume sit five properties that make the VA structurally unique as a hearing-aid AI dataset:

1. **A single electronic health record (CPRS / VistA)** with standardized fields for hearing diagnoses, hearing-aid orders, and outcome measures across all VA medical centers.
2. **Standardized fitting protocols** with strong consistency across audiologists trained inside the VA system.
3. **Structured outcome instruments** — APHAB, COSI, HHIE-S, AzBio, QuickSIN — recorded across visits, often longitudinally, in machine-readable fields.
4. **Demographically narrow but rich population** — ~9M enrolled veterans, disproportionately older, disproportionately noise-exposed, with high prevalence of tinnitus, TBI, PTSD, vestibular dysfunction, and cognitive decline. Comorbidity data is already linked at the patient level.
5. **Decades of longitudinal continuity** inside a single payer — a hearing-aid wearer fitted in 2002 may have continuous records through 2026.

For ML purposes, that combination — high volume, standardized outcomes, demographically rich, longitudinally continuous, comorbidity-linked — exists nowhere else in the world at scale. The NHS is larger by units but more fragmented across NHS Trusts and HIMSA-style fitting software variants. Private OEM telemetry is richer per-device but disconnected from clinical outcomes.

## What the Cluster Could Become — IF the Telemetry Is Connected

With three OEMs simultaneously deployed at scale into a standardized-outcome population, the VA is structurally a **multi-arm natural experiment**:

- Outcome equity across OEM platforms (do APHAB scores actually differ between Omega AI and Integrated Xperience after controlling for fitting audiologist?)
- AI-feature effectiveness in older, noise-exposed populations (does Auracast Assistant uptake correlate with hearing handicap reduction?)
- Candidacy expansion warrant (does Active Mini IX's same-day fitting reduce drop-off vs custom ITE in this population?)
- Comorbidity-conditional fitting (do TBI patients fitted with 4D-sensor BrainHearing show different adherence than non-TBI controls?)

These are not hypothetical questions. The data to answer them is already being recorded in CPRS / VistA. What is missing is the bridge from device-side telemetry to the EHR-side outcomes.

## What Is Missing — the Telemetry + Outcome Bridge

Today, device-level telemetry — sound-classifier transitions, gain changes, app interactions, wear time, in-situ environment statistics — almost never flows back into either OEM ML pipelines or VA outcome models. The contract delivers the chip. It does not deliver the feedback signal.

Three barriers:

1. **Regulatory.** Veteran PHI flowing out of CPRS to a private OEM is a high friction operation under VA Directive 6500, even with patient consent and de-identification.
2. **Technical.** Most hearing aids have very limited on-device storage; telemetry retention windows are short; companion-app data ownership is fragmented across OEMs.
3. **Incentive.** OEMs compete on premium-tier sales into the VA, not on telemetry-side science. There is no contract clause obliging telemetry return.

What an audit-clean telemetry + outcome pipeline would need to look like, at minimum:

- Device-side de-identification at the OEM SoC level, with no raw audio leaving the aid.
- A standardized telemetry schema across OEMs (analogous to FHIR for EHR) that the VA could ingest into VistA-side analytic warehouses.
- IRB-approved patient-consent flow at the time of fitting, with opt-in granularity by data type.
- A queryable outcome layer linking telemetry events to APHAB/COSI deltas — the actual closed-loop signal.

## Strategic Implications

- **The competitive frontier in the VA channel for the next five years will not be portfolio breadth.** All three OEMs now have premium AI platforms in the schedule. The next differentiator is who can build a defensible telemetry + outcome bridge that the VA, IRB, and patient will accept.
- **First-mover advantage on telemetry pipelines compounds.** Once an OEM has a structured outcome bridge, every subsequent algorithm release inherits the closed-loop signal; competitors without it ship blind.
- **The structural moat shifts from chip to dataset.** The chip race is fought on watts and TOPS. The dataset race is fought on consent, IRB approval, schema, and EHR integration. These are different skill stacks. The OEM that fields both wins.
- **NHS UK is the analog on the other side of the Atlantic.** A second OEM cluster around NHS — likely 2027 — should be expected. The strategic playbook is portable.

## Connection to Other Wiki Threads

- **Closed-loop data flywheel** — the VA is the largest existing substrate where the loop could plausibly close at scale, IF the telemetry side is built.
- **Longitudinal hearing phenotyping** — VA's longitudinal continuity makes it the canonical substrate for digital phenotyping of hearing-aid wearers.
- **Care-partner dyad models** — VA's enrolled-spouse data is structurally available and underused.
- **Audiologist workforce shortage** — VA audiology is overstretched; back-office AI (per AAA 2026 panel) targets exactly this constraint.

## Open Questions

- Will any OEM publicly commit to a VA telemetry-return pilot within the next 12 months?
- Could the Cooperative Research and Development Agreement (CRADA) mechanism — already used for Department of Defense hearing-protection work — provide the legal substrate for telemetry return?
- What would happen if the VA RFP'd a multi-OEM standardized telemetry schema? (It hasn't. The leverage is asymmetric in the VA's favor here.)

## Sources
- [Oticon Expands U.S. VA Portfolio (May 2026)](../../sources/oticon-va-portfolio-zeal-intent-verit-may-2026.md)
- [Signia Active Mini IX (May 12, 2026)](../../sources/signia-active-mini-ix-may-2026.md)
- [Starkey — Omega AI Reaches Government Services (May 1, 2026)](../../sources/starkey-omega-ai-government-services-may-2026.md)
