---
title: Cross-Lifespan Speech Models
type: concept
created: 2026-05-21
updated: 2026-06-16
sources: [cross-lifespan-diarization-usc-may-2026.md, oticon-play-si-pediatric-launch-april-2026.md, oticon-play-si-hearingreview-april-2026.md, pediatric-softband-bcd-database-frontiers-may-2026.md, qvac-medpsy-edge-medical-llm-may-2026.md, arxiv-2606-05440-age-aware-adapter-children-asr-jun-2026.md, arxiv-2606-16539-elderly-asr-online-adaptation.md, arxiv-2606-16546-elderly-asr-pseudo-labeling.md]
related: [speech-enhancement-neural-networks.md, on-device-ml-hearing-aids.md, medical-domain-edge-llms.md, small-language-models-edge-ai.md, companion-phone-speech-pipeline.md, ../entities/demant-oticon.md, longitudinal-hearing-phenotyping.md, ../entities/vcca-computational-audiology.md, dnn-in-hearing-aids.md, elderly-speech-recognition.md, ../entities/dementiabank-pitt-dataset.md, ../entities/jccocc-moca-dataset.md, ../entities/xunying-liu-cuhk-speech-group.md]
tags: [speech-foundation-models, lifespan, pediatric-speech, older-adult-speech, age-distribution-shift, domain-adaptation, speaker-diarization, training-data-moat, age-conditioned-adapters, hearing-aids, whisper, voxtral, qwen3-asr]
---

# Cross-Lifespan Speech Models

The age-domain-shift problem in speech foundation models: models pre-trained on adult-skewed corpora degrade predictably at the edges of the human lifespan — children and older adults — for downstream tasks including speaker diarization, ASR, and (by extension) every hearing-aid task that consumes those representations.

This page treats the problem as a **training-distribution moat** question for hearing-aid manufacturers and a **safety-relevant generalization gap** for any hearing-aid pipeline that depends on foundation-model features.

## The Seed Result

**Xu, Feng & Narayanan (USC, May 19, 2026; arXiv:2604.05201).** "Exploring Speech Foundation Models for Speaker Diarization Across Lifespan." End-to-end neural diarization built on speech foundation models, evaluated across children, adults, and older adults.

Three regimes tested:
- **Zero-shot cross-age inference** — train on one band, test on another.
- **Joint multi-age training** — single model over the full lifespan.
- **Domain-specific adaptation** — targeted adaptation to the age band of interest.

Headline finding: foundation models trained on adult-skewed corpora **fail predictably at the edges of the lifespan**. Domain adaptation closes most of the gap.

See [cross-lifespan diarization source](../../sources/cross-lifespan-diarization-usc-may-2026.md).

## Why This Matters for Hearing Aids

### 1. The Customer Base Is at the Older Edge of the Lifespan
The hearing-aid customer base is over-65-weighted by construction. The foundation-model substrates that the field is currently fine-tuning on — Whisper, Voxtral, Qwen3-ASR, QVAC MedPsy — were pre-trained on corpora whose age distribution **does not match the customer base**. The structural gap is largest exactly where the product is sold.

### 2. Pediatric Platforms Are Now Shipping at Scale
April 2026 brought **Oticon Play SI**, the first pediatric hearing aid with 4D sensors + LE Audio + Auracast and "second-generation AI sound processing" on the Sirius platform. The Boys Town study reported 50% improved sentence recognition in noise for teenagers and 77% reduced listening difficulty. May 2026 brought a **n=5,490 pediatric softband BCD database** expanding candidacy evidence.

Pediatric AI hearing aids are no longer hypothetical. Any pediatric DNN that consumes upstream foundation-model features inherits the foundation model's pediatric-speech limitations.

See [[../entities/demant-oticon]] for Play SI details.

### 3. Diarization Is Foundational for Downstream HA Tasks
Hearing aids increasingly run speaker-aware pipelines:
- **Target speaker extraction** (Hsu et al. 2026) at sub-5 ms causal latency depends on speaker embeddings.
- **Auracast routing** in multi-source venues will benefit from speaker-identity awareness.
- **Conversation tracking** for care-partner dyads (see [[care-partner-dyad-models]]) is diarization-shaped.
- **Scene classification** at the multi-talker edge is increasingly speaker-aware.

Diarization errors at the lifespan edges propagate downstream into every one of these.

### 4. All Major Foundation Models Inherit the Same Bias
| Foundation model | Pre-training corpus | Age distribution |
|-----|-----|-----|
| Whisper | Web-scraped audio + transcripts | Adult-skewed |
| Voxtral | Mistral edge-native speech model | Adult-skewed |
| Qwen3-ASR | Multilingual ASR corpus | Adult-skewed |
| QVAC MedPsy | Text-only medical Q&A (no audio) | — |

There is no current commercial foundation-model substrate with explicitly lifespan-balanced pre-training.

## A New Dimension of Training-Data Moat

The wiki has previously framed the OEM training-data moat as a function of:
- **Acoustic-scene diversity** (12M–22M sound scenes; see [[dnn-in-hearing-aids]]).
- **Audiogram + telemetry + fitting-outcome corpora** as a candidate pre-training corpus (see [[../syntheses/pretraining-corpus-as-moat-hearing-ai]]).

The USC paper opens a third axis: **lifespan-stratified speech corpora and age-conditioned adapters**. The relevant differentiating assets become:

- Pediatric speech corpora at scale — much harder to collect than adult speech (consent, IRB, ethics).
- Older-adult speech corpora that are not entangled with hearing-loss artefacts.
- Age-conditioned adapter heads on top of shared foundation backbones — a low-parameter personalization layer that does not require retraining the foundation model. **Jialu Li (arXiv:2606.05440, 3 Jun 2026)** is the first published instance of this approach for children's ASR specifically: per-age adapter modules with router-based selection at inference, ground-truth routing closes ~3% of WER (12.6→12.3 overall, 18.4→17.6 macro). Predicted-age routing tracks ground-truth — the method works without exact age metadata. Hard discrete age routing outperforms continuous FiLM conditioning, suggesting the age-band structure is more informative than the continuous scalar.

The OEMs whose customer-acquisition funnels include both pediatric (Phonak Sky, Oticon Play SI) and adult/older-adult platforms are positioned to assemble lifespan-stratified corpora that pure-research labs and consumer-audio companies cannot replicate.

## Bracketing the Lifespan — June 2026 Two-Sided Closure

The age-axis pattern has now been demonstrated at both ends of the lifespan within twelve days, both using a **small learnable conditioning hook over a frozen / mostly-frozen foundation backbone**:

| Lifespan edge | Paper | Posted | Routing variable | Hook type | Headline gain |
|---|---|---|---|---|---|
| Pediatric (3–12+) | Jialu Li, arXiv:2606.05440 | Jun 3 2026 | Age band (ground-truth or estimated) | Per-age-band adapter | 12.6→12.3% WER overall, 18.4→17.6% macro |
| Elderly (≥65, dementia cohort) | Deng et al. arXiv:2606.16539 | Jun 15 2026 | Speaker identity (online, no enrollment) | Cross-utterance audio-textual prompt | −0.61% abs WER (English), −1.22% abs CER (Cantonese); 9.83× RTF speedup |
| Elderly (semi-supervised training) | Deng et al. arXiv:2606.16546 | Jun 15 2026 | Speaker identity + confidence rank | Learnable per-speaker prompt + curriculum | −1.45% abs WER (English, 6.21% rel), −2.27% abs CER (Cantonese, 6.98% rel) |

The CUHK elderly pair adds two things the pediatric work alone could not:
1. **The non-English channel.** The Cantonese JCCOCC MoCA results (see [[../entities/jccocc-moca-dataset]]) show the gains transfer to a tonal, non-Indo-European language. The pediatric work was English-only.
2. **Training-time × inference-time decomposition.** Deng et al. publish both halves of the pipeline on the same day — online speaker adaptation at inference (2606.16539) and confidence-curriculum + learnable-prompt training-time adaptation (2606.16546). The pediatric work covered only the inference-time adapter axis.

See [[elderly-speech-recognition]] for the dedicated older-edge page.

## Confound: Hearing-Impaired Speech Production

Older-adult speech also covaries with **hearing-impaired speech production** — presbyphonia, dysarthria, reduced articulatory precision, the Lombard effect under self-perceived inaudibility. The USC paper does not disentangle age effects from hearing-loss effects.

For hearing-aid applications this is partly fortunate (the population whose speech the device must understand *is* the older population) but it complicates corpus design: an "older-adult speech corpus" for hearing-aid training is implicitly an "older-adult-with-some-degree-of-hearing-loss corpus", and the corpus design must decide whether that's a feature or a bug.

## Where the Adapter Lives

The foundation models themselves are far too large to fit a hearing-aid SoC (see [[on-device-ml-hearing-aids]]). The natural deployment surface for an age-conditioned adapter is the **paired smartphone** (see [[companion-phone-speech-pipeline]]), where:
- Foundation-model inference already lives (Whisper, Voxtral, Qwen3-ASR).
- The age of the wearer is already known to the companion app.
- An age-conditioned adapter is a few-MB delta over a shared backbone.

A hearing-aid-local adapter is also possible at the small-DNN scale (sub-1M-param scene classifiers, beamformer steering, gain shaping), where lifespan-conditioned variants could be selected at the firmware level based on the wearer's enrolled age band.

## Open Questions
- Does the USC paper's diarization result replicate for **speech enhancement** and **scene classification** — the tasks hearing aids actually run?
- How much of the older-adult degradation is age vs hearing-loss confounded? Is the proper control "older adults with normal hearing"?
- Are pediatric foundation-model adapters governed by additional regulatory constraints under EU MDR and FDA SaMD when deployed in pediatric medical devices?
- Where in the stack should the age conditioning live — at the foundation-model fine-tune layer, at the adapter, at the scene-classifier, at the companion-app prompt? All four are tractable, with different latency/update/regulatory profiles.
- Does **Auracast routing** in venues with multi-age audiences (classrooms, family gatherings, intergenerational care settings) require lifespan-balanced models, or is a single adult-conditioned model adequate in a streaming scenario where the source separation has already been done upstream?

## Related Pages
- [[speech-enhancement-neural-networks]] — Where the foundation-model features feed in
- [[on-device-ml-hearing-aids]] — Why the adapter, not the foundation model, lives on the device
- [[medical-domain-edge-llms]] — Adjacent foundation-model-on-companion-phone framing
- [[small-language-models-edge-ai]] — Compression/adapter techniques for shipping the resulting models
- [[companion-phone-speech-pipeline]] — The deployment tier where lifespan-conditioned adapters most naturally live
- [[../entities/demant-oticon]] — Play SI as the canonical pediatric platform now exposed to the age-distribution-shift problem
- [[longitudinal-hearing-phenotyping]] — Telemetry-side framework that can collect lifespan-stratified data
- [[../entities/vcca-computational-audiology]] — WCA 2026 Seoul "AI for the Ear and Beyond" track as the natural surfacing venue
- [[dnn-in-hearing-aids]] — Acoustic-scene-diversity moat as the prior dimension; lifespan corpora as the new one

## Sources
- [Cross-Lifespan Speaker Diarization (Xu, Feng & Narayanan, May 2026)](../../sources/cross-lifespan-diarization-usc-may-2026.md) — Seed paper; foundation models fail at lifespan edges; domain adaptation closes most of the gap
- [Age-Aware Adapter Tuning for Children's ASR (Li, Jun 2026)](../../sources/arxiv-2606-05440-age-aware-adapter-children-asr-jun-2026.md) — Parameter-efficient per-age-band adapter modules; 12.6%→12.3% WER overall, 18.4%→17.6% macro; predicted-age routing tracks ground-truth; hard age routing > FiLM
- [Elderly ASR Online Audio-Textual Prompt (Deng et al., Jun 15 2026)](../../sources/arxiv-2606-16539-elderly-asr-online-adaptation.md) — Older-edge inference-time bracket; zero-shot online speaker adaptation; English + Cantonese
- [Elderly ASR Confidence-Curriculum Pseudo-Labeling (Deng et al., Jun 15 2026)](../../sources/arxiv-2606-16546-elderly-asr-pseudo-labeling.md) — Older-edge training-time bracket; semi-supervised, learnable speaker prompts
- [Oticon Play SI Pediatric Launch (Apr 2026)](../../sources/oticon-play-si-pediatric-launch-april-2026.md) — Pediatric platform now shipping flagship AI
- [Oticon Play SI HearingReview Coverage (Apr 2026)](../../sources/oticon-play-si-hearingreview-april-2026.md) — Boys Town pediatric clinical evidence
- [Pediatric Softband BCD Database (Frontiers, May 2026)](../../sources/pediatric-softband-bcd-database-frontiers-may-2026.md) — Pediatric candidacy expansion
- [QVAC MedPsy Edge Medical LLM (May 2026)](../../sources/qvac-medpsy-edge-medical-llm-may-2026.md) — Companion-phone substrate that inherits adult-skewed pre-training
