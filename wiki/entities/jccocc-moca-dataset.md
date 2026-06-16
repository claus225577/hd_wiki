---
title: JCCOCC MoCA Corpus
type: entity
entity_type: dataset
created: 2026-06-16
updated: 2026-06-16
sources: [arxiv-2606-16539-elderly-asr-online-adaptation.md, arxiv-2606-16546-elderly-asr-pseudo-labeling.md]
related: [../concepts/elderly-speech-recognition.md, ../concepts/cross-lifespan-speech-models.md, ../concepts/hearing-loss-dementia-link.md, ../concepts/digital-phenotyping-cognitive-decline.md, xunying-liu-cuhk-speech-group.md, dementiabank-pitt-dataset.md]
tags: [dataset, jccocc-moca, cantonese, tonal-language, elderly-speech, dementia, moca, montreal-cognitive-assessment, asr-benchmark, clinical-corpus, cuhk]
---

# JCCOCC MoCA Corpus

JCCOCC MoCA is a **Cantonese-language** corpus of Montreal Cognitive Assessment (MoCA) recordings, built and used at the Chinese University of Hong Kong. It is the de facto benchmark for **non-English elderly / dementia speech recognition** within the CUHK speech research line.

This wiki tracks it as the **dataset entity** that paired with [[dementiabank-pitt-dataset]] gives the elderly-ASR field an English × Cantonese cross-lingual benchmark — important because almost all elderly-ASR literature is English-only.

## Why It Matters for Hearing AI

### 1. Non-English elderly benchmark
The cross-lifespan failure mode of adult-skewed foundation models ([[../concepts/cross-lifespan-speech-models]]) has historically been measured almost exclusively in English. JCCOCC MoCA provides a **tonal-language, non-Indo-European** measurement channel. Generalization claims about elderly-ASR adaptation methods need to clear both the English (DementiaBank Pitt) and Cantonese (JCCOCC MoCA) benchmarks before they can be called language-agnostic.

### 2. CER, not WER
Because Chinese is character-based, JCCOCC MoCA results are reported in **CER (character error rate)** rather than WER. CER captures errors at a finer granularity than WER (no word-segmentation ambiguity), which matters for the small-delta gains that elderly-ASR adaptation methods typically achieve.

### 3. Tonal-language ASR for cognitive screening
Tonal-language dementia screening pipelines that depend on lexical / prosodic features have a different feature inventory than English pipelines (tone-stability, tone-merging-rate). The same ASR substrate evaluated on JCCOCC MoCA is the substrate those screening pipelines will run on.

## June 2026 Benchmark Activity
Two June 2026 papers from the [[xunying-liu-cuhk-speech-group]] use JCCOCC MoCA as the Cantonese half of an English × Cantonese elderly-ASR evaluation:

| Paper | Mechanism | JCCOCC MoCA result vs baseline |
|---|---|---|
| Deng et al., arXiv:2606.16539 | Inference-time audio-textual prompt | −1.22% absolute CER |
| Deng et al., arXiv:2606.16546 | Training-time confidence-curriculum + learnable prompt | −2.27% absolute CER (6.98% relative) |

The Cantonese gains are larger in absolute terms than the English Pitt gains in both papers — consistent with the prior that non-English elderly speech is even further from the foundation-model pre-training distribution and therefore has more headroom for adaptation.

## Related Pages
- [[../concepts/elderly-speech-recognition]] — primary concept
- [[../concepts/cross-lifespan-speech-models]] — parent framing
- [[../concepts/hearing-loss-dementia-link]] — cohort overlap
- [[../concepts/digital-phenotyping-cognitive-decline]] — adjacent screening pipeline
- [[dementiabank-pitt-dataset]] — English counterpart used in the same June 2026 papers
- [[xunying-liu-cuhk-speech-group]] — corpus builder and primary research group

## Sources
- [Deng et al. arXiv:2606.16539 (Jun 15 2026)](../../sources/arxiv-2606-16539-elderly-asr-online-adaptation.md)
- [Deng et al. arXiv:2606.16546 (Jun 15 2026)](../../sources/arxiv-2606-16546-elderly-asr-pseudo-labeling.md)
