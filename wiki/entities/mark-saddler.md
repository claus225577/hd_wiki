---
title: Mark Saddler
type: entity
created: 2026-06-20
updated: 2026-06-20
sources: [saddler-mcdermott-2024-nature-comms-temporal-coding.md, saddler-clarity6-2025-individualized-hi-models.md, vcca2026-pre-conference-workshops-jun-19-2026.md]
related: [../concepts/task-optimized-dnn-as-auditory-model.md, ../concepts/differentiable-cochlear-models.md]
tags: [researcher, dtu, mit, mcdermott-lab, computational-audition, task-optimized-dnn, postdoc]
---

# Mark Saddler

Postdoctoral researcher in the Hearing Systems Research Section, Department of Health Technology, Technical University of Denmark (DTU). Previously postdoc / PhD with Josh H. McDermott at MIT's Computational Audition Lab. Personal page: https://msaddler.github.io/.

## Research program

Saddler develops deep-learning models of human auditory perception. His method trains task-specific DNNs to perform everyday hearing tasks (speech-in-noise, sound localization, pitch estimation) on the output of biophysically faithful cochlear simulators, then compares trained-model behavior to human listener behavior. The trained network functions as a falsifiable scientific hypothesis about how the human auditory system solves the task. See [[../concepts/task-optimized-dnn-as-auditory-model]].

Three research strands:

1. **Auditory-nerve phase locking** — is precise spike timing necessary for human auditory behavior? Saddler & McDermott (Nat Comms 2024) showed temporal-coding requirements are task-dependent, not universal.
2. **Pitch perception** — Saddler, Gonzalez, McDermott (Nat Comms 2021) — human-like pitch behavior emerges only when cochleae have high temporal fidelity and models are optimized on naturalistic sounds.
3. **Hearing loss and assistive technology** — Saddler, Dau, McDermott (Clarity-6 2025) extends the program to HI listeners; key finding is that the hearing aid drives more variance in intelligibility than the listener does in current datasets.

## Public engagement

- **VCCA 2026 Pre-Conference Workshop 2 — "A Practical Introduction to Machine Learning for Hearing Science"** (Friday, June 19, 2026). Hands-on Jupyter notebooks; materials on GitHub. This is the first time the audiology community's flagship virtual conference has run a foundational ML lab in its pre-conference track — significant for the discipline-formation timeline of ML in audiology.

## Strategic relevance for the hearing-aid industry

Saddler's program is the cleanest current articulation of a future fitting paradigm where the deployed device is tuned not against a population audiogram but against a per-wearer simulated periphery + behavioral DNN. Whoever in industry builds the operational pipeline that runs this framework against in-situ wearer telemetry first controls the most data-efficient personalization substrate.

## Related Pages

- [[../concepts/task-optimized-dnn-as-auditory-model]] — the methodological frame.
- [[../concepts/differentiable-cochlear-models]] — the optimization machinery that makes per-wearer fitting tractable.

## Sources

- [Saddler & McDermott (Nat Comms 2024)](../../sources/saddler-mcdermott-2024-nature-comms-temporal-coding.md)
- [Saddler, Dau, McDermott (Clarity-6 2025)](../../sources/saddler-clarity6-2025-individualized-hi-models.md)
- [VCCA 2026 Pre-Conference Workshops (Jun 19, 2026)](../../sources/vcca2026-pre-conference-workshops-jun-19-2026.md)
