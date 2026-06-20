---
title: "Models optimized for real-world tasks reveal the task-dependent necessity of precise temporal coding in hearing"
type: paper
authors: ["Mark R. Saddler", "Josh H. McDermott"]
venue: "Nature Communications"
year: 2024
date_ingested: 2026-06-20
tags: [task-optimized-dnn, auditory-periphery, phase-locking, temporal-coding, sound-localization, mit, mcdermott-lab, dnn-as-model]
---

# Models optimized for real-world tasks reveal the task-dependent necessity of precise temporal coding in hearing

**Authors:** Mark R. Saddler, Josh H. McDermott
**Venue:** Nature Communications (2024)
**Lab:** McDermott Computational Audition Lab, MIT
**URL:** https://www.nature.com/articles/s41467-024-XXXXX (link via Saddler's publication page: https://msaddler.github.io/publications/)

## Core finding

Deep neural networks trained to perform everyday auditory tasks (speech recognition, sound localization, pitch estimation) on the output of biophysically faithful cochlear simulators were used as in-silico models of human auditory perception. The headline result: models with high-fidelity auditory-nerve phase locking exhibited more human-like sound localization and speech perception than models with degraded temporal precision. Critically, the precision of temporal coding required to match human behavior was *task-dependent* — not a single universal threshold across all auditory functions.

## Method

- Build a parameterized peripheral auditory model (cochlear filterbank + inner-hair-cell → auditory-nerve response).
- Vary the upper cutoff of auditory-nerve phase locking, generating a family of biologically plausible peripheries.
- Train task-specific DNNs on each periphery to perform the auditory task end-to-end on natural-sound stimuli.
- Compare trained-DNN behavior (errors, biases, psychometric curves) against human listener data on the same task.
- The periphery that produces a DNN whose mistakes match human mistakes is the periphery most consistent with how humans solve that task.

## Why this matters for the hearing-aid field

- **The model is the experiment.** Most ML in hearing aids treats the trained model as an engineering deliverable (a denoiser, a fitting algorithm). Saddler & McDermott's framing treats the model as a falsifiable scientific hypothesis about how human hearing actually works.
- **Task-dependence is a fitting-algorithm constraint.** If different auditory tasks need different temporal-coding fidelity, then a single one-size-fits-all peripheral model (and hence a single hearing-aid signal-processing pipeline) cannot be optimal across speech-in-noise, localization, music, and pitch tasks simultaneously.
- **Companion to differentiable cochlear models.** This program is upstream of the [[../wiki/concepts/differentiable-cochlear-models]] thread — it tells you which peripheral features to make differentiable and against which behavioral target.

## Cross-references

- Companion 2025 work: [[saddler-clarity6-2025-individualized-hi-models]] — extends the framing to hearing-impaired listeners, with the humbling finding that most variance came from the hearing aid, not the listener.
- Saddler's VCCA 2026 pre-conference ML workshop: [[vcca2026-pre-conference-workshops-jun-19-2026]].
- Concept page: [[../wiki/concepts/task-optimized-dnn-as-auditory-model]].

## Carry-Forward Flags
- Whether the task-dependent temporal-precision result generalises to in-ear-microphone speech, beyond the lab's stimulus set.
- Whether a fitting algorithm tuned against a task-optimized DNN's behavior outperforms one tuned against population audibility curves.
