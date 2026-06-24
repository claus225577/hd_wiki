---
title: Enrique A. Lopez-Poveda
type: entity
created: 2026-06-24
updated: 2026-06-24
sources: [vcca-2026-main-programme-june-2026.md, vcca2026-conference.md, vcca2026-pre-conference-workshops-jun-19-2026.md]
related: [../concepts/differentiable-cochlear-models.md, ../concepts/task-optimized-dnn-as-auditory-model.md, ../concepts/cochlear-implant-ai.md, ../concepts/efferent-moc-feedback-hearing-ai.md, vcca-computational-audiology.md, mark-saddler.md, ../syntheses/clinical-ml-convergence-june-2026.md]
tags: [person, researcher, audiologist, salamanca, spain, computational-auditory-models, cochlear-models, cochlear-implant, moc-efferent, vcca-2026-keynote]
---

# Enrique A. Lopez-Poveda

Professor at the **Universidad de Salamanca** (Instituto de Neurociencias de Castilla y León / IBSAL), one of the senior figures in **computational auditory modelling** in Europe. Long-running research programme on cochlear and brainstem models, with extensions into hearing-aid signal processing, cochlear-implant sound coding, and medial-olivocochlear (MOC) efferent feedback.

## 2026 Recognition

**VCCA 2026 Day 2 Keynote (Jun 26, 2026):** *"Computational Auditory Models in the Service of Improving Audiology."*

The keynote title is the clearest single statement on the VCCA 2026 programme of the "computational model as substrate, not sidecar" thesis: computational auditory models (cochlear, brainstem, cortical) are not just research tools — they are operational infrastructure for clinical and engineering audiology. The framing aligns with three other strands on the same programme:
- Saddler's Session 4.A talk "Perceptual Sensitivity is Explained by Optimization for Ecological Hearing Tasks" (task-optimized DNNs as auditory models).
- Van Heghe's Session 5.B talk "Neural Response-Driven Optimization of CI Stimulation Using Differentiable Auditory Models" (CI-side use of the same operator family).
- Banerjee's Pre-Conference Workshop 3 "Computational Models of the Auditory Periphery: From Normal Hearing to Impairment" (educational substrate).

Together, four independent groups on the same VCCA naming computational auditory models as the substrate the audiology field should be building on.

## Structural Contributions to the Field

### 1. Computational cochlear modelling

Long-running programme on biophysically grounded models of the cochlear filterbank, including dual-resonance non-linear (DRNL) filter models that have been widely adopted in hearing-aid and CI research. The Lopez-Poveda DRNL line of work sits in the lineage that leads through CARFAC (Lyon) to the Google DAL (Ballesta Rosen et al. 2026) — the differentiable cochlear model now operational inside training loops.

See [[../concepts/differentiable-cochlear-models]].

### 2. Medial olivocochlear (MOC) efferent feedback

Lopez-Poveda's group has been one of the most active in formalising the role of the **MOC reflex** — the brainstem-controlled efferent feedback loop that adjusts cochlear gain in response to descending auditory cortex / brainstem signals — as a candidate substrate for *scene-conditioned* gain control in hearing aids. The MOC reflex is the biological precedent for what an "intelligent gain controller" in a hearing aid should be doing.

See [[../concepts/efferent-moc-feedback-hearing-ai]].

### 3. Cochlear-implant sound coding from a model-based perspective

Extensions of the computational-auditory-model framework into CI sound-coding strategies — using biophysically faithful periphery models as the target the CI stimulation pattern should be reconstructing in the auditory nerve. Adjacent to Van Heghe's VCCA 2026 talk and to the broader CI-AI programme.

### 4. Salamanca as a computational-audiology hub

The Lopez-Poveda group at Salamanca, in combination with Helia Relaño-Iborra at Eriksholm (also Spanish), gives Spain an outsized footprint at VCCA 2026 — beyond the conference being hosted from Spain. Spain has emerged as one of the most active European nodes in computational audiology, comparable in concentration to Oldenburg (HA signal processing), Cambridge (CI signal processing), Tübingen (OHC biology / pharmacology), and Mass Eye and Ear (synaptopathy / gene therapy).

## Why This Matters for Hearing AI / Data Science

### Names the substrate the differentiable / task-optimized side is implicitly building

Saddler's task-optimized-DNN-as-auditory-model and the Google DAL differentiable cochlear model are both, in essence, operationalisations of the Lopez-Poveda framework: take a biophysically grounded computational model of the auditory periphery, plug it into the training loop, and train against it. Lopez-Poveda's keynote names what these papers are doing in the language the clinical audiology field uses.

### MOC as a candidate ML operator

The MOC reflex is a candidate biological-precedent architecture for scene-conditioned gain control in hearing aids — one of the few biological loops that has a clear ML analogue (closed-loop gain modulation by an upstream classifier). Several recent ML papers (efferent / closed-loop SE, scene-conditioned amplification) cite the MOC reflex as motivation; Lopez-Poveda's group is the primary academic source on the substrate.

### Bridge from physiology to fitting

Computational auditory models give the field a path from physiological measurements (otoacoustic emissions, ABR, EHF audiometry) directly to per-wearer fitting parameters — without the audiogram as intermediate. This is the same direction the Hidden HL / Acousia / Saddler programmes are pulling: away from audiogram-as-sole-input toward physiology-and-perceptual-model as inputs.

## Related Pages

- [[../concepts/differentiable-cochlear-models]] — The differentiable lineage that operationalises Lopez-Poveda's computational-model framework.
- [[../concepts/task-optimized-dnn-as-auditory-model]] — Saddler-side operationalisation.
- [[../concepts/cochlear-implant-ai]] — CI-side operationalisation (Van Heghe VCCA 2026 talk).
- [[../concepts/efferent-moc-feedback-hearing-ai]] — MOC reflex as a candidate biological-precedent operator family.
- [[vcca-computational-audiology]] — VCCA 2026 keynote context.
- [[mark-saddler]] — Saddler's task-optimized-DNN programme is the ML-side operationalisation.
- [[../syntheses/clinical-ml-convergence-june-2026]] — Lopez-Poveda's keynote sits naturally inside the clinical-ML-convergence synthesis.

## Sources

- [VCCA 2026 Main Programme](../../sources/vcca-2026-main-programme-june-2026.md) — Day 2 keynote.
- [VCCA 2026 Conference Overview](../../sources/vcca2026-conference.md) — Programme structure.
- [VCCA 2026 Pre-Conference Workshops](../../sources/vcca2026-pre-conference-workshops-jun-19-2026.md) — Banerjee periphery-model workshop context.
