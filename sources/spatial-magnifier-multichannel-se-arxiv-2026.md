---
title: "Spatial-Magnifier: Spatial Upsampling for Multichannel Speech Enhancement"
authors: [Dongheon Lee, Ashutosh Pandey, Sanjeel Parekh, Daniel Wong, Jacob Donley, Buye Xu, Juan Azcarreta]
affiliation: Meta Reality Labs (and collaborators)
date: 2026-05
arxiv_listing: https://arxiv.org/list/eess.AS/2026-05
type: research-paper
tags: [speech-enhancement, multichannel, spatial-upsampling, beamforming, mic-arrays, wearables, hearing-aids, earbuds, meta-reality-labs]
---

# Spatial-Magnifier: Spatial Upsampling for Multichannel Speech Enhancement (Lee et al., May 2026)

## Key Extraction

- **Question:** A wearable mic array (hearing aid, earbud, smart glasses) has fundamentally limited beamformer selectivity because mic spacing is constrained by industrial design. Can a learned model approximate the spatial selectivity of a *larger* array from a small one?
- **Method:** Learn a spatial-upsampling stage that maps the multichannel input from a small array to features as if produced by a denser/larger array, and feed the upsampled spatial representation into a downstream multichannel speech-enhancement network.
- **Authors / Affiliation:** Lee, Pandey, Parekh, Wong, Donley, Xu, Azcarreta — Meta Reality Labs and collaborators (group also publishes prior multichannel-SE work for the Quest line).

## Why This Matters for Hearing AI

- **The mic-spacing wall is the binding constraint** on directional selectivity in wearable form factors. A hearing aid behind the ear or an in-ear earbud cannot physically host the mic spacing that gets a large conference-room beamformer its directionality.
- **Spatial upsampling is the wearable-friendly analogue of super-resolution** for vision — instead of more silicon, more pixels, or a bigger array, you bolt on a learned stage that *infers* what a denser array would have measured. The DSP cost lives in the model, not the hardware.
- **Auracast / LE Audio convergence:** As streaming audio shifts upstream of the device, the *device's own* mic array becomes more critical for the listening-effort-dominated cocktail-party scene where streaming doesn't help. Spatial upsampling targets exactly this regime.
- **Beamformer + DNN cascades** are how production hearing aids handle directionality today. Spatial upsampling slots in as a pre-processing stage upstream of the existing beamformer / DNN pipeline.

## Open Questions

- Does the spatial-upsampling stage add latency above the < 10 ms hearing-aid budget? Wearable / AR/VR latency budgets are looser than HA — production transfer is non-trivial.
- How does it compose with binaural processing (left + right HA) where the *bilateral* virtual array is already much larger than either monaural array?
- Calibration sensitivity — small mic arrays in HAs drift; learned spatial-upsampling models are typically more sensitive to calibration than classical beamformers.

## Source

arXiv eess.AS May 2026 listing (paper #10 in the listing). Full paper accessed via arXiv listing page; specific arXiv ID to be backfilled when paper page resolves.
