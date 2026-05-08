---
title: Remote Cochlear Implant Programming in Real-Life Listening Environments — A Feasibility and Acceptability Study
type: research-paper
date: 2026-04-22
journal: Frontiers in Audiology and Otology
authors: Charlotte V. R. Snoeck, Martina Brendel, Jan-Willem A. Wasmann
affiliation: Radboud University Medical Center, Nijmegen
url: https://www.frontiersin.org/journals/audiology-and-otology/articles/10.3389/fauot.2026.1730079/full
doi: 10.3389/fauot.2026.1730079
tags: [cochlear-implant, teleaudiology, remote-fitting, ux, feasibility-study, real-world, cosi, ecological-validity, advanced-bionics, labeled-data]
---

# Remote CI Programming in Real-Life Listening Environments (Snoeck, Brendel, Wasmann — Apr 22 2026)

## Key Extractions

### Study Design
- Within-subject feasibility and acceptability study on remote CI programming conducted in participants' **actual real-life listening environments**, not the clinic.
- **n = 12** post-lingually deafened CI users, mean age 62.
- 4 visits per participant over 2–4 months:
  - Session 1: in-clinic baseline + COSI goal-setting
  - Session 2: remote fitting at home in a quiet environment
  - Session 3: remote fitting in an individually-chosen *challenging* environment (commute, office, restaurant, etc.)
  - Session 4: in-clinic follow-up
- Tools: Advanced Bionics Target CI v1.5 + Remote Support app; Client Oriented Scale of Improvement (COSI); custom satisfaction surveys.

### Results
- **All 12 participants** would recommend remote fitting; 6/12 high satisfaction, 4/12 satisfied.
- **Best-aided speech-in-quiet stable** within ≤4 percentage points at the group level — i.e., no safety degradation.
- **37 patient-defined COSI goals** addressed:
  - 10 rated "much better"
  - 8 rated "better"
  - 4 rated "a little better"
  - 12 "no improvement"
  - All 12 participants achieved improvement on ≥1 goal.
- Cited benefits: time/cost savings (9/12), improved fitting in real-world contexts (8/12), scheduling flexibility (7/12).
- Pain points: technical issues (7/12), reduced non-verbal cues (6/12), lip-sync/audio interruptions, connection instability.

### Authors' Framing
- Existing remote-CI evidence has focused on **clinical equivalence** in quiet — necessary but no longer the binding question.
- The unique advantage of remote fitting is to **adjust settings inside the actual environment that bothers the patient** — shorter feedback loops, ecologically valid context.
- Adoption remains stuck at ~14% in the Netherlands despite a decade of equivalence evidence; reframing remote care as ecological-validity care, not clinic-replacement care, may unlock further adoption.

### Implementation Notes
- Keep remote sessions short to avoid Zoom fatigue.
- Focus on one COSI goal per session.
- Avoid for low-performing users who rely on lip-reading without in-person support.

## Relevance to Hearing-Tech Data Science

### Triple of (Settings × Context × Outcome) — A New Labeled Dataset
Each remote in-situ fitting now produces:
- **Programming change** — concrete parameter delta in the CI map
- **In-situ acoustic context** — the actual environment that motivated the change
- **Subjective outcome (COSI)** — patient-rated improvement on their goal
This triple cannot be assembled from sound-booth fittings. With telemetry, it is a labeled training set for context-aware CI mapping that finally generalizes outside the clinic — a structural advance over today's clinic-trained ML.

### Bottleneck Has Shifted
- Not audiology workflow.
- Not clinical equivalence.
- It is **UX and connectivity infrastructure**, plus reimbursement.

### Connects to
- Teleaudiology and remote care trend.
- Audiologist workforce shortage — remote multiplies clinician reach.
- Closed-loop data flywheel — every in-situ session can feed firmware.
- Computational audiology research community (VCCA).

## Limitations
- Small n; uncontrolled within-subject design.
- Single-manufacturer (Advanced Bionics) software path.
- Self-selected "real-life" environments — potentially most-motivated subset.
- Effect on objective sentence-in-noise scores in noisy environments not measured.

## Cross-References Within Wiki
- [[../wiki/concepts/teleaudiology]] — primary concept hosting this evidence
- [[../wiki/concepts/cochlear-implant-ai]] — context for CI mapping ML
- [[../wiki/concepts/closed-loop-data-flywheel]] — feedback-loop framing
- [[../wiki/concepts/audiologist-workforce-shortage]] — access motivation
- [[../wiki/entities/advanced-bionics]] — software platform used
- [[../wiki/entities/vcca-computational-audiology]] — research venue alignment
