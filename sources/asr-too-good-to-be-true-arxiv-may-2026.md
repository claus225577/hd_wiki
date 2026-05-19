---
title: "Too Good to Be True: A Study on Modern Automatic Speech Recognition for the Evaluation of Speech Enhancement"
authors: [Danilo de Oliveira, Tal Peer, Timo Gerkmann]
affiliation: undisclosed in abstract (speech-enhancement research group; Gerkmann is a long-standing SE/audio researcher at Universität Hamburg)
date: 2026-05-12
arxiv_id: "2605.12107"
url: https://arxiv.org/abs/2605.12107
arxiv_listing: https://arxiv.org/list/eess.AS/2026-05
type: research-paper
source_type: arxiv-preprint
ingested: 2026-05-19
tags: [speech-enhancement, asr, wer-evaluation, evaluation-metrics, generative-se, transducer-asr, embedded-language-models, hearing-aids, interspeech-2026]
---

# Too Good to Be True — Modern ASR for SE Evaluation (de Oliveira, Peer & Gerkmann, May 2026)

## Bibliographic
- **Authors:** Danilo de Oliveira, Tal Peer, Timo Gerkmann
- **Submitted:** 12 May 2026 (arXiv:2605.12107, eess.AS)
- **Venue intent:** submitted to Interspeech 2026 based on cohort and date
- **URL:** https://arxiv.org/abs/2605.12107

## Core Claim

The community's habit of using automatic speech recognition (ASR) as the objective backstop for evaluating speech enhancement (SE) — measuring SE quality as the word error rate (WER) of an ASR run on enhanced audio — is methodologically broken. Modern ASR models with large-scale noisy training and embedded language models do correlate **more** with human WER than simpler systems, **but** that improvement comes precisely from properties that disqualify them as an acoustic-faithful yardstick: their noise robustness and contextual inference can transcribe correctly through residual acoustic damage in the enhanced signal.

In effect, a modern ASR's WER on enhanced audio under-reports SE failure exactly when the SE has failed.

## Method

- A listening experiment comparing how multiple modern ASR architectures correlate with human WER on enhanced speech.
- ASR systems vary by: scale of noisy training data, presence vs absence of embedded language modeling, architecture (transducer, attention-based, etc.).
- Human WER established via formal listening tests on the same enhanced utterances.
- Correlations between ASR-WER and human-WER computed per system.

## Key Findings

1. **Best correlator with humans:** a transducer-style ASR with large-scale noisy training and embedded language modeling.
2. **Caveat:** the same properties that drive the strong correlation (noise robustness, language-prior contextualization) make these systems "uninformative to an acoustics-focused evaluation."
3. **Implication:** WER scores depend heavily on the ASR choice and text-normalization pipeline. The implicit assumption that "newer ASR = better SE evaluator" is wrong.

## Hearing-Aid Relevance

The abstract does not name hearing aids directly, but the implication is direct and material:

- Hearing aids ship a signal to a human auditory system, not to an ASR system. The right metric is acoustic faithfulness to ground truth, not contextual transcription accuracy.
- The hearing-impaired listener is even more sensitive to residual acoustic damage than a normal-hearing listener — exactly the damage ASR-WER masks.
- This is the third paper in twelve days arguing the current SE evaluation stack is structurally too forgiving: paired with **L3-SE (Wang et al., May 9)** on linguistic hallucination in LM-based SE, and **Behringer et al. (May 5)** on listening-effort separating systems that intelligibility scores call equivalent.

## Field Recommendation (Reading)

- Pair every ASR-based SE eval with formal listener panels.
- Treat ASR-WER as a coarse upper bound on SE quality, not as a substitute for human evaluation.
- Acoustic-faithfulness metrics that are independent of ASR (and not trained to generate plausible text) need to be built. None are off the shelf.

## Cross-References

- `linguistic-hallucination-speech-enhancement.md` — sibling failure-mode page, language model in the SE itself
- `listening-effort-evaluation.md` — sibling evaluation-metric gap
- `speech-enhancement-neural-networks.md` — parent concept
- `l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md` — sibling source
- `codec-intelligibility-se-behringer-arxiv-2026.md` — sibling source
