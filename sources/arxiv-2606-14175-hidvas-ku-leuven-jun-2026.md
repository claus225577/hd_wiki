---
title: HIDVAS — A Hearing Instrument Dataset in Various Acoustical Scenarios for Algorithm Evaluation and Training
type: source
date: 2026-06-12
ingested: 2026-06-15
authors: [Arnout Roebben, Giuliano Bernardi, Jan Wouters, Toon van Waterschoot, Marc Moonen]
publication: arXiv:2606.14175 (eess.AS), accepted EURASIP Journal on Audio, Speech, and Music Processing
url: https://arxiv.org/abs/2606.14175
institution: KU Leuven (ESAT-STADIUS, ESAT-PSI / ExpORL)
license: CC-BY-4.0
tags: [hearing-aid-dataset, public-benchmark, dummy-head-recordings, dome-configuration, vent-acoustics, reverberation, eardrum-microphone, bte, ric, sim-to-real, ku-leuven, eurasip-jasmp]
---

# HIDVAS — A Hearing Instrument Dataset in Various Acoustical Scenarios

## Metadata
- **Title:** HIDVAS: A Hearing Instrument Dataset in Various Acoustical Scenarios for Algorithm Evaluation and Training
- **Authors:** Arnout Roebben, Giuliano Bernardi, Jan Wouters, Toon van Waterschoot, Marc Moonen (KU Leuven)
- **arXiv:** 2606.14175 (eess.AS)
- **Posted:** June 12, 2026
- **Accepted:** EURASIP Journal on Audio, Speech, and Music Processing
- **License:** CC-BY-4.0 (open)

## Method
- Real (not simulated) recordings made on a **dummy head** with mounted hearing-instrument shells in **behind-the-ear (BTE)** and **receiver-in-canal (RIC)** configurations.
- **Eardrum-level microphones** capture the signal as the user would perceive it.
- **8 external loudspeakers** drive stimuli; **2 external reference microphones** in the room.
- Stimuli: male and female speech, speech-shaped noise, singing voice, stringed instrument, wind instrument, percussion instrument.
- **4 reverberation conditions:** three in one room (T30 = 0.09 s, 0.47 s, 0.73 s) + one in a different room (T30 = 1.48 s).
- **4 dome configurations:** open, semi-open, closed, no-RIC (control without receiver in canal).
- Provides both impulse responses and audio recordings — described as a "hearing instrument in a box."
- Three example use cases included to demonstrate practical application.

## Why It Matters for Hearing AI

### Real recordings vs simulated reverberation
- Most public training data for hearing-aid speech enhancement uses simulated reverb (RIR convolution + additive noise).
- Deployed systems chronically underperform vs. lab benchmarks on real-world reverberant scenes — the "sim-to-real" gap.
- HIDVAS provides real measurements that capture diffraction around the head, body shadow, vent leak, microphone placement asymmetries that simulators miss.

### Dome configuration as a first-class published variable
- Clinical fitting decisions hinge on dome selection (vent size, occlusion, low-frequency leak, own-voice perception, feedback margin).
- Almost no public ML dataset has captured dome variation as a structured factor; most ML pipelines train on one acoustic configuration and silently inherit a distribution mismatch.
- HIDVAS exposes the vent-acoustic axis to ML training and evaluation pipelines for the first time at this granularity.

### "Hearing instrument in a box" — a substrate, not a corpus
- The dataset includes both audio and impulse responses → enables researchers to compose new scenarios via convolution while still using real measurement primitives.
- Useful for: SE algorithm benchmarking, beamformer evaluation, room-aware dereverb training, scene classification, listener-perception modelling.

### Continuity with KU Leuven's public-substrate program
- KU Leuven has been steadily releasing structured public benchmarks for hearing-relevant ML — SparrKULee (n=85 EEG, 168 h, speech-evoked auditory responses), AV-GC-AAD (gaze-controlled auditory attention decoding), and now HIDVAS.
- Signals an emerging "publish your measurement room" approach to building academic-industry collaboration substrate in hearing AI.

### Open piece — what's still missing
- Listener-perception labels (HASPI/COSI/effort ratings) are not part of HIDVAS itself; pair with CPC datasets for end-to-end evaluation.
- Pediatric / cross-lifespan variants not in this drop — addresses the adult-distribution-only critique only partially.
- No bilateral fitting feedback (the dyad / care-partner unit, see ASHA NSLHM angle May 2026).

## Cross-References
- Related concept: `room-aware-dereverberation.md` (HIDVAS provides RIR substrate for RIR-conditioned dereverb training)
- Related concept: `training-deployment-distribution-gap.md` (HIDVAS is a structural fix on the sim-to-real axis)
- Related concept: `synthetic-data-for-hearing-ai.md` (HIDVAS is the real-data complement to Meta synthetic data April 2026)
- Related source: `arxiv-2606-13109-c2d-mic-projection-nakatani-jun-2026.md` (also data-substrate; C2D is a *method* for paired-mic training data, HIDVAS is a published *dataset*)
- Related source: `arxiv-2606-04103-dal-differentiable-cochlea-google-jun-2026.md` (DAL provides a per-listener cochlear model; HIDVAS provides the per-room acoustic substrate)
- Related entity: `ku-leuven-hearing-research.md` (new candidate entity page)
- Related concept: `hidvas-dataset.md` (new concept page)
