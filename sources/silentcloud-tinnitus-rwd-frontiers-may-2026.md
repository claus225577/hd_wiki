---
title: "Ringing in insights: analyzing real-world data from a tinnitus management application and its potential for transforming care"
type: academic-paper
date_published: 2026-05-07
date_ingested: 2026-05-11
journal: Frontiers in Audiology and Otology
volume: 4
doi: 10.3389/fauot.2026.1769291
url: https://www.frontiersin.org/journals/audiology-and-otology/articles/10.3389/fauot.2026.1769291/full
authors: [Raffael Schmitt, Maren Stropahl]
affiliation: Sonova AG, Research & Development, Stäfa, Switzerland
tags: [silentcloud, tinnitus, digital-therapeutics, icbt, real-world-data, adherence, sonova, retrospective-observational, thi]
---

# SilentCloud Real-World Data Analysis — Frontiers (May 2026)

## Summary

First peer-reviewed real-world outcomes paper for **SilentCloud**, Sonova's CE-marked and FDA 510(k)-cleared digital therapeutic for tinnitus. Retrospective observational analysis of app users who completed the internet-based cognitive behavioural therapy (iCBT) module, measured via the Tinnitus Handicap Inventory (THI).

## Key Numbers

- **Total registered users:** 17,271 across five European countries
- **iCBT completers analysed:** 63
- **Completion rate:** ~0.4% (registered → iCBT completion)
- **Mean THI reduction (completers):** −14.7 points (p < 0.001)
- **Effect size:** Cohen's d ≈ 0.69 (medium-to-large)
- **Clinically meaningful improvement (≥7 pts):** 63.5% of completers
- **Decreased THI overall:** 77.8% of participants

## Sample Characteristics

- Mean age 51.9 years (SD = 13.8)
- Average tinnitus duration: 8.5 years
- Tinnitus type: 79.3% tonal, 20.7% atonal
- Selection bias noted: completers older, higher baseline distress, prior treatment experience vs non-completers

## App Modules

- **Your Tinnitus Tutor** — Education and counselling
- Sound therapy options
- **Your Counselling Therapy** — iCBT module (the focus of this analysis)

## Methods

- One-sided paired-samples t-test
- Cohen's dav effect size
- Welch's t-test for between-group comparisons
- Holm–Bonferroni correction for multiple comparisons
- **No ML/AI methods reported** — traditional statistical analysis only

## Authors' Limitations

- "Observed pre–post improvements may partially reflect non-specific effects" — users engaged with multiple modules concurrently, so iCBT effect cannot be cleanly isolated
- High dropout (most users never engaged with therapy modules)
- Adherence barriers: motivation, habits, perceived benefit, lack of professional support

## Significance

**Industrial provenance:** Sonova R&D publishing real-world data from its own digital therapeutic. Demonstrates the company's intent to ground SilentCloud (acquired 2026, originally launched 2023) in peer-reviewed evidence, not just regulatory clearance.

**The funnel as the headline:** 17,271 → 63 completers is the chart that should drive the next research agenda. Efficacy among completers is established; the open ML problem is dropout prediction, sequence-aware intervention, content ordering, and (probably) dyadic onboarding once we accept the patient is rarely doing this alone.

**Cross-link to broader pattern:** Same adherence-funnel collapse appears across digital therapeutics broadly (Pear Therapeutics, Akili, Mahana) — this is not a tinnitus-specific problem.

## Related
- `wiki/entities/sonova-ag.md`
- `wiki/concepts/digital-therapeutics-tinnitus.md` (to be created)
- `wiki/concepts/care-partner-dyad-models.md` (adherence schema)
- `sources/sonova-silentcloud-acquisition-2026.md`
- `reference_silentcloud` memory (date verification — SilentCloud first launched 2023)
