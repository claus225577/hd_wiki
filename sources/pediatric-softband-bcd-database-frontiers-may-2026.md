---
title: Retrospective review of softband bone conduction hearing device fittings and outcomes from routine clinical care
type: research-paper
date: 2026-05-08
journal: Frontiers in Audiology and Otology
url: https://www.frontiersin.org/journals/audiology-and-otology/articles/10.3389/fauot.2026.1800016/full
tags: [bone-conduction, pediatric-audiology, softband, candidacy-expansion, telemetry, clinical-database, peach, real-world-evidence, ome, microtia]
---

# Pediatric Softband BCD Database — 5,490 Children Across 28 Years (Frontiers — 8 May 2026)

## Key Extractions

### Study Design
- Two-part retrospective review of routine-clinical-care fittings within a publicly-funded pediatric audiology system.
- **Study A:** 5,490 children fitted with bone-conduction devices (BCDs) over 1998–2025.
- **Study B:** 200 children with long-term softband-BCD use, deeper outcome capture.

### Headline Outcomes
- **PEACH score 46.4% unaided → 82.4% aided** (p = 0.003).
- **74% regular daily use** — a strong adherence signal in pediatrics.
- **Speech perception aided > 80%** across test conditions.
- Functional benefit consistent across etiology groups, including OME.

### The Striking Finding
- **88% of fittings were *not* the textbook microtia/atresia population.**
- The fitted population spanned:
  - Otitis media with effusion (OME)
  - Craniofacial anomalies
  - Cleft palate
  - "Unknown etiology"
  - Syndromic and acquired hearing losses
- Children with bilateral OME demonstrated **similar functional benefit** to those with congenital conductive losses — the historical candidacy gate.

### Authors' Conclusion
- Routine clinical care has been delivering BCDs to a much broader pediatric population than guideline indications historically supported.
- Outcomes within this expanded population are robust enough to support broader candidacy explicitly.
- Provides the first large-scale characterization of contemporary fitting practices within a publicly-funded pediatric audiology system.

## Relevance to Hearing-Tech Data Science

### Telemetry as Warrant
- Candidacy expansion happened in the *data* before it happened in the *guideline*.
- The dataset is not from a designed RCT — it is the byproduct of routine clinical care, captured at scale across 28 years.
- This is the canonical "telemetry becomes evidence" pattern that hearing aid R&D has been talking about but rarely delivering on.

### Why It Matters for Hearing Aid R&D
- **Boring, durable, longitudinal usage data** is more powerful than any single flashy model.
- Routine fitting and wear-time telemetry, if captured uniformly, becomes:
  - The defensible warrant for candidacy expansion
  - The labeled set for ML personalization
  - The differentiator in regulatory and reimbursement conversations
- Manufacturers / clinics that don't treat routine fitting/usage telemetry as a strategic asset are leaving a regulatory and reimbursement moat unbuilt.

### Pairs With
- LUCIA Trial (May 6, 2026) — the inverse pattern: an RCT created where natural cohorts were absent.
- Apple Hearing Study (May 2026) — telemetry-at-scale from consumer devices producing population-scale insight.
- WSA Sound Preference Tool (Apr 2026) — explicit attempt to add structured fields to fitting records.
- Knipper hidden-hearing-loss / digital-phenotyping work — the principle that signal exists in routine data if you collect it cleanly.

### Open Questions
- Which fitting-record fields would have changed the analysis if they had been structured? (Wear time, follow-up adherence, reason-for-visit, lateralization, custom-mold remake count, etc.)
- Could a similar 5,000-patient hearing-aid telemetry study, on a publicly-funded system, run today? Most national systems still don't capture wear-time telemetry as a structured field.
- What would the equivalent guideline-expansion be in adult hearing aids?

## Cross-References Within Wiki
- [[../wiki/concepts/longitudinal-hearing-phenotyping]] — telemetry-as-evidence backbone
- [[../wiki/concepts/closed-loop-data-flywheel]] — fitting → outcome → guideline as a flywheel pattern
- [[../wiki/concepts/teleaudiology]] — adjacent context for pediatric remote care
- [[../wiki/concepts/digital-phenotyping-cognitive-decline]] — methodological cousin (passive routine signal as evidence)
- [[../wiki/syntheses/hearing-aid-market-outlook]] — implications for candidacy-driven market expansion

## Limitations
- Single publicly-funded system — generalization to private-payor systems may differ.
- Retrospective design — selection effects on which children entered the BCD pathway not fully controlled.
- PEACH is a parent/caregiver-rated instrument; subjective signal weight should be acknowledged.
- "Unknown etiology" category absorbs heterogeneity that future structured datasets should disaggregate.
