---
title: Joint Speech Enhancement + WDRC / AGC (End-to-End)
type: concept
created: 2026-06-25
updated: 2026-06-25
sources: [arxiv-2606-25959-se-agcnet-joint-se-agc-jun-2026.md]
related: [speech-enhancement-neural-networks.md, dnn-in-hearing-aids.md, dnn-architectures-hearing-aids.md, differentiable-dsp.md, nal-nl2-fitting.md, listening-effort-evaluation.md, dnn-vs-natural-processing.md, on-device-ml-hearing-aids.md]
tags: [speech-enhancement, automatic-gain-control, agc, wdrc, loudness, lufs, joint-optimization, end-to-end, hearing-aids, loss-function, perceived-loudness, se-agcnet]
---

# Joint Speech Enhancement + WDRC / AGC (End-to-End)

The dominant block diagram inside every shipping hearing aid for the past 25 years has been a cascade:

```
mic → [feedback cancellation] → [noise reduction / SE] → [WDRC / AGC] → [output]
```

Each block is tuned independently. NR (or DNN-SE in modern chips) is optimised against intelligibility metrics (PESQ, STOI, SI-SDR). WDRC is fitted against prescriptive loudness targets (NAL-NL2, DSL v5). The two modules are validated separately, often by different teams, and integrated by chaining them at runtime.

**The June 2026 challenge to this design:** the cascade is an artefact — not a law — and joint optimisation removes it.

## The Failure Modes the Cascade Hides

Zhang, Rao, Zhong & Chng (SE-AGCNet, [[../../sources/arxiv-2606-25959-se-agcnet-joint-se-agc-jun-2026]], arXiv:2606.25959, 24 Jun 2026, accepted Interspeech 2026) formalise two failure modes that hearing-aid fitters have lived with for years:

| Order | Failure mode |
|---|---|
| AGC → SE | The gain stage amplifies background noise into the SE input, harming downstream noise reduction. |
| SE → AGC | The SE stage over-suppresses low-volume speech that the gain stage was supposed to recover. The classic "it's quieter, but the soft talkers got quieter too" fitting-room complaint. |

Each module, by itself, is doing its job correctly under its own loss. The failure is at the **interface** — and the interface is not optimised at all.

## SE-AGCNet — The Joint-Training Recipe

SE-AGCNet jointly optimises SE and AGC end-to-end with a **loudness-aware loss**:

- **Loss includes loudness metrics**: integrated loudness (LUFS, ITU-R BS.1770), short-term LUFS, and Loudness Range (LRA) — alongside conventional SE objectives.
- **Companion data generator**: *SE-AGC-DataGen* synthesises paired training data with controlled loudness and noise characteristics. Off-the-shelf datasets do not provide the joint (clean, noisy, target loudness) triple that joint optimisation needs.
- **Reported wins**: outperforms cascaded SE→AGC and AGC→SE baselines on speech quality, ASR accuracy, *and* loudness achievement.

The paper is framed for meeting scenarios; the joint-optimisation idea is what generalises.

## Why It Matters for Hearing Aids

### 1. The HA ML loss function has been wrong
PESQ, STOI, SI-SDR are *intelligibility surrogates*. They are not what the wearer experiences and not what audiologists fit against. NAL-NL2 and DSL v5 are **loudness-balanced** prescriptions — i.e., the clinical target is and always has been a loudness function, not a spectrogram-distance function. LUFS-aware losses (or DAL-style differentiable auditory losses; see [[differentiable-dsp]]) line up the optimisation target with the clinical target for the first time.

### 2. The block diagram collapses
"NR → WDRC" becomes a **single learned block**. The consequences ripple downstream:
- Fewer separately-validated modules → simpler regulatory story for AI-modified processing.
- Fewer fitting parameters at the interface → potentially simpler fitter UX.
- One training-data substrate covers both functions → less double-instrumentation.

### 3. Reframes the "DNN-vs-natural-processing" debate
The Korhonen / Widex finding that classical natural processing sometimes beats DNN SE may be an artefact of the same cascade-optimisation problem: DNN SE *plus* a downstream WDRC tuned independently can leave the wearer with worse loudness perception than a single well-tuned natural-processing chain. Joint optimisation could close that gap by aligning the optimisation target with the perceptual goal — see [[dnn-vs-natural-processing]].

## What's Still Missing for Hearing-Aid Deployment

- **Latency.** Meeting-scenario SE can tolerate hundreds of milliseconds; HA budget is <10 ms. SE-AGCNet's architecture has not been validated under that constraint.
- **Fitting interface.** What replaces NAL-NL2 / DSL v5 prescription targets when the WDRC stage is no longer a parametric compressor but a learned block? The fitter needs a knob, the regulator needs a target, and the audiogram still needs to be the input.
- **Per-ear personalisation.** SE-AGCNet trains on a population. Hearing aids process per-wearer with an audiogram-shaped gain prescription. Whether the LUFS-aware loss composes with audiogram conditioning is unsolved.
- **Compression-time-constants.** WDRC attack/release behaviour (typically 5–500 ms time constants) is part of the fitter's lever set. Learned end-to-end blocks need an equivalent surface — or a principled reason that one isn't needed.

## Adjacent Architectural Moves

- **DAL — Differentiable Auditory Loss** (Google, arXiv:2606.04103, Jun 2026). Same family of "match the loss to the auditory system, not the spectrogram." Could plug directly into SE-AGCNet's training signal.
- **[[differentiable-dsp]] (DDSP).** Adaptive room equalisation that subsumes FxLMS as a special case. Same pattern at a different stage of the chain — learnable operators replacing hand-tuned DSP modules.
- **[[on-chip-hearing-ai-levers-june-2026]] synthesis.** Joint NR+WDRC is a sixth lever to add alongside memory bandwidth, sparsity, inference steps, frame rate, and algebraic weight sharing.

## Implications for the 2028 HA Generation

The processing chain in a 2028 hearing aid likely contains *one* learned "noise-reduction + dynamic-range" block trained end-to-end with a loudness-aware loss, audiogram conditioning, and explicit fitter-exposed levers — not two cascaded modules with separate training pipelines. The fitting protocol that targets it is the harder open problem.

## Related Pages
- [[speech-enhancement-neural-networks]] — SE branch of the cascade being joined.
- [[dnn-in-hearing-aids]] — Production context.
- [[dnn-architectures-hearing-aids]] — Architecture catalogue.
- [[differentiable-dsp]] — Adjacent move: learnable DSP operators.
- [[nal-nl2-fitting]] — Prescriptive target the new loss has to compose with.
- [[listening-effort-evaluation]] — What the LUFS-aware loss is ultimately trying to influence.
- [[dnn-vs-natural-processing]] — Debate that joint optimisation may rewrite.
- [[on-device-ml-hearing-aids]] — Power/latency frame.

## Sources
- [SE-AGCNet: An End-to-End Framework for Joint Speech Enhancement and Loudness Control in Meeting Scenarios](../../sources/arxiv-2606-25959-se-agcnet-joint-se-agc-jun-2026.md) — primary, 24 Jun 2026 (Interspeech 2026).
