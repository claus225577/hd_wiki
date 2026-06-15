---
title: HIDVAS — Hearing Instrument Dataset in Various Acoustical Scenarios
type: concept
created: 2026-06-15
updated: 2026-06-15
sources:
  - arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md
related:
  - training-deployment-distribution-gap.md
  - room-aware-dereverberation.md
  - synthetic-data-for-hearing-ai.md
  - speech-enhancement-neural-networks.md
  - dnn-architectures-hearing-aids.md
  - close-to-distant-microphone-projection.md
tags: [public-dataset, hearing-aid-benchmark, ku-leuven, dummy-head-recordings, dome-configuration, vent-acoustics, eardrum-microphone, real-recordings, cc-by-4-0, eurasip-jasmp]
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
