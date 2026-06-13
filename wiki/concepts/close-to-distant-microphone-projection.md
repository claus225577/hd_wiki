---
title: Close-to-Distant (C2D) Microphone Projection — Real Paired Training Data for Speech Enhancement
type: concept
created: 2026-06-13
updated: 2026-06-13
sources: [arxiv-2606-13109-c2d-microphone-projection-nakatani-jun-2026.md]
related: [synthetic-data-for-hearing-ai.md, speech-enhancement-neural-networks.md, training-deployment-distribution-gap.md, closed-loop-data-flywheel.md, linguistic-hallucination-speech-enhancement.md, dnn-in-hearing-aids.md, probabilistic-generative-models-hearing-ai.md, on-device-ml-hearing-aids.md]
tags: [training-data, close-to-distant, c2d, microphone-projection, pmwf, parametric-multichannel-wiener-filter, simulation-to-reality-gap, real-paired-data, chime6, guided-source-separation, hearing-aid-data-collection, training-substrate, ntt]
---

# Close-to-Distant (C2D) Microphone Projection

A training-data substrate for speech enhancement that produces **real noisy-clean pairs** from dual-microphone field recordings, replacing the simulated noisy-clean pairs that have been the field's default for the last decade. Introduced by **Nakatani, Ikeshita, Kamo, Delcroix & Araki** (NTT Communication Science Laboratories) at **ICASSP 2026** (arXiv:2606.13109, submitted 11 Jun 2026).

## The Problem C2D Solves

Modern speech-enhancement (SE) DNNs require **paired noisy-clean training data** — a noisy input and the clean reference the model should learn to produce. In real-world acoustic environments, clean references are not available: the deployed device records noisy signal, and there is no oracle of what the underlying clean speech was.

The field has worked around this for a decade with **simulated** pairs:
- Take clean speech corpora (LibriSpeech, VCTK, internal OEM corpora).
- Convolve with measured or generated room impulse responses.
- Add noise at controlled SNRs.
- Train on the simulated pairs.

The resulting models inherit a **simulation-to-reality gap** — they generalize imperfectly to the acoustic conditions a deployed device actually encounters. This is one face of the broader [[training-deployment-distribution-gap]].

## The C2D Method

C2D records the same scene with **two microphones**:

1. **Close-talking microphone** — near the speaker's mouth. High SNR, near-clean speech, but **not** a true clean reference (still contains environmental leakage, residual reverberation, SNR floor).
2. **Distant microphone array** — further from the speaker. The realistic deployment condition: noisy, reverberant, the signal a hearing aid or far-field device would receive.

C2D estimates an **optimal projection matrix** that:
- Transforms the close-mic input into the corresponding clean reference for the distant array, **and**
- Simultaneously performs denoising of the close-mic signal.

The implementation is a variant of the **Parametric Multichannel Wiener Filter (PMWF)** — a classical optimal beamformer / denoiser parameterized to operate as a learned projection across the two mic positions.

The output is a noisy-clean pair: the distant-mic recording as the noisy input, the C2D-projected close-mic recording as the clean target. Both come from **the same real acoustic event** — no simulation step.

## Reported Result (Nakatani et al., ICASSP 2026)

- Evaluated on the **CHiME6 dinner-party ASR** task under **oracle diarization**.
- **Outperforms Guided Source Separation (GSS)** — the prior SOTA in that setting — on enhancement quality and downstream ASR.
- C2D-derived SE training targets are demonstrably better than the alternative real-data cleaning pipeline.

## Why C2D Matters for Hearing Aids

### 1. The Lever Moves From "Bigger Model" to "Better Training-Signal Substrate"

The 2023-2026 hearing-aid SE arms race has spent most of its margin on architecture (CRN → SepFormer → Mamba → diffusion → SB-RF) and on synthetic-data scale (12M sound scenes for Oticon More 2021, 13.5M-22M for current flagships). Both levers are showing diminishing returns: architectures are bumping into the <10 ms HA latency budget, and synthetic scenes do not close the simulation-to-reality gap regardless of count.

C2D opens a **third lever**: the same model, same architecture, same compute budget — but trained on real paired data. The improvement is upstream of every architectural choice.

### 2. A Concrete Data-Collection Pathway

The C2D pattern maps cleanly onto a hearing-aid data-collection cohort:

| Component | Role |
|---|---|
| **Body-worn close-talk mic** | Wearer-mounted lavalier or collar mic produces the close-mic signal |
| **Ear-worn aid mics** | The deployed-condition distant array — same form factor as the production hearing aid |
| **Field recording during real-world use** | Both mics record simultaneously across the day |
| **C2D projection (offline)** | Converts close-mic recordings into clean training targets paired with the aid-mic distant recording |

This is a deployable program. The privacy and consent overhead is non-trivial — close-mic field recordings are high-fidelity speech samples — but the engineering pattern is unambiguous and the labels it produces are paired training data that no amount of simulation can reproduce.

### 3. Composability With Every Other Frontier

C2D is **orthogonal** to:
- **Latency-floor work** — SB-RF (one-step generative SE), HALO (half-frame-rate STFT SE), DriftSE (equilibrium one-step), DiffVQE (one-step AEC). C2D-trained models can run any of these inference architectures.
- **Architecture search** — NDF+, Spatial-Magnifier, TF-MLPNet, GAP-URGENet. The training data substrate is independent of the model topology.
- **In-the-loop training** — DFC-IL closes the train-vs-deploy gap on the dynamics side (feedback path); C2D closes it on the data side (clean reference). They stack.
- **Personalization tier** — DAL (differentiable cochlea), AIDA-2 (Bayesian generative). C2D produces the training pairs; DAL/AIDA-2 reshape the loss function on top.

A team could swap simulated training pairs for C2D-derived real pairs without changing any other piece of their SE stack.

### 4. Partial Mitigation of the Generative-SE Hallucination Risk

The May-June 2026 hallucination evidence (L3-SE / Wang et al., May 2026; Saha Shetu / Habets / Brendel, June 2026) shows that generative SE produces measurably more linguistic hallucinations than discriminative SE, particularly in OOD conditions. A non-trivial fraction of "OOD" is just "the simulated training distribution did not match deployment." Real paired data narrows the OOD region the model has to extrapolate across.

C2D does **not** eliminate generative-SE hallucination — the strong language prior is the immediate cause, not the training data — but it reduces one of the upstream contributors.

## Counter-Position to Simulated Synthetic Data

The standard hearing-aid training-data taxonomy (see [[synthetic-data-for-hearing-ai]]) has been:

| Approach | Method | Scale Potential | Realism |
|---|---|---|---|
| Traditional synthetic mixing | Signal processing: mix clean speech + noise at various SNRs | High | Medium — limited by mixing rules |
| HA microphone simulation | Convolve clean audio with measured HA impulse responses | Medium | High for known devices |
| AI-generated synthetic data | Large model generates / augments scenarios (Meta-style) | Very high | Potentially high |
| **C2D real paired data (NEW)** | **Dual-mic field recording + PMWF projection** | **Medium-bounded by collection cost** | **Real — no simulation step** |

C2D occupies a slot the taxonomy did not previously have a credible entry for: **scalable real paired data**. Earlier real-data approaches (e.g., headphone playback in real rooms) hit calibration and acoustic-validity ceilings; C2D's PMWF projection is the missing piece that lets the close-mic act as a clean target without actually being one.

## Open Questions

- **Compute cost at corpus scale.** The PMWF projection is per-scene; how does it scale to the 10M+ pairs OEMs train on?
- **From dinner-party to mobile wearer.** CHiME6 is a fixed-array static-room evaluation. Does C2D survive moving heads, body motion, hair, glasses, and head-shadow asymmetry — the actual HA wearing conditions?
- **Diarization dependency.** The CHiME6 evaluation uses oracle diarization. Does C2D need oracle speaker boundaries, or can it be combined with neural diarization (the [[foundation-model-fusion-speech]] direction)?
- **Privacy & consent.** Close-mic field recordings are high-fidelity speech. Differential-privacy, on-device aggregation, or post-collection redaction may need to be co-designed with the C2D pipeline.
- **Wearer-specific signal in the projection matrix.** Does the learned projection capture head-shadow / mic-placement / individual-anatomy information that could be reused for personalization rather than only training-target generation?
- **Composition with continual learning.** [[continual-learning-hearing-ai]] argues the natural HA personalization tier is the companion phone. C2D-derived field pairs feed into that loop as the on-device label substrate.

## Related Pages
- [[synthetic-data-for-hearing-ai]] — counter-paradigm; C2D is the real-data alternative to simulation
- [[speech-enhancement-neural-networks]] — downstream model substrate that consumes C2D-derived training pairs
- [[training-deployment-distribution-gap]] — broader concept; C2D closes the data-side instance of the gap
- [[closed-loop-data-flywheel]] — adjacent: where the field-recording side of the equation lives
- [[linguistic-hallucination-speech-enhancement]] — failure mode partly driven by training-distribution mismatch
- [[probabilistic-generative-models-hearing-ai]] — alternative paradigm; could also benefit from real paired data
- [[dnn-in-hearing-aids]] — production SE consumer of training data
- [[on-device-ml-hearing-aids]] — deployment substrate the C2D-trained model targets

## Sources
- [Nakatani et al. — Close-to-Distant Microphone Projection for Real-World SE (arXiv:2606.13109, ICASSP 2026)](../../sources/arxiv-2606-13109-c2d-microphone-projection-nakatani-jun-2026.md) — origin of the method; CHiME6 evaluation; PMWF implementation; outperforms Guided Source Separation
