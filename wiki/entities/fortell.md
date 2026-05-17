---
title: Fortell
type: entity
created: 2026-05-13
updated: 2026-05-13
sources: [fortell-spatial-ai-ija-may-2026.md]
related: [../concepts/hearing-aid-chip-architectures.md, ../concepts/dnn-in-hearing-aids.md, ../concepts/on-device-ml-hearing-aids.md, ../concepts/speech-enhancement-neural-networks.md, phonak.md, sonova-ag.md]
tags: [startup, hearing-aids, ai-chip, spatial-ai, premium, cocktail-party, custom-silicon]
---

# Fortell

## What

US-based hearing aid startup launching late 2025 / early 2026 with a vertically integrated stack: custom AI chip + single-purpose "Spatial AI" neural network + curated multitalker dataset + a single clinical channel. Positions itself against premium hearing aids from Sonova/Phonak, Demant/Oticon, GN/ReSound, WSA/Signia, and Starkey, targeting cocktail-party / multitalker noise as the primary differentiator.

## Architecture Highlights

- **Custom AI chip:** Reported at ~235× the compute of conventional hearing aid SoCs; up to 100 billion operations per second; end-to-end latency under 10 ms
- **Spatial AI algorithm:** Trained on millions of real-world multitalker recordings; separates the target speech stream from ambient noise, then re-amplifies that stream rather than the whole scene
- **Co-design philosophy:** Silicon and algorithm explicitly designed for each other (similar in philosophy to Phonak's DEEPSONIC dual-chip in Sphere Infinio, but in a startup full-stack form)

## Distribution & Pricing

- **Single clinical channel:** Park Avenue, Manhattan (boutique fitting model)
- **Price:** ~$6,800 / pair
- **Access:** Waitlist; referral-driven; explicitly positioned as a NYC-elite status product

## Clinical Evidence

### IJA May 2026 — Preference Study
- n = 20 adults, mild-to-moderately-severe bilateral sensorineural hearing loss
- 100 randomized blinded A/B trials per participant against five state-of-the-art incumbents
- Result: 99/100 trials preferred Fortell (1 tie); average SNR uplift 12.2 dB vs 3.0–5.9 dB for controls
- Consultants: William Shapiro and Mario Svirsky (NYU Langone)
- Source: [Spatial AI Preferred — IJA May 2026](../../sources/fortell-spatial-ai-ija-may-2026.md)

### Companion Nov 2025 Intelligibility Study
- 17 dB SNR improvement vs 1.9 dB control
- 80% word comprehension in challenging noise (vs 31% control); 50% in extremely challenging noise (vs 7%)
- 95% participant preference vs five top competitors

## Strategic Position

- **Validates the co-design thesis.** First clear empirical case where a startup full-stack hearing aid beats incumbent premium HAs on an industry-standard preference test by an order of magnitude in SNR. Aligns with Phonak's strategic bet on dedicated AI silicon in Sphere Infinio.
- **Counter-pressure on shared-silicon strategies.** Aizip's pitch that software-only optimization on commodity DSPs can match custom NPUs is harder to defend against Fortell's data.
- **Premium positioning ≠ mass-market threat (yet).** A boutique Park Avenue clinic at $6,800 / pair does not displace volume products. The translational risk to incumbents is whether the architecture compresses into mainstream RIC / BTE form factors and price bands.
- **Industry-sponsored evidence caveat.** Clinical work is manufacturer-funded with consulted experts; independent replication has not yet appeared.

## Open Questions

1. **Scale path** — Does Fortell expand beyond Manhattan, license the chip + algorithm to incumbents, or remain a boutique brand?
2. **Independent replication** — Will academic groups outside the consultant network reproduce the 99/100 preference and 12.2 dB SNR claims with their own protocols?
3. **Form-factor compression** — Can the 235× compute chip be re-spun for ITC/CIC / power-constrained variants without losing the SNR advantage?
4. **OEM response** — Will Sonova / Demant / GN / Starkey / WSA accelerate dedicated-AI-chip programs, or argue that shared NPU + software optimization closes the gap?

## Related Pages
- [[../concepts/hearing-aid-chip-architectures]] — Co-design as the differentiator
- [[../concepts/dnn-in-hearing-aids]] — Adjacent algorithmic landscape
- [[../concepts/speech-enhancement-neural-networks]] — Cocktail-party / source separation paradigm
- [[phonak]] — Sphere Infinio dedicated AI chip as the incumbent parallel
- [[sonova-ag]] — Parent company of Phonak (the most directly comparable incumbent)

## Sources
- [Spatial AI Preferred — IJA May 2026](../../sources/fortell-spatial-ai-ija-may-2026.md) — Preference study, chip specs, dataset framing
