---
title: Training–Deployment Distribution Gap in Hearing-Aid ML
type: concept
created: 2026-06-03
updated: 2026-06-15
sources:
  - arxiv-2606-03832-dfc-il-voit-doclo-jun-2026.md
  - arxiv-2606-13109-c2d-microphone-projection-nakatani-jun-2026.md
  - arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md
related:
  - acoustic-feedback-cancellation.md
  - on-device-ml-hearing-aids.md
  - speech-enhancement-neural-networks.md
  - dnn-architectures-hearing-aids.md
  - continual-learning-hearing-ai.md
  - close-to-distant-microphone-projection.md
  - synthetic-data-for-hearing-ai.md
tags: [training-loop, closed-loop-dynamics, distribution-shift, deployment-gap, methodology, dsp, on-chip, c2d, real-paired-data, simulation-to-reality-gap]
---

# Training–Deployment Distribution Gap in Hearing-Aid ML

## Concept
Hearing aids deploy ML models into a closed-loop acoustic environment — the wearer's ear canal, the room around it, the feedback path from receiver to microphone, the body-worn motion of the device itself. The ML training stack, by contrast, almost always optimises against **open-loop, quasi-stationary, offline corpora**. The gap between training conditions and deployment conditions is the unmeasured contributor to many real-world failures attributed to "the model."

The argument was sharpened by Voit & Doclo's June 2026 work on deep feedback cancellation (arXiv:2606.03832): training the neural canceller *inside* the closed-loop dynamics it will face (DFC-IL) holds stability at high amplification gains where open-loop-trained variants begin to howl. The same gap, structurally, applies to most hearing-aid ML sub-problems.

## Where the Gap Appears

| Sub-problem | Open-loop training assumes | Deployment reality |
|---|---|---|
| Feedback cancellation | Stable feedback path, fixed gain | Time-varying path, non-stationary gain, instability near operating point |
| Speech enhancement | Stationary noise mixed offline | Non-stationary scenes, dynamic SNR, wearer movement |
| Beamforming | Static array geometry, fixed listener | Head turns, occlusion, hair, glasses |
| Scene classification | Balanced corpus | Wearer-specific scene distribution, long tails |
| Own-voice detection | Studio-recorded own-voice | Cough, chewing, head motion, partial occlusion |
| Noise reduction | iid noise | Convolutional reverberation, talker interruption |

## Why It Has Persisted
- Closed-loop simulation is **slow** and not differentiable end-to-end without explicit modelling.
- Open-loop training is **easier to scale** with web-scraped or synthetic data.
- Evaluation harnesses themselves (PESQ, STOI, HASPI, WER) are **measured under open-loop conditions**, masking the gap until real-world telemetry surfaces it.
- The training-loop framing is a **methodology** argument, harder to publish than a new architecture.

## What Closes the Gap
Drawing from DFC-IL and adjacent literature:
1. **In-the-loop training** — feed the model its own outputs back through a simulated acoustic environment during training.
2. **Domain randomization at the dynamics level** — sample over the parameters of the closed-loop system (gain, path delay, room geometry).
3. **Telemetry-grounded fine-tuning** — use deployed-device logs (where regulation permits) to surface failure modes for retraining.
4. **Curriculum from stable to unstable** — train on quasi-stationary first, anneal toward the unstable operating regime.
5. **Predetermined change control plans** — regulatory frameworks (FDA SaMD, EU AI Act) that allow telemetry-driven update of the model post-clearance.
6. **Real paired training data via C2D microphone projection** (Nakatani et al., ICASSP 2026, arXiv:2606.13109) — closes the **data-side** instance of the gap by replacing simulated noisy-clean pairs with real ones derived from dual-microphone field recordings + PMWF projection. The DFC-IL approach closes the gap on the **dynamics** side (closed-loop feedback); C2D closes it on the **data** side (clean reference). They are complementary and stackable. See [[close-to-distant-microphone-projection]].
7. **Public real-recording benchmarks like HIDVAS** (Roebben et al., KU Leuven, arXiv:2606.14175, June 12, 2026) — close the **evaluation-substrate** instance of the gap by publishing real dummy-head + eardrum-level recordings across structured acoustic and dome-configuration factors that simulators silently fail to capture. Where DFC-IL closes the dynamics side and C2D closes the paired-data side, HIDVAS closes the shared-benchmark side: it gives the community a common real-acoustic yardstick rather than letting each team ship a simulator-bound private benchmark. See [[hidvas-dataset]].

## Why It Matters Strategically
The architectural lever ("bigger model, more data, foundation-model fine-tune") is approaching diminishing returns. The training-loop lever (close the gap between train and deploy) is **earlier on its curve**. Teams that integrate closed-loop dynamics into their training pipeline are likely to capture a non-obvious quality margin without needing to ship a bigger model.

## Related Pages
- [[acoustic-feedback-cancellation]] — the canonical case where this gap is most visible
- [[on-device-ml-hearing-aids]] — the deployment substrate where the gap is felt
- [[speech-enhancement-neural-networks]] — the largest population of models silently affected
- [[continual-learning-hearing-ai]] — the closed-loop framing extended over the user's lifetime
- [[dnn-architectures-hearing-aids]] — the architectural lever this concept counter-positions
- [[close-to-distant-microphone-projection]] — closes the data-side instance of the gap (real paired SE training data)
- [[synthetic-data-for-hearing-ai]] — the simulation paradigm whose limits this concept names

## Sources
- [Voit & Doclo — In-the-Loop Training of Deep Feedback Cancellation for Hearing Aids (arXiv:2606.03832)](../../sources/arxiv-2606-03832-dfc-il-voit-doclo-jun-2026.md) — origin of the DFC-IL framing, primary empirical evidence for the gain-regime stability gap
- [Nakatani et al. — C2D Microphone Projection (arXiv:2606.13109, ICASSP 2026)](../../sources/arxiv-2606-13109-c2d-microphone-projection-nakatani-jun-2026.md) — closes the data-side instance of the gap with real paired SE training data via dual-mic + PMWF projection
- [Roebben et al. — HIDVAS Hearing Instrument Dataset (arXiv:2606.14175, EURASIP JASMP)](../../sources/arxiv-2606-14175-hidvas-ku-leuven-jun-2026.md) — closes the public-benchmark instance of the gap with real dummy-head + eardrum-level recordings across 4 dome configurations and 4 reverberation conditions
