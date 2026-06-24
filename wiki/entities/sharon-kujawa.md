---
title: Sharon Kujawa
type: entity
created: 2026-06-24
updated: 2026-06-24
sources: [vcca-2026-main-programme-june-2026.md, vcca2026-conference.md, knipper-hidden-hearing-loss-dementia-may-2026.md]
related: [../concepts/hidden-hearing-loss.md, ../concepts/otoprotection-pharmacology.md, ../concepts/kv74-kcnq4-outer-hair-cell.md, vcca-computational-audiology.md, ../syntheses/hidden-hearing-loss-fullstack-june-2026.md]
tags: [person, researcher, audiologist, harvard-medical-school, mass-eye-and-ear, synaptopathy, cochlear-synaptopathy, hidden-hearing-loss, kujawa-liberman, vcca-2026-invited, animal-models]
---

# Sharon Kujawa

Professor at **Harvard Medical School**; **Director of Audiology Research at Massachusetts Eye and Ear**. The senior figure in the field of **cochlear synaptopathy** and the founder, with M. Charles Liberman, of the modern animal-model framework for **hidden hearing loss**.

## The Founding Result — Kujawa & Liberman, 2009

The Kujawa & Liberman *Journal of Neuroscience* paper (2009) is the single foundational citation of the modern HHL field. Working in mouse models, they showed that moderate noise exposure can cause **permanent loss of inner-hair-cell ribbon synapses** (the synaptic contacts between inner hair cells and auditory-nerve fibres) **without killing hair cells and without permanently shifting absolute hearing thresholds**. The audiogram looked normal post-recovery; the auditory nerve's ability to encode suprathreshold information was permanently degraded.

The result reframed the field. For decades the working assumption had been: if absolute thresholds return to baseline after noise exposure, the cochlea has recovered. Kujawa & Liberman showed that this is wrong — there is a regime of cochlear damage that is permanent, behaviourally significant, and invisible to the standard audiogram. That regime is what became known as cochlear synaptopathy, and the audiometric phenotype it produces is what the clinical field calls hidden hearing loss.

See [[../concepts/hidden-hearing-loss]] for the broader phenotype and [[../concepts/kv74-kcnq4-outer-hair-cell]] for the adjacent OHC-side biology.

## 2026 Recognition

**VCCA 2026 Day 2 Invited Speaker (Jun 26, 2026):** *"Hidden Hearing Loss: From Animal Models to Human Translation."*

Having the founder of the synaptopathy programme as a keynote-tier invited speaker — paired with Harvey Dillon's Day 1 keynote on disambiguating listening difficulty with normal audiograms, with the dedicated Session 3.A on Hidden Hearing Loss & Subclinical Auditory Disorders, and with Matthias Inghels's poster on closed-loop ML compensation for hidden HL — is the strongest single endorsement to date that the audiology community treats HHL as a first-class clinical phenotype, not an animal-model curiosity.

The 17 years between Kujawa & Liberman 2009 and the VCCA 2026 invitation is the field's typical translation lag: founding mechanism → human studies → clinical validation → diagnostic protocol → conference-track formalisation.

## Structural Contributions to the Field

### 1. The synaptopathy mechanism

Foundational and follow-up work over 2009–2024 establishing:
- Moderate noise exposure → permanent ribbon-synapse loss → permanent suprathreshold deficit without threshold shift.
- The lost synapses are predominantly those connected to **low-spontaneous-rate auditory-nerve fibres** — exactly the fibres responsible for coding suprathreshold information in noise.
- Age-related synaptopathy proceeds even without explicit noise exposure and accounts for a substantial fraction of presbycusis-related speech-in-noise difficulty.

### 2. Human-translation programme

The harder problem. Animal histology cannot be done in living humans, so the human-translation work has had to construct *indirect* signatures of synaptopathy from electrophysiology (ABR wave I amplitude, MEMR), psychoacoustics, and speech-in-noise performance. The translation has been contested across the 2014–2024 literature, with the central open question being which of the proposed human signatures actually reflect synaptopathy and not other co-occurring mechanisms.

Kujawa's 2026 VCCA invited talk is explicitly framed *"From Animal Models to Human Translation"* — the most senior current statement of the field's translational position.

### 3. Mass Eye and Ear as a Hidden-HL Hub

Mass Eye and Ear (Harvard Medical School affiliate) houses the Kujawa lab alongside the Liberman lab (until Liberman's retirement) and the Harvard / Mass Eye and Ear team behind the OTOF gene-therapy work (Nature 2026 — see `harvard-mass-eye-ear-gene-therapy-otof-nature-2026.md`). The institutional concentration parallels Tübingen on the OHC-pharmacology side: same institution producing both basic-science mechanism work and clinical-translation programmes.

## Why This Matters for Hearing AI / Data Science

### The data substrate currently mislabels HHL listeners as normal-hearing

Most public HA / SE training datasets enroll listeners by audiogram. HHL listeners present with normal audiograms and so are either excluded (if "no hearing loss") or labelled as normal-hearing controls (in studies that recruit a normal-hearing comparison arm). This contaminates both the training and the evaluation data: the listener population the model is built for is biased *away* from a phenotype that is substantial in the real wearer population.

### The diagnostic substrate the ML side needs depends on Kujawa's translational work

The non-invasive electrophysiological and behavioural signatures of synaptopathy that Kujawa's translational programme is validating are the same substrate the ML-fitting side needs to *infer* HHL phenotype from in-clinic measurements. Without robust human-translation work, the field has no way to label the wearer pool by mechanism — and therefore no way to learn mechanism-specific compensation.

### The closed-loop compensation problem is now on the ML programme

The Inghels poster at VCCA 2026 Session 4.A — "Computational Closed-Loop Methods to Compensate for Standard and Hidden Hearing Losses" — places the ML-side compensation of HHL on the conference programme alongside Kujawa's diagnostic-side invited talk. This is the first VCCA where the diagnostic side and the ML-compensation side of HHL appear together as first-class programme elements.

## Related Pages

- [[../concepts/hidden-hearing-loss]] — The clinical phenotype Kujawa's mechanism work underlies.
- [[../concepts/otoprotection-pharmacology]] — Adjacent intervention layer; Acousia's Bimokalner targets OHC biology, Kujawa's work targets IHC-side ribbon synapses.
- [[../concepts/kv74-kcnq4-outer-hair-cell]] — The OHC-side biology pair to Kujawa's IHC-side synaptopathy work.
- [[vcca-computational-audiology]] — VCCA 2026 invited speaker context.
- [[../syntheses/hidden-hearing-loss-fullstack-june-2026]] — Kujawa's mechanism as the basic-science foundation of the full HHL stack.

## Sources

- [VCCA 2026 Main Programme](../../sources/vcca-2026-main-programme-june-2026.md) — Day 2 invited talk.
- [VCCA 2026 Conference Overview](../../sources/vcca2026-conference.md) — Programme structure.
- [Knipper Public Statement on Hidden HL (May 2026)](../../sources/knipper-hidden-hearing-loss-dementia-may-2026.md) — Parallel European-side public framing of the same phenotype.
- Kujawa, S.G. & Liberman, M.C. (2009) "Adding insult to injury: cochlear nerve degeneration after 'temporary' noise-induced hearing loss." *Journal of Neuroscience* 29(45): 14077–14085 — foundational synaptopathy paper.
