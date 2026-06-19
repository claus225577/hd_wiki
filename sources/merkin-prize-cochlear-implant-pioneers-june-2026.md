---
title: 2026 Merkin Prize in Biomedical Technology — Awarded to Five Cochlear Implant Pioneers
type: source
source_type: prize-announcement
date: 2026-06-17
authors: [Broad Institute of MIT and Harvard, Merkin Prize Foundation]
url: https://merkinprize.org/
mirror_urls:
  - https://hearingreview.com/hearing-products/implants-bone-conduction/cochlear-implants/five-cochlear-implant-pioneers-awarded-2026-merkin-prize-in-biomedical-technology
  - https://www.broadinstitute.org/news/2026-merkin-prize-biomedical-technology-awarded-pioneers-modern-cochlear-implant
  - https://www.prnewswire.com/news-releases/2026-merkin-prize-in-biomedical-technology-awarded-to-pioneers-of-the-modern-cochlear-implant-302800432.html
  - https://today.duke.edu/2026/06/blake-wilson-and-cochlear-implant-team-win-2026-merkin-prize
ingested: 2026-06-18
tags: [cochlear-implant, merkin-prize, hochmair, graeme-clark, michael-merzenich, blake-wilson, cis-strategy, advanced-bionics, awards, recognition]
---

# 2026 Merkin Prize in Biomedical Technology — Awarded to Five Cochlear Implant Pioneers

## Announcement
On **June 17, 2026**, the Broad Institute of MIT and Harvard announced that the 2026 Richard N. Merkin Prize in Biomedical Technology was awarded jointly to five scientists and engineers for developing the modern cochlear implant. The $400,000 prize is shared among the recipients; the ceremony will take place in **September 2026**.

## Recipients
1. **Graeme Clark** (University of Melbourne) — Led the safety and engineering studies underpinning the modern CI; discovered key speech-coding insights enabling spoken-language understanding without lipreading; created the first FDA-approved multi-channel cochlear implant (1985).
2. **Ingeborg Hochmair** (Vienna Technical University → MED-EL co-founder) — With Erwin Hochmair, developed the first microelectronics multi-channel cochlear implant. First implanted in a deaf patient in Vienna on **December 16, 1977**.
3. **Erwin Hochmair** (Vienna Technical University → MED-EL co-founder) — Co-developer of the first multi-channel CI with subcutaneous receiver + flexible electrode array.
4. **Michael Merzenich** (UCSF) — Established the neurophysiological basis for cochlear implantation; designed electrode arrays; conducted early clinical trials; led commercialization through Advanced Bionics (now a Sonova subsidiary).
5. **Blake Wilson** (Research Triangle Institute / Duke University) — Developed the **Continuous Interleaved Sampling (CIS)** signal-processing strategy in 1989, which pushed mean speech understanding past 80% across CI users. CIS remains the default sound-coding strategy in every shipping CI to date.

## Key Quote
> "What makes this work especially remarkable is that it required not one breakthrough but several."
> — Harold Varmus, Merkin Prize selection committee chair

> "This whole story is a beautiful convergence of fields … basic science can act as the backbone on which to create life-changing technologies."
> — Emery Brown, MIT, selection committee member

## Significance for Hearing AI
The Merkin Prize is the largest individual award in biomedical-technology recognition and historically goes to translated foundational work. Its 2026 recipients sit at the **base of the CI stack** that current ML/AI work is layering on top of:

- **Hochmair multi-channel hardware** — the platform substrate the Cochlear Nucleus Nexa system (Jan 2026) and the fully-implantable CI candidates (Envoy / Spiral Therapeutics / Advanced Bionics April 2026) all extend.
- **Clark speech-coding insights** — predecessor of the band-axis processing now being relearned by FAConformer / BASENet / BiEAR (June 2026 arXiv cluster).
- **Merzenich neurophysiology + Advanced Bionics commercialization** — Sonova's CI division traces directly to Merzenich's commercialization work; the Spiral Therapeutics drug-delivery investment (April 2026) extends that lineage into precision therapeutics.
- **Wilson CIS** — the single algorithm against which every ML CI sound-coding paper benchmarks itself; the persistence of CIS as the dominant strategy is the strongest available evidence that foundational fixed-rule DSP can outlast 35+ years of ML experimentation.

## Extracted Themes
- **Foundational layer recognition.** The award lands precisely as ML adds another layer on top — CI silicon now runs ML (Cochlear Nucleus Nexa), but the underlying coding strategy is still Wilson's CIS.
- **Convergence narrative.** The committee explicitly framed the win as a convergence of neurophysiology + engineering + behavioral science — a template the AI/data-science community can adopt for hearing-AI work.
- **Implications for AI's role.** The data-science framing is "learnable shell on top of foundational primitive that was right the first time" rather than "replace what came before."

## Relevance Links
- Direct: [[../wiki/concepts/cochlear-implant-ai]] — the ML side of the same stack
- Direct: [[../wiki/entities/advanced-bionics]] — commercialization lineage
- Direct: [[../wiki/entities/sonova-ag]] — current owner of Advanced Bionics
- Adjacent: [[../wiki/entities/cochlear-ltd]] — current Nucleus Nexa manufacturer
- Adjacent: [[../wiki/concepts/software-defined-medical-implants]] — the layer ML is adding on top of CIS
- Adjacent: [[../wiki/syntheses/band-axis-shared-coordinate-system-june-2026]] — band-axis ML rediscovering the structure Clark's coding work already named
