---
title: Clarity Prediction Challenge (CPC)
type: entity
created: 2026-05-27
updated: 2026-05-27
sources:
  - frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md
related:
  - ../concepts/non-intrusive-intelligibility-prediction.md
  - ../concepts/foundation-model-fusion-speech.md
  - ../concepts/speech-enhancement-neural-networks.md
  - ../concepts/listening-effort-evaluation.md
  - vcca-computational-audiology.md
tags: [evaluation-challenge, intelligibility-prediction, clarity-project, hearing-aid-benchmarks, cpc1, cpc2, cpc3, interspeech]
---

# Clarity Prediction Challenge (CPC)

## What It Is
A recurring open challenge run under the **Clarity Project**, asking participants to predict the percentage of words a hearing-impaired listener correctly recognizes from hearing-aid-processed speech, **given the audio and the listener's audiogram only** (i.e., non-intrusive prediction). It is one of the very few public, listener-grounded, hearing-aid-processed benchmarks.

## Iterations
- **CPC1, CPC2** — earlier rounds; established the listener-panel methodology and the non-intrusive framing.
- **CPC3** (deadline 31 July 2025; results presented at an ISCA workshop satellite event of Interspeech 2025, Rotterdam, 22 August 2025) — **fully dynamic listening environments, real backgrounds, measured hearing-aid signals.** 21 submissions from 14 teams worldwide, intrusive and non-intrusive tracks both populated.
- **CPC3 dataset** is publicly available (Zenodo) and has become the *de facto* benchmark for follow-up papers in 2026.

## Why It Matters
- **Listener-grounded.** Labels come from hearing-impaired participants, not from a synthetic intelligibility model — the dataset is the ground truth that the next-generation intelligibility metric is trained against.
- **Real measured HA signals.** Avoids the unrealism of simulating hearing-aid processing; the audio is what a wearer would actually hear.
- **Dynamic environments.** Moves away from the artificial static scenes that older benchmarks used.
- **Open submissions.** Any team can attack it — academic, OEM, startup. The CPC3 leaderboard is a credible cross-group comparison.

## What Has Happened After Results Presentation
- The CPC3 dataset has continued to attract submissions and analyses after the official challenge close.
- Notable May 2026 follow-up: **Nakazawa, "Frame-Aligned Fusion of Canary and WavLM" (arXiv:2605.23619, 22 May 2026)** — analyzes fusion-architecture choices on CPC3, reaches Eval RMSE 24.96 / Corr 0.796 with frame-aligned mid-fusion of Canary × WavLM.
- The competitive design choice has shifted from "which single foundation model" to "which encoder pair, and where do they meet" — CPC3 is the benchmark on which that question is currently being argued.

## Structural Role in the Field
- Acts as a **shared yardstick** that the post-HASPI evaluation stack is being calibrated against.
- Anchors the field's transition to non-intrusive, foundation-model-based intelligibility prediction.
- Likely host for the future axes the field still needs: linguistic faithfulness (cf. L3-SE), listening effort (Behringer et al.), ASR-independent acoustic faithfulness (de Oliveira et al.).

## Open Questions
- Will CPC4 (whenever it lands) require fusion-architecture declarations as part of submissions?
- Will the listener panel expand to include cross-lifespan stratification (pediatric, oldest-old) where current foundation models are most biased?
- Will OEMs commit listener-panel access to the Clarity Project to broaden ecological validity?

## Related Pages
- [[non-intrusive-intelligibility-prediction]] — the metric class CPC anchors
- [[foundation-model-fusion-speech]] — the methodology winning on CPC3 today
- [[speech-enhancement-neural-networks]] — the upstream-of-evaluation context
- [[listening-effort-evaluation]] — the unbuilt third axis CPC may yet host
- [[vcca-computational-audiology]] — the Computational Audiology Network ecosystem that hosts overlapping benchmarks

## Sources
- [Nakazawa — Frame-Aligned Fusion of Canary and WavLM (arXiv:2605.23619)](../../sources/frame-aligned-fusion-canary-wavlm-cpc3-may-2026.md) — current Clarity-anchored SOTA; the post-results-paper analysis tradition
