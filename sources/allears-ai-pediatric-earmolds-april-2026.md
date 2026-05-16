---
title: "ALLEars — AI-Predicted Custom Pediatric Earmolds (Western University × Boys Town)"
authors: [Susan Scollie, Soodeh Nikan, Joshua Pearce (Western University), Ryan McCreery (Boys Town National Research Hospital)]
date_published: 2026-04
date_ingested: 2026-05-15
url: https://news.westernu.ca/2026/04/ai-custom-earmolds-children-hearing-aids/
type: news-research-announcement
venue: Western News (Western University)
funder: Oberkotter Foundation
funding_amount_usd: 4400000
funding_term_years: 4
tags: [pediatric-hearing, custom-earmolds, ml-prediction, 3d-printing, ear-canal-growth, mirroring, open-source-medical, ear-impression, cochlear-implant-adjacent, allears]
---

# ALLEars — AI-Predicted Custom Pediatric Earmolds

## Summary

Multi-institution collaboration applying machine learning to pediatric ear-canal growth prediction so that custom earmolds can be 3D-printed in advance of fit drift. Funded by the Oberkotter Foundation at $4.4M USD over four years. Software to be released openly to the global hearing-healthcare community.

## Project Architecture

- **ML growth prediction:** Models trained on large datasets of pediatric ear impressions learn how the ear-canal shape evolves over months/years, allowing earmold geometry to be projected forward rather than reactively re-impressed each time fit fails.
- **Mirroring:** A second model predicts one ear's geometry from the other, halving the impression burden on young children — clinically meaningful because impression-taking is invasive and stressful for pediatric patients.
- **3D-printing pipeline:** Predicted geometries feed a 3D-printing manufacturing flow that produces molds before they are needed, eliminating the wait-then-refit gap that currently fragments early language-development support.
- **Open release:** Software stack will be openly distributed — a deliberate counter to the closed proprietary fit-software lineage of the major OEMs.

## Lead Personnel

- **Susan Scollie (Western University)** — lead investigator; longtime author of pediatric prescription-formula research (DSL line)
- **Soodeh Nikan (Western University)** — AI lead
- **Joshua Pearce (Western University)** — additive manufacturing / 3D printing
- **Ryan McCreery (Boys Town National Research Hospital, Nebraska)** — pediatric audiology / acoustic prediction

## Why It Matters

- **Critical-window framing:** Hearing-aided pediatric language development is bounded by a narrow neurodevelopmental window. Each refit gap is a measurable loss of high-quality auditory input during that window. Predictive manufacturing converts a reactive workflow into a planned one.
- **Open-source pediatric stack:** Most upstream hearing-aid software (fit formulas, REM models, verification) is proprietary OEM-bundled. Open release of pediatric tooling is a structural shift in who can build pediatric audiology infrastructure (academic centers, low-resource regions).
- **Cross-domain ML application:** This is primarily a geometric-prediction / shape-modeling problem — closer in technique to medical-image segmentation and shape-completion ML than to the speech-enhancement DNN lineage that dominates HA AI conversation.

## Limitations / Open Questions

- Dataset provenance and demographic coverage of the impression training set not publicly detailed; growth trajectories likely vary by ethnicity, age band, and underlying syndromic status.
- Validation pathway against gold-standard impression-fit not yet published.
- Mirroring assumption (left/right symmetry) may not hold for syndromic populations where hearing intervention is most acute.

## Coverage

- Western News announcement (Apr 2026): https://news.westernu.ca/2026/04/ai-custom-earmolds-children-hearing-aids/

## Related Wiki Pages
- [[../concepts/hearing-aid-prescription-formulas]] — Fit chain that earmold geometry feeds into
- [[../concepts/synthetic-data-for-hearing-ai]] — Data-pipeline analog (predicted geometries vs measured)
- [[../concepts/teleaudiology]] — Open-source pediatric tooling enables remote/low-resource workflows
