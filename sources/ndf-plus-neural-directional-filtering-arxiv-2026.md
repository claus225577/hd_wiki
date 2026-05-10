---
title: "NDF+: Joint Neural Directional Filtering and Diffuse Sound Extraction"
authors: [Weilong Huang, Le Nhat Tam Huynh, Oliver Thiergart, Emanuël A. P. Habets]
affiliation: Fraunhofer IIS / FAU Erlangen-Nürnberg
date: 2026-05-07
arxiv_id: 2605.06108
arxiv_url: https://arxiv.org/abs/2605.06108
arxiv_listing: https://arxiv.org/list/eess.AS/2026-05
type: research-paper
tags: [speech-enhancement, directional-filtering, beamforming, diffuse-extraction, multichannel, cocktail-party, hearing-aids, fraunhofer]
---

# NDF+: Joint Neural Directional Filtering and Diffuse Sound Extraction (Huang et al., May 2026)

## Key Extraction

- **Question:** Real acoustic scenes have *both* directional sources (talkers, sirens) and diffuse components (room reverberation, ventilation, crowd babble). Existing systems typically address one or the other. Can a single neural model jointly handle directional filtering and diffuse-component extraction?
- **Method:** A unified neural architecture that simultaneously performs directional filtering (extract the target talker from a known/estimated direction) and diffuse-sound extraction (model and isolate the spatially-spread components).
- **Authors / Affiliation:** Huang, Huynh, Thiergart, Habets — Fraunhofer IIS / International Audio Laboratories Erlangen (Habets group is one of the senior groups in the field for spatial audio + ML).

## Why This Matters for Hearing AI

- **Cocktail-party scene = directional + diffuse simultaneously.** Hearing-impaired listeners suffer in noise specifically when babble is *spatially diffuse* — there is no directional null to point a classical beamformer at, because the interference is everywhere.
- **Joint modeling is more biologically plausible** than two separate pipelines: the auditory cortex doesn't bolt directional and diffuse processing together post-hoc.
- **Pairs naturally with target-speaker-extraction (TSE)** approaches like the sub-5ms causal TSE (Hsu et al., April 2026, already in wiki). Directional filtering picks the source by spatial position; TSE picks by speaker embedding; diffuse extraction handles the rest. This three-way decomposition is increasingly how production hearing aids will think about the scene.
- **Fraunhofer pipeline:** Habets' group is upstream of Phonak/Sonova's spatial-audio research. NDF+ findings tend to surface in Phonak Infinio / Sphere generations one to two cycles later.

## Open Questions

- Latency profile: Habets-group papers historically aren't latency-constrained to HA budgets (10 ms). Real test is whether NDF+ has a causal, < 10 ms variant.
- Calibration / adaptation behavior in moving listeners (head turns) — diffuse-component statistics shift with head pose.
- How does it interact with bilateral HA processing — is diffuse extraction done per-ear or shared?

## Source

arXiv:2605.06108 — submitted 7 May 2026. https://arxiv.org/abs/2605.06108
Backfilled in the 2026-05-10 daily digest after arXiv abstract page resolved (was previously listed as TBD pending paper page).
