---
title: DementiaBank Pitt Corpus
type: entity
entity_type: dataset
created: 2026-06-16
updated: 2026-06-16
sources: [arxiv-2606-16539-elderly-asr-online-adaptation.md, arxiv-2606-16546-elderly-asr-pseudo-labeling.md]
related: [../concepts/elderly-speech-recognition.md, ../concepts/cross-lifespan-speech-models.md, ../concepts/hearing-loss-dementia-link.md, ../concepts/digital-phenotyping-cognitive-decline.md, xunying-liu-cuhk-speech-group.md, jccocc-moca-dataset.md]
tags: [dataset, dementiabank, pitt-corpus, english, elderly-speech, dementia, dysarthric-speech, cookie-theft, asr-benchmark, clinical-corpus]
---

# DementiaBank Pitt Corpus

DementiaBank's Pittsburgh corpus ("Pitt") is the canonical reference dataset for English-language elderly and dementia speech recognition. It contains audio of clinical interviews — most notably the **Cookie Theft picture description** task — collected from older speakers across cognitive-status bands (healthy, mild cognitive impairment, Alzheimer's-type dementia, vascular dementia).

This wiki tracks it as the **dataset entity** that lives at the intersection of elderly speech recognition, hearing-loss × dementia screening, and the cross-lifespan ASR generalization problem.

## Why It Matters for Hearing AI

### 1. Reference benchmark for the elderly-edge of the lifespan failure mode
Adult-skewed speech foundation models degrade hardest on the youngest and oldest speakers ([[../concepts/cross-lifespan-speech-models]]). DementiaBank Pitt is the standard public-corpus measurement of how badly they degrade on the older edge. Any OEM that ships a hearing-care companion-phone ASR substrate ([[../concepts/companion-phone-speech-pipeline]]) should track its WER on this corpus.

### 2. Adjacent to the hearing-loss × dementia comorbidity
The hearing-loss / cognitive-decline link ([[../concepts/hearing-loss-dementia-link]]) means the cohort that hearing-aid OEMs disproportionately see overlaps with the DementiaBank-Pitt cohort. The corpus is therefore not a niche academic dataset — it samples a population the industry actually sells to.

### 3. Substrate for speech-based dementia screening
Lexical-density, semantic-fluency, pause distribution, and discourse-coherence features derived from Cookie Theft narratives are the input layer of speech-based cognitive screening pipelines ([[../concepts/digital-phenotyping-cognitive-decline]]). ASR errors on DementiaBank Pitt propagate directly into those features.

## Key Tasks Evaluated
- **ASR / WER reduction** — primary task for the June 2026 CUHK papers.
- **Diagnosis classification** — Alzheimer's-vs-control classification, separate research line.
- **Linguistic feature extraction** — semantic / syntactic / pause features as input to cognitive-screening pipelines.

## June 2026 Benchmark Activity
Two June 2026 papers from the [[xunying-liu-cuhk-speech-group]] use DementiaBank Pitt as the English half of an English × Cantonese elderly-ASR evaluation:

| Paper | Mechanism | Pitt result vs baseline |
|---|---|---|
| Deng et al., arXiv:2606.16539 | Inference-time audio-textual prompt | −0.61% absolute WER |
| Deng et al., arXiv:2606.16546 | Training-time confidence-curriculum + learnable prompt | −1.45% absolute WER (6.21% relative) |

## Related Pages
- [[../concepts/elderly-speech-recognition]] — primary concept
- [[../concepts/cross-lifespan-speech-models]] — parent framing
- [[../concepts/hearing-loss-dementia-link]] — cohort overlap
- [[../concepts/digital-phenotyping-cognitive-decline]] — adjacent screening pipeline
- [[jccocc-moca-dataset]] — Cantonese counterpart used in the same June 2026 papers
- [[xunying-liu-cuhk-speech-group]] — primary research group benchmarking on this corpus

## Sources
- [Deng et al. arXiv:2606.16539 (Jun 15 2026)](../../sources/arxiv-2606-16539-elderly-asr-online-adaptation.md)
- [Deng et al. arXiv:2606.16546 (Jun 15 2026)](../../sources/arxiv-2606-16546-elderly-asr-pseudo-labeling.md)
