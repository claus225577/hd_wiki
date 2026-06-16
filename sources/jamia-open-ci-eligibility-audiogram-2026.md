---
title: "Advancing clinical utility of artificial intelligence: lessons from developing a model to predict cochlear implant eligibility"
url: https://academic.oup.com/jamiaopen/article/9/2/ooag024/8526583
date: 2026-04-01
type: paper
journal: JAMIA Open
tags: [cochlear-implant, ci-eligibility, audiogram, machine-learning, clinical-decision-support, referral, ml-clinical-utility]
---

# JAMIA Open — ML for Cochlear Implant Eligibility Prediction

## Key Extractions

- **Venue:** JAMIA Open (Journal of the American Medical Informatics Association — Open), 2026.
- **Question:** Given a routine audiogram, who meets cochlear-implant candidacy criteria and should be referred for evaluation?
- **Method:** ML pipeline trained on audiogram features (pure-tone thresholds + speech-perception inputs where available) labeled against documented CI candidacy.
- **Finding:** ML model **flags CI-eligible adults from routine audiograms** with performance materially above current referral heuristics (e.g., "60/60 rule" — 60% WRS at 60 dB).
- **Framing:** The paper is positioned not as a benchmark race but as a clinical-utility / deployment lessons paper — what it took to push a CI-eligibility classifier through to clinician workflow integration.

## Relevance to Hearing + AI

- **Under-referral is the binding constraint.** Only ~5–10% of CI-eligible adults in the US are actually implanted; the gap is largely a *referral* problem (audiologists not flagging candidates, ENTs not seeing them). An ML model that turns the existing audiogram pile into a referral filter directly attacks the bottleneck.
- **Audiogram-as-input is realistic.** Unlike pre-implant MRI prediction (Hong Kong / Australia / US pediatric study, 92% accuracy) which requires neuroimaging, this approach uses data every audiologist already collects. Deployment surface is the existing EHR.
- **Companion to the outcome-prediction lineage.** Outcome prediction (will this person benefit?) and eligibility prediction (does this person meet candidacy?) are different ML problems; the field needs both. JAMIA Open paper sits on the eligibility side.
- **JAMIA Open as venue.** Publishing in a clinical-informatics journal rather than an audiology one is a signal that CI-eligibility ML is being treated as a *clinical decision support* problem, not an audiology research problem — which changes who reads it and who deploys it.
- **Pairs with audiologist-shortage thread.** Automated referral filters on the audiogram pile are one of the most direct technological responses to the audiologist workforce gap.

## Cross-references

- Companion outcome-prediction work: Pediatric CI language outcomes (Hong Kong / Australia / US, 92% accuracy on pre-implant MRI).
- Largest CI outcome prediction study to date: 4,046 patients across 32 US institutions (Ear and Hearing, Sept 2025).
- LUCIA bilateral CI trial (UK, May 2026) — generates labeled adult cohort for second-CI outcome prediction.
- Related concept page: [[automated-audiometry]] — audiogram-as-input ML pipeline.
- Related concept page: [[cochlear-implant-ai]] — full CI AI landscape.
