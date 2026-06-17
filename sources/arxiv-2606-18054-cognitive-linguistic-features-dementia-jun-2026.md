---
title: "AI-based Cognitive-linguistic Features for Dementia Assessment in Picture Description"
type: source
source_type: arxiv-paper
arxiv_id: 2606.18054
authors: [Lingfeng Xu, Prad Kadambi, Samuel Goldinger, Visar Berisha, Kimberly D. Mueller, Julie Liss]
affiliations: [Arizona State University (Berisha / Liss group, likely); University of Wisconsin (Mueller, likely)]
date_published: 2026-06-16
ingested: 2026-06-17
url: https://arxiv.org/abs/2606.18054
tags: [dementia, cognitive-linguistic, picture-description, cookie-theft, adress, llm-clinical-evaluation, claude-3-5-sonnet, explainability, dementiabank, severity-scoring, jpad-style-construct]
---

# AI-based Cognitive-linguistic Features for Dementia Assessment (Xu et al., June 2026)

## Bibliographic
- **Authors:** Lingfeng Xu, Prad Kadambi, Samuel Goldinger, Visar Berisha, Kimberly D. Mueller, Julie Liss
- **Posted:** 16 June 2026 (arXiv:2606.18054)
- **URL:** https://arxiv.org/abs/2606.18054

## Problem
Cookie Theft picture description has been the canonical clinical task for connected-speech dementia assessment for fifty years. The problem with automating it at scale is that the historically useful features (lexical density, semantic-fluency proxies, mean-length-of-utterance) are statistical surrogates for the constructs a clinician actually reads — discourse coherence, information-unit coverage, semantic specificity, syntactic complexity, error patterns. The constructs are what the diagnosis hangs on; the statistical surrogates were what the NLP stack could measure.

## Contribution
Xu et al. define **seven explicit cognitive-linguistic constructs** for the Cookie Theft task and use **Claude 3.5 Sonnet** to generate, for each construct, **both** a severity score **and** a free-text explanation grounded in the transcript.

The framing is: the LLM is not used as a black-box classifier. It is used as a **clinician-style scoring instrument** that emits both the score and the justification. The justification is the auditable channel that lets a clinician decide whether to trust the score.

## Headline Numbers
- **85% accuracy** on the **ADReSS** dataset (the standard public benchmark for AD-vs-control via Cookie Theft).
- **3.99 / 5 expert agreement** on the generated **explanations** — i.e. expert reviewers, blind to the LLM, rated the explanations as essentially clinician-grade on a 5-point scale.

The 3.99/5 number is the more important number. Accuracy on ADReSS is a leaderboard metric. Expert-judged explanation quality is the **auditability and trust** metric, which is what determines whether the pipeline can sit upstream of a clinical decision.

## Why It Matters for Hearing AI

### 1. LLM-as-rubric-scorer pattern for connected speech
The construct-driven scoring rubric (seven explicit constructs, score + explanation per construct) is the same template a hearing-care LLM companion would need to deploy for any longitudinal speech-derived clinical signal — not just dementia. It generalises to depression assessment, listening-effort self-report parsing, intelligibility self-rating, etc.

### 2. ADReSS is built on DementiaBank Pitt Cookie Theft
The dataset chain is: DementiaBank Pitt corpus → ADReSS challenge subset → this paper. The hearing-aid ASR stack (see [[../wiki/concepts/elderly-speech-recognition.md]]) is already being benchmarked on Pitt for the **transcription** step. Xu et al. operate the **scoring** step on the same substrate. Together they define the audio-to-score pipeline end to end.

### 3. The clinician-style explanation as the regulatory surface
Explainability is not optional for a clinical-grade screening tool. A construct-grounded explanation that a clinician scores 3.99/5 is the kind of artefact the FDA Predetermined Change Control Plan (PCCP) framework can be written around — the model can update, the constructs and explanation rubric stay anchored.

## Limits / Open Questions
- ADReSS is small, US-English, and clinic-recruited. Generalisation to in-the-wild ambient elderly speech (the actual hearing-aid telemetry case) is open.
- The 85% accuracy number is at-or-near recent ADReSS leaderboard ceilings; whether the explanation channel **trades off** raw accuracy is not separately reported.
- Claude 3.5 Sonnet is a cloud-only model. The on-device or hybrid version of the rubric scorer — what runs inside a hearing-care companion app at HA latency / privacy budgets — is unbuilt.
- Cookie Theft is one task. The construct stack would need to be re-defined for every other connected-speech elicitation (free conversation, reading passage, verbal-fluency tasks).

## Related Wiki Pages
- [[../wiki/concepts/elderly-speech-recognition.md]] — the transcription substrate this scoring layer sits on top of
- [[../wiki/concepts/digital-phenotyping-cognitive-decline.md]] — the cognitive-screening pipeline this fits inside
- [[../wiki/concepts/hearing-loss-dementia-link.md]] — clinical context
- [[../wiki/entities/dementiabank-pitt-dataset.md]] — upstream dataset
- [[../wiki/concepts/medical-domain-edge-llms.md]] — on-device deployment surface

## Related Sources
- [LLM Dementia / Depression Assessment from Clinical Interviews (Braun et al., Jun 2026)](arxiv-2606-18019-llm-dementia-depression-clinical-interviews-jun-2026.md) — same week, history-taking interview substrate, open-weights LLMs
- [Cross-Lingual Alzheimer Detection (Girish et al., Jun 2026)](arxiv-2606-17254-cross-lingual-alzheimer-detection-jun-2026.md) — same week, cross-lingual axis
- [Elderly-ASR Online Adaptation (Deng et al., Jun 2026)](arxiv-2606-16539-elderly-asr-online-adaptation.md) — upstream transcription layer
- [Elderly-ASR Pseudo-Labeling (Deng et al., Jun 2026)](arxiv-2606-16546-elderly-asr-pseudo-labeling.md) — upstream transcription layer
