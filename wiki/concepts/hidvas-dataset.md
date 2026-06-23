---
title: HIDVAS — Hearing Instrument Dataset in Various Acoustical Scenarios
type: concept
created: 2026-06-15
updated: 2026-06-23
last_change: "2026-06-23 — Flagged HIDVAS as the natural training substrate for the DDSP-EQ adaptive room EQ framework (Marcos-Macias et al., arXiv:2606.22563, DAFx26, Jun 21 2026). Added the DDSP-EQ source to frontmatter and a new sub-section calling out the dome × reverb cross-product as the per-wearer fitting substrate for the FxLMS-DDSP recast."
sources:
  - arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md
  - arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md
related:
  - training-deployment-distribution-gap.md
  - room-aware-dereverberation.md
  - synthetic-data-for-hearing-ai.md
  - speech-enhancement-neural-networks.md
  - dnn-architectures-hearing-aids.md
  - close-to-distant-microphone-projection.md
  - differentiable-dsp.md
  - fxlms-adaptive-filtering.md
  - acoustic-feedback-cancellation.md
tags: [public-dataset, hearing-aid-benchmark, ku-leuven, dummy-head-recordings, dome-configuration, vent-acoustics, eardrum-microphone, real-recordings, cc-by-4-0, eurasip-jasmp, ddsp, fxlms]
---

# HIDVAS — Hearing Instrument Dataset in Various Acoustical Scenarios

## What
A public dataset of real (not simulated) recordings made on a dummy head with mounted hearing-instrument shells, accepted at the EURASIP Journal on Audio, Speech, and Music Processing in June 2026 and released under CC-BY-4.0 by Roebben, Bernardi, Wouters, van Waterschoot, Moonen at KU Leuven.

## Composition
- **Recording platform:** dummy head with mounted BTE and RIC hearing-instrument shells; eardrum-level microphones.
- **External array:** 8 loudspeakers, 2 reference microphones in the room.
- **Stimuli:** male and female speech, speech-shaped noise, singing voice, stringed instrument, wind instrument, percussion instrument.
- **Reverberation conditions:** T30 = 0.09 s, 0.47 s, 0.73 s (one room), 1.48 s (a second room).
- **Dome configurations:** open, semi-open, closed, no-RIC (control).
- **Format:** both impulse responses and audio recordings (the "hearing instrument in a box" framing).
- **Use cases:** three example use cases are documented in the paper.

## Why It Matters

### Real recordings beat simulators on the sim-to-real axis
- Most public hearing-aid SE training data uses simulated reverb (RIR convolution + additive noise).
- Deployed systems chronically underperform vs. lab benchmarks on real-world reverberant scenes.
- HIDVAS captures diffraction around the head, body shadow, vent leak, microphone-placement asymmetries that simulators miss.

### Dome configuration as a first-class published variable
- Vent acoustics drive fitting decisions in the clinic — low-frequency leak, occlusion, own-voice perception, feedback margin.
- Almost no public ML dataset has captured dome variation as a structured factor; ML pipelines train on one acoustic configuration and silently inherit a distribution mismatch.
- HIDVAS exposes the vent-acoustic axis for ML training and evaluation pipelines at this granularity for the first time.

### Substrate, not just a corpus
- Provides both audio and impulse responses → researchers can compose new scenarios via convolution while still using real measurement primitives.
- Useful for: SE algorithm benchmarking, beamformer evaluation, room-aware dereverb training, scene classification, listener-perception modelling.

### Continuity with KU Leuven's public-substrate program
- KU Leuven has been steadily releasing structured public benchmarks for hearing-relevant ML — SparrKULee (n=85 EEG, 168 h, speech-evoked auditory responses), AV-GC-AAD (gaze-controlled auditory attention decoding), and now HIDVAS.
- An emerging "publish your measurement room" pattern as substrate for academic-industry collaboration in hearing AI.

## DDSP-EQ Use Case (Marcos-Macias et al., Jun 21 2026)
The DDSP-EQ framework ([arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md](../../sources/arxiv-2606-22563-ddsp-adaptive-room-eq-jun-2026.md), DAFx26) recovers classical **FxLMS** as a Differentiable DSP special case for adaptive room equalisation. HIDVAS supplies exactly the substrate that framework needs:
- **4 dome configurations × 4 reverberation conditions, with impulse responses included.** Train DDSP-EQ on subsets, hold out a dome / reverb to evaluate generalisation.
- **Per-dome personalisation studies.** Fit a DDSP-EQ topology per dome configuration — the clinical fitting question the framework is built for.
- **Stackable with neural feedback cancellation (DFC-IL, Voit & Doclo, Jun 2026)** — joint training of DDSP-EQ + DFC-IL on HIDVAS IRs is unpublished but architecturally straightforward.

See [[differentiable-dsp]] and [[fxlms-adaptive-filtering]] for the operator-family framing.

## Limitations / Open Pieces
- No listener-perception labels (HASPI / COSI / effort ratings) — pair with CPC1/2/3 for end-to-end evaluation.
- No pediatric / cross-lifespan variants — addresses the adult-distribution-only critique only partially.
- No bilateral fitting feedback or care-partner dyad — single-listener framing.

## Related Pages
- [[training-deployment-distribution-gap]] — HIDVAS is the public-benchmark instance of the closure tactic for this gap
- [[room-aware-dereverberation]] — HIDVAS provides the RIR substrate for RIR-conditioned dereverb training
- [[synthetic-data-for-hearing-ai]] — HIDVAS is the real-data complement to simulator/synthetic pipelines
- [[close-to-distant-microphone-projection]] — sibling data-substrate work (C2D is a method, HIDVAS is a dataset)
- [[speech-enhancement-neural-networks]] — primary downstream consumer
- [[dnn-architectures-hearing-aids]] — DNN training pipelines that benefit from a real-acoustic public benchmark

## Sources
- [Roebben et al. — HIDVAS (arXiv:2606.14175, EURASIP JASMP, June 12, 2026)](../../sources/arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md) — primary source
