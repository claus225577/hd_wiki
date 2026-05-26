---
title: M. Kathleen (Kathy) Pichora-Fuller
type: entity
created: 2026-05-26
updated: 2026-05-26
sources: [wca-2026-pichora-fuller-aram-glorig-may-26-2026.md, world-congress-audiology-seoul-may-2026.md]
related: [../concepts/listening-effort-evaluation.md, ../concepts/communication-accessibility-metric.md, ../concepts/subjective-objective-hearing-gap.md, ../concepts/hearing-loss-dementia-link.md, ../concepts/multimodal-hearing-assessment.md, ../concepts/cortical-reorganization-hearing-aids.md, vcca-computational-audiology.md, who-hearing-program.md]
tags: [person, researcher, cognitive-audiology, fuel-framework, listening-effort, healthy-aging, communication-accessibility, who-rehabilitation-alliance, aram-glorig-award]
---

# M. Kathleen (Kathy) Pichora-Fuller

Professor Emerita, Department of Psychology, University of Toronto; Adjunct Professor, Department of Gerontology, Simon Fraser University, Vancouver. Among the most cited figures in cognitive audiology and the architect of the field's bridge from audiogram-side measurement to lived-experience outcomes.

## 2026 Recognition

**Aram Glorig Award (2026)** — The International Society of Audiology's highest honor — for "distinguished and lasting contribution to the field of Audiology." Presented at the **37th World Congress of Audiology (WCA 2026 Seoul, 26 May 2026)** alongside the award lecture **"Hearing and Healthy Aging: The Imperative for Communication Accessibility."** See [[../../sources/wca-2026-pichora-fuller-aram-glorig-may-26-2026]].

## Structural Contributions to the Field

### 1. FUEL — Framework for Understanding Effortful Listening (2016)

Co-authored with Sophia Kramer and colleagues following the 2015 Eriksholm Workshop; published as a supplement in *Ear and Hearing* (2016). FUEL operationalizes the listening experience as the interaction of:

- **Demand** — acoustic + linguistic + cognitive task load
- **Resources** — sensory + cognitive + executive capacity
- **Motivation** — effort the listener is willing to expend

This is structurally different from prior listening-effort accounts because it makes **motivation** a first-class variable. A listener with the same demand and resources will allocate different effort depending on context, fatigue, social stakes, and reward — and that allocation is the variable that determines real-world device acceptance, not raw intelligibility. See [[../concepts/listening-effort-evaluation.md]].

### 2. Three Decades of Cognitive-Audiology Work

Foundational papers establishing that cognitive load is the missing variable connecting the audiogram to lived-experience outcomes:

- **Pichora-Fuller & Singh (2006)** — Effects of age on auditory and cognitive processing
- **Pichora-Fuller, Schneider & Daneman (1995)** — How young and old listeners use context
- **Pichora-Fuller et al. (2016, Eriksholm)** — FUEL framework
- Three decades of work on word recognition in noise, dual-task paradigms, and pupillometry as effort indices

### 3. WHO Rehabilitation Alliance — Hearing in Later Life

Active International Society of Audiology (ISA) representative on the **WHO World Rehabilitation Alliance** working group on primary care. Leads the **Hearing in Later Life** working group. This positions her academic work directly inside the policy infrastructure that determines whether hearing care gets bundled into primary care globally. See [[who-hearing-program]].

### 4. Healthy-Aging Framing of Hearing Loss

Long-running advocacy that hearing should be measured as a contributor to healthspan, not as an isolated sensory deficit. This framing is the upstream rationale for the entire dementia–hearing loss research program (ACHIEVE, Framingham, Apple Hearing Study walking-speed result) — see [[../concepts/hearing-loss-dementia-link]].

## Why Her Award Matters for Hearing-AI / Data Science

The hearing-AI optimization stack today measures at three layers:

| Layer | Metric | What it captures |
|---|---|---|
| Signal | PESQ / STOI / HASPI / HASQI | Acoustic fidelity / intelligibility proxy |
| Lexical | WER (often via ASR) | Words correctly recognized |
| Neural attention | AAD (Mesgarani et al., *Nat Neurosci*, May 2026) | The voice the brain is locked onto |

Pichora-Fuller's framework adds a fourth, **interactional / communication-accessibility** layer that no standardized metric covers today. The 2026 keynote argument is that this is the layer the field has not built for.

Her award is the most senior endorsement to date that the field's evaluation construct has outrun its measurement stack. Concrete consequences for ML-side R&D:

1. **Unit of evaluation shifts from signal to conversation** — multi-speaker, multi-turn, multi-environment.
2. **FUEL is already the operational specification** — what is missing is the wearable telemetry stack that estimates motivation × demand × resources continuously over a real day.
3. **The first OEM that ships a HASPI-equivalent for communication accessibility owns the next-decade outcome conversation** — clinical, regulatory, reimbursement.

See [[../concepts/communication-accessibility-metric]] for the proposed metric layer and [[../concepts/listening-effort-evaluation]] for the existing effort-measurement substrate.

## Related Pages
- [[../concepts/listening-effort-evaluation]] — FUEL is the operational specification beneath this concept page
- [[../concepts/communication-accessibility-metric]] — The metric layer her 2026 keynote argues the field still has not built
- [[../concepts/subjective-objective-hearing-gap]] — Adjacent framing: the audiogram does not capture the lived experience
- [[../concepts/multimodal-hearing-assessment]] — Companion measurement direction recovering normal-audiogram-but-impaired cases
- [[../concepts/hearing-loss-dementia-link]] — Upstream healthy-aging framing
- [[../concepts/cortical-reorganization-hearing-aids]] — Becker et al. MEG plasticity result as one neural substrate of FUEL's "resources" axis
- [[vcca-computational-audiology]] — Pichora-Fuller appears in adjacent VCCA programming on cognitive audiology; WCA 2026 Seoul context
- [[who-hearing-program]] — Her WHO Rehabilitation Alliance role anchors the policy translation

## Sources
- [WCA 2026 Seoul — Pichora-Fuller Aram Glorig Award Lecture (26 May 2026)](../../sources/wca-2026-pichora-fuller-aram-glorig-may-26-2026.md) — Award + keynote "Hearing and Healthy Aging: The Imperative for Communication Accessibility"
- [World Congress of Audiology 2026 — Seoul](../../sources/world-congress-audiology-seoul-may-2026.md) — Congress context, plenary scheduling, CAN AI track
- Pichora-Fuller et al. (2016) "Hearing impairment and cognitive energy: The Framework for Understanding Effortful Listening (FUEL)." *Ear and Hearing* 37 Suppl 1: 5S-27S. DOI 10.1097/AUD.0000000000000312
