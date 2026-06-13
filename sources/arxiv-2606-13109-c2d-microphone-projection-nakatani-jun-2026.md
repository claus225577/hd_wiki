---
title: "Generating Training Targets for Real-World Speech Enhancement via Close-to-Distant Microphone Projection (C2D)"
type: source
source_type: arxiv-paper
arxiv_id: 2606.13109
authors: [Tomohiro Nakatani, Rintaro Ikeshita, Naoyuki Kamo, Marc Delcroix, Shoko Araki]
affiliations: [NTT Communication Science Laboratories]
date_published: 2026-06-11
ingested: 2026-06-13
url: https://arxiv.org/abs/2606.13109
venue: Proc. IEEE ICASSP 2026
tags: [speech-enhancement, training-data, close-to-distant, microphone-projection, pmwf, parametric-multichannel-wiener-filter, simulation-to-reality-gap, chime6, guided-source-separation, real-paired-data, hearing-aid-data-collection]
---

# C2D — Close-to-Distant Microphone Projection (Nakatani et al., Jun 2026)

## Bibliographic
- **Authors:** Tomohiro Nakatani, Rintaro Ikeshita, Naoyuki Kamo, Marc Delcroix, Shoko Araki
- **Affiliation:** NTT Communication Science Laboratories (Japan)
- **Venue:** Proc. IEEE ICASSP 2026
- **Posted:** 11 June 2026 (arXiv:2606.13109)
- **URL:** https://arxiv.org/abs/2606.13109

## Problem
Modern speech-enhancement (SE) DNNs require **paired noisy-clean training data**. In real-world acoustic environments, clean references are not available — the wearer's actual ear-side microphone records noisy signal, and there is no oracle of the underlying clean speech. The field has worked around this for a decade with **simulated** noisy-clean pairs: take clean speech corpora, convolve with impulse responses, add noise at controlled SNRs. The cost is a persistent **simulation-to-reality gap** — models trained on simulated pairs generalize imperfectly to the acoustic conditions a deployed hearing aid actually encounters.

## Contribution
C2D ("Close-to-Distant" microphone projection) closes the gap by enabling **real paired data**. Record the same scene with two microphones:
- A **close-talking microphone** near the speaker's mouth (high SNR, near-clean speech).
- A **distant microphone** array further from the speaker (noisy, reverberant — the realistic deployment condition).

The close-mic signal is **not** a clean reference — it still contains environmental noise leakage, residual reverberation, and SNR floor effects. C2D estimates an **optimal projection matrix** that transforms the close-mic input into the corresponding clean reference for the distant array while **simultaneously performing denoising**. The implementation is a variant of the **Parametric Multichannel Wiener Filter (PMWF)**.

The result is a training pipeline that turns dual-mic field recordings into noisy-clean pairs without simulation.

## Key Results
- **Evaluated on CHiME6** (dinner-party ASR task) under **oracle diarization**.
- **Outperforms Guided Source Separation (GSS)** — the prior SOTA in that setting — on enhancement quality and downstream ASR.
- C2D produces SE training targets from real recordings that are demonstrably better than GSS-cleaned outputs.

## Why It Matters for Hearing Aids
- **Training-data substrate, not architecture.** The standard hearing-aid OEM training stack already uses 12M-22M *simulated* scenes (Oticon More 12M, current flagships 13.5M-22M per `concepts/speech-enhancement-neural-networks.md`). Synthetic mixing + measured impulse responses cover wide acoustic diversity but inherit the simulation-to-reality gap.
- **A new data-collection pathway.** For hearing-aid R&D, the C2D pattern maps cleanly onto a **body-worn close mic + ear-worn aid mics** dual recording during real-world data collection. Wearers in field studies could carry a close-talking reference mic, producing labeled training pairs without simulation.
- **The lever moves.** Where the field has been spending its margin on "bigger model + more synthetic data," C2D offers an alternative: **better training-signal substrate** with the same downstream model. The improvement is upstream of architecture choice — it composes with any SE network the OEM trains.
- **Companion to L3-SE-style faithfulness concerns.** Generative SE that hallucinates under low-SNR distribution shift (see `concepts/linguistic-hallucination-speech-enhancement.md`) is partly a consequence of training-distribution mismatch. Real-paired training data narrows the mismatch the model has to extrapolate across.
- **Composability.** Orthogonal to the latency-floor work (SB-RF, HALO, DriftSE, DiffVQE), the architectural-search work (NDF+, Spatial-Magnifier), and the in-the-loop training work (DFC-IL). A team could swap simulated training pairs for C2D-derived real pairs without changing the rest of the stack.

## Open Questions
- Compute cost of the PMWF projection at corpus scale, and whether C2D survives the move from CHiME6 dinner-party to free-roaming hearing-aid wearer data.
- Whether the close-talking mic can be sufficiently miniaturized / unobtrusive for a typical HA field study (clinical trials, OEM data-collection cohorts).
- Does C2D require oracle diarization, or can it be combined with neural diarization (the foundation-model fusion lineage tracked in `concepts/foundation-model-fusion-speech.md`)?
- Privacy and consent — close-mic field recordings are high-fidelity speech samples; the data-governance overhead may dominate the scientific cost.
- Does the projection matrix carry **wearer-specific** information (head shadow, mic-placement variation) that could be exploited for personalization rather than only training-target generation?

## Related Wiki Pages
- [[../wiki/concepts/close-to-distant-microphone-projection.md]] — primary concept page
- [[../wiki/concepts/synthetic-data-for-hearing-ai.md]] — counter-position to simulation
- [[../wiki/concepts/speech-enhancement-neural-networks.md]] — downstream model substrate
- [[../wiki/concepts/training-deployment-distribution-gap.md]] — broader framing of the train-vs-deploy mismatch
- [[../wiki/concepts/linguistic-hallucination-speech-enhancement.md]] — distribution-shift contributor to generative-SE hallucination
- [[../wiki/concepts/closed-loop-data-flywheel.md]] — the field-data side of the equation
