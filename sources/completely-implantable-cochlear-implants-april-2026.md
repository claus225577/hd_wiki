---
title: "On the Cusp of Completely Implantable Cochlear Implants"
author: Hamilton-Basich M
publication: Hearing Review
date: 2026-04-21
url: https://hearingreview.com/hearing-products/implants-bone-conduction/cochlear-implants/on-the-cusp-of-completely-implantable-cochlear-implants
type: industry-review
tags: [cochlear-implant, fully-implantable, envoy-medical, cochlear-ltd, med-el, fda, edge-ai]
---

# On the Cusp of Completely Implantable Cochlear Implants

## Key Extraction

Three companies developing fully implantable cochlear implants (no external processor):

### Cochlear Ltd.
- **21 years of R&D** on fully implantable CI
- **Subcutaneous microphone** placed behind the ear under the skin
- **Subcutaneous battery** behind the ear
- Longest development timeline among the three

### MED-EL
- **TICI (Totally Implantable Cochlear Implant)** program
- **Subcutaneous microphone** under the skin
- **Fine structure coding strategies** — MED-EL's established strength in preserving temporal fine structure
- Details on battery/power not specified in article

### Envoy Medical
- **Acclaim** — fully implantable cochlear implant
- **Piezoelectric sensor at the incus** — captures sound vibrations directly from the ossicular chain (no microphone)
- **No magnet** required — MRI-compatible advantage over conventional CIs
- **Chest-implanted battery** lasting **10-15 years**
- **No external components** whatsoever — completely invisible
- Envoy anticipates **FDA approval late 2027 / early 2028**
- **Pivotal trials enrolled** as of article date

## Significance

- **Eliminates the external processor** — 24/7 invisible hearing restoration
- **Stigma elimination** — no visible device at all
- **Water/sport compatibility** — no external components to protect
- **Sleep hearing** — users can hear while sleeping (not possible with current CIs where processor is removed)
- **MRI compatibility** (Acclaim) — significant clinical advantage for ongoing healthcare

## Relevance to Hearing + AI

- **Massive edge AI implications:** All signal processing must occur under the skin with extreme power constraints
- **Power budget challenge:** Under-skin processing with battery lasting 10-15 years requires ultra-efficient inference
- **No external update path:** Firmware updates may require surgical intervention or wireless over-skin programming
- **Microphone placement:** Subcutaneous mics face tissue attenuation and body noise challenges — AI denoising becomes critical
- **Piezoelectric approach (Envoy):** Direct ossicular vibration sensing is a fundamentally different input signal than airborne acoustic microphone capture — requires different ML preprocessing
- **Size/thermal constraints:** All compute must fit within biocompatible implant housing with strict thermal limits (tissue damage above ~2C rise)
- **Battery life vs. compute tradeoff:** 10-15 year battery life with continuous operation demands sub-microwatt inference budgets
- Represents the ultimate edge AI challenge: real-time audio processing at power levels orders of magnitude below current hearing aid chips
