---
title: "Can Large Audio Language Models Ignore Multilingual Distractors? An Evaluation of Their Selective Auditory Attention Capabilities (MUSA Benchmark)"
date: 2026-05-17
url: https://arxiv.org/abs/2605.17225
type: arxiv-paper
tags: [lalm, selective-auditory-attention, cocktail-party, multilingual, benchmark, speech-foundation-models, evaluation, hearing-aid-ai]
authors: ["Heejoon Koo"]
arxiv_id: 2605.17225
---

## Key Facts

- Paper introduces MUSA, a cocktail-party-inspired *multilingual* benchmark for source-grounded spoken-language understanding and reasoning in Large Audio Language Models (LALMs).
- Setup: pair an English target dialogue with a semantically plausible distractor in English, Spanish, Korean, or Chinese.
- Evaluation regimes:
  - Single (target only — baseline)
  - Source-separation two-stage pipeline
  - End-to-end cocktail-party (LALM hears mixture and is asked about the target)
- Controlled SNR sweeps across all conditions.
- Headline finding: strong single-source performance does NOT predict cocktail-party robustness. As SNR worsens, accuracy degrades sharply.
- Dominant error class: "distractor-grounded source confusion" — LALM confidently grounds the answer in the *wrong language*, not background noise per se.
- Implication for production deployment: LALMs that benchmark well on monolithic ASR or single-source QA can fail catastrophically in realistic multilingual scenes.

## Why It Matters for Hearing Aids

The hearing-aid AI roadmap quietly assumes selective auditory attention is solved by scaling speech foundation models. MUSA shows it isn't — and the failure mode is *worse* than acoustic SNR collapse: the model confidently picks the wrong language and stays there.

Three concrete implications:
1. Many hearing aid wearers live in multilingual environments (US Latino communities, UK, Singapore, Hong Kong, EU border regions, expat households).
2. The hearing-aid cocktail party is *harder* than the benchmark — lower SNRs, faster speaker turn-taking, older listeners.
3. Every team fine-tuning Whisper / Voxtral / Qwen3-ASR / QVAC MedPsy for a hearing-care feature inherits this failure mode by default.

Pair with:
- Choudhari/Mesgarani (Nature Neuroscience, 11 May 2026) — brain-controlled hearing showed neural attention decoding works on humans via intracranial ECoG. MUSA is the mirror: software-side selective attention isn't there yet, and we now have a benchmark to track when it gets there.
- L3-SE linguistic hallucination (arXiv:2605.08608, May 9 2026) — a related but distinct failure mode in LM-based SE.
- Cross-lifespan diarization (arXiv:2604.05201, May 19 2026) — age-domain shift is the *other* unsolved evaluation gap.

Together: three structural cracks in the hearing-aid speech-enhancement evaluation stack in the same fortnight (May 8–19, 2026).
