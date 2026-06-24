---
title: Waldo Nogueira
type: entity
created: 2026-06-24
updated: 2026-06-24
sources: [vcca-2026-main-programme-june-2026.md, vcca2026-conference.md]
related: [../concepts/cochlear-implant-ai.md, ../concepts/hearing-aid-chip-architectures.md, ../concepts/software-defined-medical-implants.md, vcca-computational-audiology.md]
tags: [person, researcher, hannover-medical-school, cochlear-implant, electric-acoustic-stimulation, eas, extracochlear, novel-device-class, vcca-2026-invited, germany]
---

# Waldo Nogueira

Prof. Dr.-Ing. at the **Hannover Medical School** (Medizinische Hochschule Hannover, MHH), one of Europe's primary cochlear-implant research centres. Long-running research programme on **CI sound coding**, with extensions into electric-acoustic stimulation (EAS), psychoacoustic modelling, and signal-processing strategies for residual-hearing preservation.

## 2026 Recognition

**VCCA 2026 Day 2 Invited Speaker (Jun 26, 2026):** *"Extracochlear Electric–Acoustic Interaction as the Basis for a Novel Hearing Device."*

The talk title describes a structurally new device class: an electric-acoustic interaction device that places its electrical stimulation component **extracochlear** — outside the cochlea, not requiring surgical insertion of an electrode array into the scala tympani. The framing positions the proposed device between traditional hearing aids (acoustic amplification only) and conventional cochlear implants (intracochlear electrical stimulation), with potentially less surgical risk and less residual-hearing loss than current CI / EAS hybrids.

If validated, an extracochlear EAS device would be a **net-new product category** — neither an HA, nor a bone-conduction device, nor a CI, nor a hybrid acoustic-electric CI. The candidate-population implications are substantial: listeners who are too impaired for hearing aids but for whom CI surgery's residual-hearing loss is a meaningful tradeoff could become candidates for a less-invasive electrical-stimulation option.

## Structural Contributions to the Field

### 1. CI sound-coding strategy research

Long-running programme on CI sound-coding strategies, signal-processing improvements, and psychoacoustic modelling. Hannover Medical School is one of the most active European CI research centres, with deep ties to MED-EL (headquartered in Innsbruck) and to the broader European CI clinical and research community.

### 2. Electric-acoustic stimulation (EAS) signal processing

Work on the signal-processing challenges of combined acoustic + electric stimulation for listeners with residual low-frequency hearing — including the cross-modal alignment problem (matching the temporal and spectral structure of the acoustic and electrical channels so that the listener perceives them as a single auditory stream).

### 3. Extracochlear-stimulation device concept

The VCCA 2026 invited talk is the most public framing to date of the extracochlear-EAS device concept. The technical premise: deliver electrical stimulation to the cochlear nerve or to round-window-membrane-adjacent structures without inserting an electrode array into the scala tympani, while preserving native acoustic input through the unmodified outer / middle ear.

## Why This Matters for Hearing AI / Data Science

### Net-new device categories generate net-new sound-coding / personalisation problems

Every new hearing-device category (acoustic HA, BAHA, hybrid CI, fully-implantable CI, extracochlear EAS) opens a corresponding sound-coding / personalisation / ML-optimisation problem. The mature ML stacks for HA and CI do not transfer cleanly to a device with novel electrode-tissue interface, novel residual-hearing preservation profile, and novel acoustic-electric coordination requirements.

### Candidate-population segmentation shifts

The hearing-device market has historically been segmented along a one-dimensional severity axis: mild-to-moderate (HA), severe-to-profound (CI), with bone-conduction and hybrid CIs as side branches. A successful extracochlear-EAS class would introduce a new axis (invasiveness × residual-hearing-preservation × electrical-stimulation-coverage) along which fitting algorithms would need to operate.

### Adjacent to the fully-implantable CI thread

Envoy Medical's Acclaim fully-implantable CI (FDA approval expected late 2027/2028; see [[envoy-medical]]) is the other major new CI-side device class on the horizon. Where Acclaim re-engineers the CI form factor (no external processor, totally implanted), Nogueira's extracochlear-EAS concept re-engineers the CI mechanism (no intracochlear electrode). The two are independent axes on which the conventional CI is being challenged simultaneously.

## Related Pages

- [[../concepts/cochlear-implant-ai]] — CI-side ML programme that any new CI-class device generates new work for.
- [[../concepts/hearing-aid-chip-architectures]] — Net-new device classes have net-new chip / power / latency constraints.
- [[../concepts/software-defined-medical-implants]] — Software-defined implant framework applies cleanly to new electrode-tissue interface classes.
- [[vcca-computational-audiology]] — VCCA 2026 invited speaker context.

## Sources

- [VCCA 2026 Main Programme](../../sources/vcca-2026-main-programme-june-2026.md) — Day 2 invited talk.
- [VCCA 2026 Conference Overview](../../sources/vcca2026-conference.md) — Programme structure.
