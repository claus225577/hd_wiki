---
title: "WCA 2026 Seoul — Pichora-Fuller Aram Glorig Award Lecture, 26 May 2026"
type: conference-keynote
date: 2026-05-26
url: https://wca2026seoul.com/?module=Html&action=SiteComp&sSubNo=14
secondary_url: https://isa-audiology.org/about-isa/aram-glorig-award
fuel_paper_url: https://journals.lww.com/ear-hearing/fulltext/2016/07001/hearing_impairment_and_cognitive_energy__the.2.aspx
tags: [wca2026, isa, aram-glorig-award, pichora-fuller, fuel-framework, listening-effort, communication-accessibility, cognitive-audiology, healthy-aging, plenary, outcome-measurement]
---

# WCA 2026 Seoul — Pichora-Fuller Aram Glorig Award Lecture (26 May 2026)

## Key Facts

- **Event:** Aram Glorig Award presentation + lecture at 37th World Congress of Audiology
- **Date:** Tuesday, 26 May 2026 (Day 3 of WCA 2026 Seoul, 24–27 May)
- **Awardee:** **M. Kathleen (Kathy) Pichora-Fuller**, Professor Emerita, Department of Psychology, University of Toronto; Adjunct Professor, Department of Gerontology, Simon Fraser University, Vancouver
- **Lecture title:** "Hearing and Healthy Aging: The Imperative for Communication Accessibility"
- **Award context:** Aram Glorig Award is presented by the International Society of Audiology (ISA) — the field's highest honor — for "distinguished and lasting contribution to the field of Audiology."

## Why This Award Matters

Pichora-Fuller's name is best known to the ML / hearing-AI side of the field through three structural contributions:

1. **Framework for Understanding Effortful Listening (FUEL)** — co-authored with Sophia Kramer and colleagues, published in *Ear and Hearing* (2016, Eriksholm Workshop). Operationalized the listening experience as the interaction of:
   - **Demand** (acoustic + linguistic + cognitive task load)
   - **Resources** (sensory + cognitive + executive)
   - **Motivation** (effort the listener is willing to expend)
2. **Cognitive load × hearing loss** — three decades of work showing listening effort is the missing variable connecting audiogram-side measurement to lived-experience outcomes (Pichora-Fuller & Singh 2006; Pichora-Fuller et al. 2016).
3. **WHO Rehabilitation Alliance representation** — ISA representative on the WHO World Rehabilitation Alliance working group on primary care, leading the Hearing in Later Life working group.

## Significance for Hearing-AI / Data-Science

### The Loss-Function Argument

The current hearing-AI optimization stack measures at three layers:

| Layer | Metric | What it captures |
|---|---|---|
| Signal | PESQ / STOI / HASPI / HASQI | Acoustic fidelity / intelligibility proxy |
| Lexical | WER (often via ASR) | Words correctly recognized |
| Neural attention | AAD (Mesgarani, Choudhari, Nat Neurosci May 2026) | The voice the brain is locked onto |

Pichora-Fuller's framework adds a fourth, interactional layer:

| Layer | Metric | Status |
|---|---|---|
| **Communication accessibility** | None standardized | The keynote argument is that this is the layer we have not built for |

The FUEL operationalization (motivation × demand × resources) is structurally available — what is missing is the **telemetry to instrument it on a real wearer over a real day**.

### Three Implications Named in the Keynote Framing

1. **Unit of evaluation shifts from signal to conversation.** The interactional layer is multi-speaker, multi-turn, multi-environment.
2. **FUEL is already the operational specification** — the data-science task is to build the wearable telemetry stack that estimates motivation × demand × resources continuously.
3. **The first OEM that ships a HASPI-equivalent for communication accessibility owns the next-decade outcome conversation** — clinical, regulatory, reimbursement.

## Connection to Other 2026 Threads

- Mesgarani et al. Columbia ECoG closed-loop AAD paper (Nature Neuroscience, 11 May 2026) — attention-side optimization
- Behringer et al. listening-effort codec paper (arXiv 2605.03776, 5 May 2026) — codec-level effort metric
- L3-SE linguistic-hallucination paper (Wang et al., arXiv 2605.08608, 9 May 2026) — word-level faithfulness
- de Oliveira/Peer/Gerkmann ASR-too-good paper (arXiv 2605.12107, 12 May 2026) — yardstick crack
- Gijbels et al. multimodal hearing assessment (Frontiers in Audiology and Otology, Mar 2026) — ecological-validity recovery of >10% normal-audiogram participants

Together these are pointing at a five-axis evaluation reframe: signal × lexical × neural × effort × **interactional** (communication accessibility). Pichora-Fuller's lecture is the fifth axis being named at the field's flagship congress.

## Cross-References

- [[../wiki/entities/kathy-pichora-fuller]] — NEW entity page for the awardee + body of work
- [[../wiki/concepts/communication-accessibility-metric]] — NEW concept page for the proposed metric layer
- [[../wiki/concepts/listening-effort-evaluation]] — Existing concept page — update with FUEL operationalization detail
- [[../wiki/entities/vcca-computational-audiology]] — Existing WCA 2026 entry — update with Aram Glorig context
- [[../wiki/concepts/subjective-objective-hearing-gap]] — Cross-link
- [[../wiki/concepts/multimodal-hearing-assessment]] — Cross-link (Gijbels)
- [[../wiki/concepts/auditory-attention-decoding]] — Cross-link (Mesgarani)
