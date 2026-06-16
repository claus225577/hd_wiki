---
title: Xunying Liu Group (CUHK Speech)
type: entity
entity_type: research-group
created: 2026-06-16
updated: 2026-06-16
sources: [arxiv-2606-16539-elderly-asr-online-adaptation.md, arxiv-2606-16546-elderly-asr-pseudo-labeling.md]
related: [../concepts/elderly-speech-recognition.md, ../concepts/cross-lifespan-speech-models.md, ../concepts/companion-phone-speech-pipeline.md, dementiabank-pitt-dataset.md, jccocc-moca-dataset.md]
tags: [research-group, cuhk, hong-kong, xunying-liu, elderly-asr, dysarthric-speech, cantonese-asr, speaker-adaptation, interspeech-2026]
---

# Xunying Liu Group (CUHK Speech)

A long-running speech-and-language research group at **The Chinese University of Hong Kong**, led by Xunying Liu. The group's recent work concentrates on **elderly and dysarthric speech recognition**, with a deliberate **English × Cantonese** evaluation discipline anchored by their in-house JCCOCC MoCA corpus.

This entity is tracked because, on 15 June 2026, the group posted two coupled INTERSPEECH 2026 papers that together cover the inference-time and training-time halves of the elderly-ASR adaptation problem — together they form one of the strongest single-day contributions to the cross-lifespan ASR thread the wiki is tracking ([[../concepts/cross-lifespan-speech-models]]).

## Recurring Group Members (June 2026 Pair)
Both 15-June-2026 papers share a near-identical author list, suggesting a stable core team:

- **Chengxi Deng** — first author on both papers
- **Xurong Xie**
- **Shujie Hu**
- **Mengzhe Geng**
- **Jiajun Deng**
- **Youjun Chen**
- **Huimeng Wang**
- **Haoning Xu**
- **Xunying Liu** — senior author
- Plus **Tianzi Wang** (2606.16539 only) and **Guinan Li** (2606.16546 only)

## Research Threads

### 1. Elderly / dysarthric speech recognition
The dominant theme. The group treats elderly ASR not as a niche benchmark but as **the worst-case domain** that exposes the limits of adult-skewed foundation models. The pair of June 2026 papers:

- **arXiv:2606.16539** ("Decoding while Adapting") — zero-shot online speaker adaptation via cross-utterance audio-textual prompts. The text channel stabilizes speaker representations on noisy dysarthric audio.
- **arXiv:2606.16546** ("Confidence Score Guided Incremental and Speaker Adaptive Pseudo-Labeling") — high-to-low confidence curriculum plus speaker-adaptive learnable prompts for semi-supervised training on unlabeled elderly speech.

### 2. Cantonese-language ASR
The group's JCCOCC MoCA corpus is the de facto Cantonese benchmark for elderly speech. The English × Cantonese evaluation discipline ([[dementiabank-pitt-dataset]] + [[jccocc-moca-dataset]]) is unusually rigorous for the elderly-ASR sub-field, which is otherwise almost exclusively English.

### 3. Learnable prompts / adapters over frozen FM backbones
Both June 2026 papers use the **small-learnable-hook-over-frozen-FM** pattern that has become dominant across the June 2026 wave of speech-AI research (Jialu Li's age-aware adapter, Gumbel-BEARD's layer router, the room-aware dereverberation work, this group's speaker prompts). The CUHK contribution is to apply the pattern at the **speaker-conditioning axis** specifically.

## Why It Matters for Hearing AI
- **Hearing-aid wearer demographics map onto this group's research focus.** The over-65 hearing-aid customer base, especially the cognitively-impaired sub-cohort, is exactly the domain this group benchmarks against.
- **Cantonese channel matters for Asia-Pacific OEM strategy.** GN, Sonova, Phonak, Cochlear, Widex all sell into Hong Kong, Macau, and southern China markets where Cantonese is the dominant home language. A research line that publishes Cantonese elderly-ASR benchmarks is one of the few public-corpus footholds for evaluating those markets.
- **Companion-phone deployment substrate.** The audio-textual prompt mechanism transfers directly to phone-side hearing-care companion pipelines ([[../concepts/companion-phone-speech-pipeline]]) — exactly where elderly-wearer ASR substrate lives.

## Related Pages
- [[../concepts/elderly-speech-recognition]] — concept this group's recent work primarily populates
- [[../concepts/cross-lifespan-speech-models]] — the older-edge of the lifespan framing
- [[../concepts/companion-phone-speech-pipeline]] — deployment substrate
- [[dementiabank-pitt-dataset]] — English benchmark used by the group
- [[jccocc-moca-dataset]] — group's in-house Cantonese benchmark

## Sources
- [Deng et al. arXiv:2606.16539 (Jun 15 2026)](../../sources/arxiv-2606-16539-elderly-asr-online-adaptation.md) — inference-time half
- [Deng et al. arXiv:2606.16546 (Jun 15 2026)](../../sources/arxiv-2606-16546-elderly-asr-pseudo-labeling.md) — training-time half
