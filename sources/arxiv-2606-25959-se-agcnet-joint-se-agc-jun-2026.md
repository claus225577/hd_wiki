---
title: "SE-AGCNet: An End-to-End Framework for Joint Speech Enhancement and Loudness Control in Meeting Scenarios"
type: source
source_type: arxiv-preprint
date_published: 2026-06-24
date_ingested: 2026-06-25
authors: [Jinming Zhang, Wei Rao, Xionghu Zhong, Eng Siong Chng]
identifier: arXiv:2606.25959
url: https://arxiv.org/abs/2606.25959
venue: arXiv (eess.AS) / accepted Interspeech 2026
tags: [speech-enhancement, automatic-gain-control, agc, wdrc, loudness, lufs, joint-optimization, end-to-end, hearing-aids, interspeech-2026]
---

# SE-AGCNet: An End-to-End Framework for Joint Speech Enhancement and Loudness Control in Meeting Scenarios

## Bibliographic
- **Authors:** Jinming Zhang, Wei Rao, Xionghu Zhong, Eng Siong Chng
- **Posted:** 24 June 2026
- **Venue:** arXiv 2606.25959 (eess.AS); **accepted Interspeech 2026**
- **URL:** https://arxiv.org/abs/2606.25959

## Problem
In conventional audio pipelines — including hearing aids — speech enhancement (SE) and automatic gain control (AGC) / wide-dynamic-range compression (WDRC) are implemented as **cascaded modules** tuned independently. Two failure modes are formally identified:

1. **AGC before SE** — amplifies background noise into the SE input, harming downstream noise reduction.
2. **SE before AGC** — over-suppresses low-volume speech that the gain stage was supposed to recover.

In hearing-aid fitting practice, the second failure mode shows up as the canonical complaint "it's quieter, but the soft talkers got quieter too."

## Contribution
**SE-AGCNet** — end-to-end joint optimisation of SE and AGC with a **loudness-aware loss function**:

- **Joint training** of SE and AGC sub-networks (architecture details in the paper).
- **Loss includes loudness metrics**: integrated loudness (LUFS, ITU-R BS.1770), short-term LUFS (St LUFS), and Loudness Range (LRA) — alongside conventional SE objectives.
- **Companion data-generation pipeline** — *SE-AGC-DataGen* — synthesises paired training data with controlled loudness and noise characteristics, addressing the fact that no off-the-shelf dataset provides the joint distribution of (clean speech, noisy speech, target loudness profile).

## Key Results
- Evaluated on speech quality, ASR accuracy, and loudness achievement.
- Outperforms cascaded SE→AGC and AGC→SE baselines on all three axes (per abstract).
- Tailored for meeting scenarios; the underlying joint-optimisation idea generalises.

## Why It Matters for Hearing Aids
1. **The NR→WDRC cascade is an artefact, not a law.** Hearing aids have shipped SE and WDRC as separately-tuned modules for 25 years. The artefact is downstream of when SE was DSP, WDRC was DSP, and the two teams didn't share a loss function. End-to-end joint training removes the artefact.
2. **The HA ML loss function has been wrong.** PESQ, STOI, SI-SDR optimise intelligibility *surrogates*. LUFS-aware losses optimise **perceived loudness** — which is what the wearer actually experiences and what audiologists actually fit against (NAL-NL2, DSL v5 target curves are loudness-balanced).
3. **Block-diagram consolidation.** A "single learned NR+WDRC block" replaces two separately-validated modules. This collapses fitting parameters, simplifies the regulatory story for AI-modified processing, and unifies the training-data substrate.

## Adjacent / Related Work
- **NAL-NL2, DSL v5** — Prescriptive gain rules that hearing-aid AGC/WDRC fits to today. SE-AGCNet's LUFS-aware loss is conceptually compatible with these targets but expressed in modern loudness metrics.
- **DAL (Differentiable Auditory Loss, Google, arXiv:2606.04103, Jun 2026)** — differentiable loudness-/excitation-aware losses for SE. Same family of "match the loss to the auditory system, not the spectrogram."
- **GAP-URGENet / Korhonen natural-vs-DNN** — Recent work pointing out that classical processing sometimes beats DNN SE; joint optimisation may close that gap by aligning the optimisation target with the perceptual goal.

## Open Questions
- **Latency.** Meeting scenarios tolerate hundreds of ms; HA budget is <10 ms. Does the SE-AGCNet architecture meet HA latency, or does the joint-optimisation idea need a redesigned low-latency variant?
- **Fitting interface.** What replaces NAL-NL2/DSL v5 prescription targets when the WDRC stage is no longer a parametric compressor but a learned block? Fitters need a knob.
- **Per-ear personalisation.** The paper trains on a population; HA processing is per-wearer. Does the LUFS-aware loss compose with audiogram-conditioning?
