---
title: "Spatial AI Consistently Preferred to State-of-the-Art Hearing Aids in Multitalker Noise"
authors: [Fortell research team, with NYU Langone consultants William Shapiro and Mario Svirsky]
date_published: 2026-05
date_ingested: 2026-05-13
url: https://www.tandfonline.com/doi/full/10.1080/14992027.2026.2663345
doi: 10.1080/14992027.2026.2663345
type: academic-paper
venue: International Journal of Audiology
tags: [spatial-ai, fortell, custom-silicon, speech-enhancement, multitalker, cocktail-party, preference-study, dnn-in-hearing-aids, hardware-software-codesign]
---

# Spatial AI Consistently Preferred to State-of-the-Art Hearing Aids in Multitalker Noise

## Summary

Peer-reviewed preference study comparing Fortell's "Spatial AI" hearing aid against five state-of-the-art premium hearing aids from incumbent manufacturers, in challenging multitalker noise scenarios. The investigational device was preferred in 99 of 100 randomized blinded trials, with average SNR uplift roughly double the best incumbent. Published in *International Journal of Audiology* in May 2026.

## Study Design

- **Participants:** n = 20 adults with mild-to-moderately-severe bilateral sensorineural hearing loss
- **Paradigm:** Recordings of each hearing aid in noisy, multitalker environments were presented to participants via PC/headphones in a home environment
- **Trials:** 100 randomized A/B comparisons per participant; for each trial the participant rated which device made the target talker easier to understand
- **Consultants/supervisors:** William Shapiro and Mario Svirsky (NYU Langone) — Svirsky is the Noel L. Cohen Professor of Hearing Science at NYU Grossman School of Medicine and director of Research for the Cochlear Implant Program

## Key Results

- **Preference:** Investigational device preferred in 99 / 100 trials (1 tie)
- **SNR uplift (vs unaided):**
  - Investigational device: 12.2 dB average
  - Five control hearing aids: 3.0–5.9 dB
- **Companion clinical study (also referenced on Fortell's research page, Nov 2025):**
  - 17 dB SNR improvement vs 1.9 dB control
  - 80% word comprehension in challenging noise (vs 31% control)
  - 50% word comprehension in extremely challenging noise (vs 7% control)
  - 95% of participants reported easier understanding with Fortell vs all top five competitors

## The Investigational Device (Fortell)

- **Algorithm:** "Spatial AI" — a single-purpose neural network trained on millions of real-world multitalker recordings; separates the target speech stream from background then re-amplifies it
- **Custom AI chip:** Reported at ~235× the compute of conventional hearing aid SoCs; up to 100 billion operations per second; end-to-end latency under 10 ms
- **Distribution:** Single Park Avenue clinic in Manhattan, by referral, $6,800 / pair, with a multi-month waitlist

## Significance for Hearing Aid AI

- **Co-design over algorithm-only innovation.** Every major OEM ships neural noise reduction in 2026. The headline gap here is not "DNN vs DSP" — it is on-chip compute budget. Fortell built the silicon for the algorithm rather than fitting an algorithm to existing silicon.
- **Validates Phonak Sphere's strategic bet.** Phonak's dedicated AI processor in Sphere Infinio (2024) was the first incumbent move in the co-design direction. The Fortell study suggests further gains are unlocked by a single-purpose chip + single-purpose model + curated dataset stack.
- **Counter-evidence for shared-silicon ecosystems.** Aizip's thesis (Apr 2026 source) is that software optimization on commodity DSPs can deliver competitive AI. The Fortell data argues that the SNR ceiling moves substantially when the silicon is custom.
- **Premium price point limits population impact.** $6,800 at a single Manhattan clinic does not move the population-level access needle. The translational question is whether the architecture compresses into mainstream RIC/BTE form factors and price bands.

## Limitations

- N = 20 — small for population-level claims
- Recordings played back via PC/headphones rather than in-ear A/B (not a clinical wear-and-test crossover)
- Industry-sponsored study with manufacturer-consulted experts; no public registration of the protocol noted
- Control hearing aids identified only by category ("top 5 premium") in the public summary; specific incumbent device labels not yet pulled

## Coverage

- *International Journal of Audiology* — Full article (paywalled / partial open): https://www.tandfonline.com/doi/full/10.1080/14992027.2026.2663345
- Fortell clinical research page: https://www.fortell.com/clinical-research
- NeurotechNews (Dec 2025): https://neurotechnus.com/2025/12/04/ai-hearing-aid-spatial-solution/
- Katherine Bouton, *Smart Hearing* (Jan 2026): https://katherinebouton.me/2026/01/15/revolutionary-fortell-hearing-aid-tackles-the-cocktail-party-problem-is-it-for-you/
- ClearHealthCosts (Jan 2026): https://clearhealthcosts.com/blog/2026/01/new-ai-powered-fortell-hearing-aid-tackles-the-age-old-problem-of-noise/
- Mischa Dohler blog: https://mischadohler.com/revolutionizing-hearing-ai-powered-hearing-aids-for-very-hard-of-hearing-by-fortell/

## Related Wiki Pages
- [[hearing-aid-chip-architectures]] — Custom AI silicon as the unlock for higher SNR ceilings
- [[dnn-in-hearing-aids]] — Speech-enhancement DNN landscape that Spatial AI extends
- [[speech-enhancement-neural-networks]] — Adjacent paradigm (cocktail-party / source separation)
- [[on-device-ml-hearing-aids]] — Power/latency budget that the Fortell chip is designed against
- [[../entities/fortell.md]] — Entity page for Fortell as new market entrant
