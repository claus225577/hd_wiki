---
title: Envoy Medical
type: entity
created: 2026-04-23
updated: 2026-04-23
sources: [completely-implantable-cochlear-implants-april-2026.md]
related: [../concepts/cochlear-implant-ai.md, ../concepts/on-device-ml-hearing-aids.md, advanced-bionics.md, ../concepts/hearing-aid-chip-architectures.md]
tags: [company, cochlear-implant, fully-implantable, acclaim, piezoelectric, fda]
---

# Envoy Medical

U.S.-based company developing the Acclaim, a fully implantable cochlear implant with no external components.

## Acclaim — Fully Implantable Cochlear Implant

The Acclaim is designed to be the first completely invisible cochlear implant:

### Key Technical Features
- **Piezoelectric sensor at the incus** — captures sound vibrations directly from the ossicular chain, bypassing the need for any microphone (acoustic or subcutaneous)
- **No magnet** — MRI-compatible; a significant clinical advantage over conventional CIs that require magnet removal for certain MRI scans
- **Chest-implanted battery** — lasts **10-15 years**; avoids the behind-ear battery placement used by Cochlear Ltd. and MED-EL designs
- **No external components** — completely invisible; nothing worn on the ear or head

### Regulatory Status
- **Pivotal trials enrolled** (as of April 2026)
- **Anticipated FDA approval:** Late 2027 / early 2028
- Would be the first fully implantable CI to reach the U.S. market if approved on schedule

## Competitive Position

Three companies are developing fully implantable CIs:

| Company | Approach | Sound Capture | Battery Location | Status |
|---------|----------|---------------|-----------------|--------|
| **Envoy Medical** | Acclaim | Piezoelectric at incus | Chest (10-15 yr) | Pivotal trials enrolled |
| **Cochlear Ltd.** | Unnamed | Subcutaneous mic | Behind ear | 21 years R&D |
| **MED-EL** | TICI | Subcutaneous mic | Not disclosed | In development |

Envoy's piezoelectric approach is architecturally distinct: it captures mechanical vibration from bone rather than acoustic sound through tissue, which avoids the tissue attenuation and body noise problems that subcutaneous microphones face.

## AI and Edge Computing Implications

The Acclaim represents the ultimate edge AI challenge for hearing technology:

- **Power budget:** 10-15 year battery life with continuous operation implies sub-microwatt inference budgets — orders of magnitude below current hearing aid chips (1-5 mW)
- **No external update path:** Software/firmware updates may require wireless over-skin programming or surgical intervention
- **Thermal constraints:** All compute must occur within biocompatible implant housing; tissue damage occurs above ~2C temperature rise
- **Novel input signal:** Piezoelectric ossicular vibration is a fundamentally different signal than acoustic microphone capture — ML preprocessing pipelines designed for acoustic input may not transfer directly
- **Size constraints:** All processing hardware must fit within implantable housing with strict biocompatibility requirements
- **Longevity requirements:** Hardware must function reliably for 10-15+ years — far beyond consumer electronics lifecycles

If ML-based speech processing is to be included in future fully implantable CIs, it will need to operate at power levels that current hearing aid NPUs cannot achieve. This makes technologies like [[compute-in-memory]] and [[state-space-models]] particularly relevant — their potential for ultra-low-power inference could enable AI in fully implantable devices.

## Related Pages
- [[cochlear-implant-ai]] — AI applications across the CI pipeline
- [[on-device-ml-hearing-aids]] — Edge computing constraints; fully implantable CIs push these to extremes
- [[advanced-bionics]] — Competing CI manufacturer (Sonova subsidiary)
- [[hearing-aid-chip-architectures]] — Hardware architectures; fully implantable CIs need even more efficient designs

## Sources
- [On the Cusp of Completely Implantable Cochlear Implants](../sources/completely-implantable-cochlear-implants-april-2026.md) — Three companies developing fully implantable CIs; Envoy anticipates FDA approval late 2027/early 2028
