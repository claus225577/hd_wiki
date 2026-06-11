---
title: "G-MaP-SE: Guided Speech Enhancement via GMM-Based Prior Matching"
type: source
source_type: paper
date_published: 2026-06-07
date_ingested: 2026-06-11
authors: [Yike Zhu, Ziqian Wang, Zikai Liu, et al.]
identifier: arXiv:2606.08580
url: https://arxiv.org/abs/2606.08580
venue: arXiv (eess.AS) / Interspeech 2026 (accepted)
tags: [speech-enhancement, speaker-embedding, gmm, no-enrollment, prior-matching, hearing-aid-applicable]
---

# G-MaP-SE: Guided Speech Enhancement via GMM-Based Prior Matching

## Bibliographic
- **Authors:** Yike Zhu, Ziqian Wang, Zikai Liu, and five co-authors
- **Venue:** arXiv eess.AS submitted 7 Jun 2026; accepted to Interspeech 2026
- **ID:** arXiv:2606.08580
- **URL:** https://arxiv.org/abs/2606.08580

## What
G-MaP-SE addresses a long-running fragility in target-speaker speech enhancement: most speaker-embedding-based SE systems either need a clean enrollment utterance (impractical in real deployments) or extract the embedding from noisy speech (which collapses under domain shift). The paper fits a Gaussian Mixture Model over clean-speech speaker embeddings, then at inference snaps the noisy embedding to its nearest GMM mode and injects that "matched" embedding into a TF-domain SE backbone through a lightweight gated fusion module. On VoiceBank+DEMAND and DNS Challenge 2020, prior matching consistently beats noisy conditioning and closes most of the gap to the oracle clean-conditioning upper bound, without any enrollment audio at test time.

## Why It Matters
Hearing aids that want to lock onto a partner voice or a "voice-of-interest" face exactly this problem: clean enrollment at fitting time is impractical, and noisy embeddings extracted in the cafe are exactly when the system fails. GMM prior matching is a cheap, training-free-at-inference trick that decouples the embedding quality from the test-time SNR — a useful primitive for the "user-controlled on-demand AI clarity boost" pattern. Interspeech 2026 acceptance gives it OEM-track credibility.

## Context
- Adds to the body of work on prior-conditioned / personalized SE — relevant to the user-controlled on-demand pattern Phonak and Starkey are both pushing.
- Architecturally orthogonal to HALO (frame-rate halving) and DBHN-Net (branch-fusion): could be stacked into the same backbone.

## Used In
- [[wiki/concepts/speech-enhancement-neural-networks.md]]
- [[wiki/concepts/user-controlled-on-demand-ai-hearing-aids.md]]
- [[wiki/concepts/probabilistic-generative-models-hearing-ai.md]]
