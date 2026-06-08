---
title: A Comparison of Generative and Discriminative Methods for Speech Enhancement (Saha Shetu, Habets, Brendel)
type: source
source_type: arxiv-paper
arxiv_id: 2606.02913
authors: [Shrishti Saha Shetu, Emanuël A. P. Habets, Andreas Brendel]
affiliations: [Fraunhofer IIS, International Audio Laboratories Erlangen]
published: 2026-06-03
ingested: 2026-06-08
url: https://arxiv.org/abs/2606.02913
tags: [speech-enhancement, generative-models, diffusion, discriminative-models, out-of-distribution, hallucination, evaluation]
---

# A Comparison of Generative and Discriminative Methods for Speech Enhancement

**arXiv:2606.02913** — Saha Shetu, Habets, Brendel (Fraunhofer IIS / International Audio Laboratories Erlangen), 3 Jun 2026.

## What

A controlled head-to-head between diffusion-style generative speech enhancement and standard discriminative DNN speech enhancement, testing both paradigms under the same conditions on:

- Stationary intrusive noise (in-distribution).
- Non-stationary noise (cocktail-party-like).
- Unseen reverberation (out-of-distribution generalization).
- Robustness to artifacts and content-warping ("hallucination") behavior.

## Key Findings

- **Discriminative wins on stationary intrusive noise** — established discriminative SE remains the strongest paradigm when the noise distribution matches training.
- **Generative wins on non-stationary noise and unseen reverberation** — diffusion-style generative SE generalizes better to OOD acoustic conditions.
- **Generative cost: content-warping artifacts** — generative methods occasionally produce plausible-but-incorrect content under uncertainty. The frequency and severity of such artifacts is the dominant safety concern for clinical deployment.
- The findings argue against treating the two paradigms as interchangeable; the right choice is acoustic-condition-dependent.

## Why It Matters

- **Sober baseline alongside SB-RF.** Last week's SB-RF paper (arXiv:2606.05575) made the one-step generative SE pitch — proves the *latency* problem is tractable. This paper makes the complementary point: the *content-fidelity* problem is not yet solved. The two together set up a realistic 2026-Q3 product question — when is the artifact rate low enough to ship?
- **Establishes the comparison axes.** OOD reverberation and non-stationary noise are exactly the conditions a hearing aid encounters most often. Generative wins on the conditions that matter clinically — if the artifact problem can be controlled.
- **Hallucination is now a measurable property of SE, not just LM-based SE.** Wang et al.'s L3-SE work in May 2026 documented linguistic hallucination in LM-based SE. This Fraunhofer paper extends the concept to diffusion-style generative SE.

## Carry-Forward Flags

- A paper that ships an explicit *artifact-rate metric* (analogous to WER for ASR) alongside PESQ / HASPI / CEC3 would close the loop. Watch for it.
- The hybrid-architecture answer (generative-when-OOD, discriminative-when-in-distribution, decided by an on-device scene classifier) is the obvious next product move.

## Related Wiki Pages

- [[../wiki/concepts/probabilistic-generative-models-hearing-ai.md]] — Generative paradigm contender; this paper benchmarks the broader generative-vs-discriminative question.
- [[../wiki/concepts/speech-enhancement-neural-networks.md]] — Core concept page.
- [[../wiki/concepts/linguistic-hallucination-speech-enhancement.md]] — Related failure mode in LM-based SE.
- [[../wiki/concepts/llm-based-speech-enhancement.md]] — Adjacent generative paradigm.
