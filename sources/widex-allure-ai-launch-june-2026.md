---
title: "Widex Allure AI RIC — Launch Goes Live (June 1, 2026) + L-RNN Architecture Detail"
source_type: product-launch-followup
publisher: Widex (WS Audiology)
date: 2026-06-01
url: https://hearinghealthmatters.org/hearing-news-watch/2026/dual-processor-widex-allure-ai/
also_covered:
  - https://hearingreview.com/hearing-products/hearing-aids/bte/natural-sound-meets-ai-widex-announces-allure-ai-ric-hearing-aid-with-clarity-boost-compass-cloud-2-0
  - https://www.hearingtracker.com/news/widex-launches-allure-ai-ric-with-clarity-boost-and-compass-cloud-2-0
  - https://hearinghealthmatters.org/thisweek/2026/allure-ai-hearing-aid-review/
authors: [Widex, WS Audiology, Hearing Health & Technology Matters (coverage)]
type: product-launch-followup
tags: [widex, ws-audiology, allure-ai, ric, clarity-boost, on-demand-ai, ai-co-processor, linear-recurrent-neural-network, l-rnn, state-space-models, ssm, dnn-architectures, dual-chip, hearing-aids]
ingested: 2026-06-09
---

# Widex Allure AI RIC — Launch Goes Live (June 1, 2026)

## Summary
The Widex **Allure AI RIC with Clarity Boost** went live in **five initial markets on June 1, 2026**, executing the launch announced May 20, 2026. The follow-on coverage from the first week after launch adds one materially new piece of technical information that was not in the announcement coverage: the AI co-processor runs a **third-generation "Linear Recurrent Neural Network" (L-RNN)** specifically designed for audio.

The product framing remains "natural sound is the default; AI is engaged via the Clarity Boost button when the wearer chooses." Full-scale launch in remaining markets including the US is scheduled for **November 1, 2026**.

## What's New vs the May 20 Announcement
- **Launch executed.** Five-market June 1, 2026 rollout confirmed in industry trade press coverage on or near launch day.
- **DNN architecture disclosed at the family level.** Widex AI team publicly described the architecture as a **"third generation DNN, a Linear Recurrent Neural Network (L-RNN), specifically built for sound."** Quoted rationale: "It works with the temporal aspect of sound and can keep memory of what happened before. That allows balancing noise reduction, power consumption, and sound quality in a way that other AI architectures are not able to do."
- **Dual-chip framing crystallised in coverage.** The product is now consistently described as a "dual-chip" or "two-chip" hearing aid — existing Allure DSP path + the new dedicated AI co-processor — with the AI co-processor activated only when Clarity Boost is engaged.

## Headline Facts (post-launch coverage)
- **Launch date (5 markets):** June 1, 2026.
- **Launch date (full incl. US):** November 1, 2026.
- **Chip architecture:** Two-chip platform — Allure DSP for natural sound + dedicated AI co-processor for the L-RNN AI path.
- **DNN family:** Linear Recurrent Neural Network (L-RNN), third generation, audio-specific.
- **AI activation:** User-pressed Clarity Boost button.
- **Performance claim (when engaged):** Up to 6 dB higher output SNR vs competitor AI hearing aids.
- **Battery:** 32 h total runtime including up to 6 h AI-on use or streaming.
- **Connectivity:** MFi, ASHA, LE Audio, telecoil, hands-free.
- **Companion fitting:** Widex Compass Cloud 2.0 (announced May 20; live at launch).

## Why the L-RNN Detail Matters
The Linear Recurrent Neural Network family is structurally close to the **State Space Model (SSM) lineage** (S4, Mamba, RWKV-7, Hyena, etc.) that the audio ML community has been quietly converging on since 2024. The defining properties relative to CNN / Transformer baselines:

- **Linear recurrence in time** → cheap streaming inference, constant per-step compute, no growing KV cache.
- **State carries memory** → temporal context without attention over a window.
- **Maps well to power-constrained DSP / NPU silicon** → SSM-family architectures have been the dominant choice in recent on-chip audio ML demos (e.g., Applied Brain Research, Liquid AI Time Constant Networks).

WSA picking an L-RNN over a CNN or transformer for the audio-specific co-processor is therefore aligned with the broader 2026 chip-level convergence — not an idiosyncratic Widex choice. It is also a signal that **linear-recurrent state spaces are the right primitive for streaming audio at hearing-aid power budgets** in WSA's R&D view.

## Strategic / Data-Science Significance (Updates to May 20 Source)
- **Confirms the counter-positioning** against the always-on AI race led by Phonak Sphere Infinio, ReSound Vivia, Oticon Zeal/Intent, and Starkey Omega — the product is now actually in market, not just announced.
- The **button-press telemetry as labeled training signal** thesis (see [[../wiki/concepts/user-controlled-on-demand-ai-hearing-aids]]) is now testable in the real world from June 1 onward in the five launch markets.
- The L-RNN architecture choice puts WSA structurally in the same on-chip-streaming-audio-via-SSMs camp as the rest of the 2026 chip-level audio ML field. Cross-references the convergence noted in the June 4 Olalere et al. FPGA latency benchmark (which named memory bandwidth as the binding constraint — exactly the constraint SSMs are designed to relax).

## Limits / Open Questions
- The exact L-RNN variant Widex uses (S4-style? Mamba-derived? proprietary?) is not disclosed.
- Real-world Clarity Boost engagement rates in the launch markets are not yet published.
- Whether button-press telemetry is being surfaced into Compass Cloud 2.0 as a personalization signal is still not publicly confirmed.

## Related Wiki Pages
- [User-Controlled On-Demand AI in Hearing Aids](../wiki/concepts/user-controlled-on-demand-ai-hearing-aids.md)
- [DNN Architectures for Hearing Aids](../wiki/concepts/dnn-architectures-hearing-aids.md)
- [WS Audiology / Signia](../wiki/entities/ws-audiology-signia.md)
- [Closed-Loop Data Flywheel](../wiki/concepts/closed-loop-data-flywheel.md)

## Related Sources
- [widex-allure-ai-may-2026.md](widex-allure-ai-may-2026.md) — Original May 20 announcement; this is the launch follow-on
