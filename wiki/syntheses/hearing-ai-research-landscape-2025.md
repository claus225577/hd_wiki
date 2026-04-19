---
title: Hearing+AI Research Landscape 2025
type: synthesis
created: 2026-04-15
updated: 2026-04-17
sources: [phonak-dnn-noise-reduction-clinical-trial-april-2026.md, qwen3-6-35b-a3b-open-source-april-2026.md]
related: [../syntheses/hearing-aid-ai-stack-2026.md, ../comparisons/on-device-vs-cloud-ml.md, ../comparisons/ai-hearing-aid-platforms-2026.md, ../concepts/hearing-loss-dementia-link.md]
tags: [research, landscape, 2025, deep-learning, cochlear-implant, tinnitus, neurosteering, eeg, scoping-review]
---

# Hearing+AI Research Landscape 2025

A synthesis of the research themes at the intersection of hearing science and artificial intelligence, drawing on a 2024 scoping review (91 studies, 2020–2024) plus known frontier research areas.

## Scope and Volume

A 2024 bibliometric/scoping review of AI in audiology and hearing aid research found:
- **91 studies** meeting inclusion criteria (2020–2024)
- **87.5% of all relevant publications appeared in 2020–2024** — the field is effectively new
- Before 2020: AI applications in hearing were sparse; mostly traditional signal processing with ML as a niche tool
- After 2022: Deep learning becomes the dominant paradigm across virtually all sub-areas

This rapid growth mirrors the broader explosion in applied deep learning, but hearing-specific research has lagged consumer AI by ~3–5 years. The commercial products (Phonak DEEPSONIC, ReSound DNN) are ahead of the published literature in some areas, as manufacturers conduct proprietary R&D.

## Research Theme Map

Based on the scoping review, themes can be categorized by maturity:

### Motor Themes (High Activity, High Citation)
Well-established research streams with significant published literature:

1. **Deep learning for cochlear implants (CI)**
   - Signal processing for CI: noise reduction, envelope extraction, channel interaction
   - CI fitting optimization via ML
   - Speech intelligibility prediction in CI users
   - *Key labs:* University of Leuven (Belgium), University of Southampton, MED-EL research group

2. **DNN-based hearing aid signal processing**
   - DNN noise reduction as replacement for traditional Wiener/spectral subtraction
   - Beamforming with learned spatial filters
   - Own voice processing via neural networks
   - Feedback cancellation with ML components

### Emerging Themes (Moderate Activity, Growing)
Active but not yet mature; publishing rate increasing:

3. **Tinnitus management via AI**
   - Personalized sound therapy optimization
   - Tinnitus severity classification from audiological profiles
   - Neuromodulation parameter optimization (emerging)
   - Early work on EEG-guided tinnitus treatment

4. **AI-assisted hearing aid fitting**
   - Automating or augmenting NAL-NL2/DSL prescription fitting
   - Outcome prediction (will this patient benefit from this device?)
   - Preference-based fitting using active learning / reinforcement learning
   - Remote fine-tuning via ML (cf. Signia DNN Assistant commercial implementation)

5. **Hearing screening and early detection**
   - DNN-based audiogram prediction from otoacoustic emissions (OAE) or DPOAE
   - Automated auditory brainstem response (ABR) interpretation
   - Population screening via smartphone (cf. Apple audiometry)
   - NHANES data-driven models for hearing loss risk prediction

6. **High-frequency audiometry and AI**
   - Extended high-frequency (EHF) audiometry (above 8kHz) correlates with early noise damage and ototoxicity
   - AI models that predict standard audiograms from EHF data or vice versa
   - Ototoxicity monitoring in chemotherapy patients

### Frontier Research Areas (Low Volume, High Novelty)
Small number of papers but potentially transformative:

7. **Auditory attention decoding (AAD)**
   - Decoding which speaker a listener is attending to from neural signals (EEG/ECoG)
   - Application: neurosteered hearing aids that automatically switch beam to the attended speaker
   - Technical challenge: requires EEG signals, which require electrodes — currently not miniaturized to hearing aid scale
   - *Key groups:* KU Leuven (Jonas Dynes, Tom Francart), Columbia University

8. **Neurosteering / brain-controlled hearing aids**
   - The end-goal application of AAD: hearing aids that respond to cognitive intent
   - Requires in-ear or on-ear EEG to be practical
   - *Status:* Proof of concept in lab; 2–5 years from practical demonstration; 5–10 years from product
   - Conceptually related to BCI research (Neuralink, etc.) but targeting a much lower-bandwidth use case

9. **In-ear EEG for hearing applications**
   - Electrodes embedded in hearing aid or earbud
   - Records EEG from ear canal — inferior signal quality to scalp EEG but wearable
   - Applications: AAD, cognitive load monitoring, sleep staging, seizure detection
   - *Key lab:* **Aarhus University Ear-EEG group** (Preben Kidmose, Søren Korsholm Christensen) — most published group in in-ear EEG worldwide
   - Challenges: motion artifacts, electrode-skin contact in dynamic environment, signal-to-noise ratio

10. **Large models for audio and hearing**
    - Adaptation of large audio models (Whisper, AudioLM, EnCodec) for hearing aid applications
    - Using large model representations as initialization for small on-device models
    - Few-shot fitting: use a large model to infer a complete audiogram from minimal test data
    - *Status:* Very early; most work at INTERSPEECH / ICASSP, not yet in audiology journals

## Key Institutions and Labs

| Institution | Focus | Key Researchers |
|-------------|-------|-----------------|
| Aarhus University (Denmark) | In-ear EEG, Ear-EEG | Preben Kidmose, S.K. Christensen |
| KU Leuven (Belgium) | Auditory attention decoding, CI signal processing | Tom Francart, Jan Wouters |
| Johns Hopkins (US) | ACHIEVE study, hearing-cognition | Frank Lin, Nicholas Reed |
| University of Southampton (UK) | CI machine learning | Rachel van Besouw |
| DTU (Denmark) | Hearing aid signal processing, DNN | Jesper Jensen |
| Starkey Hearing Research | Proprietary; health + AI | Industry R&D |
| Sonova (Phonak) | Proprietary; DEEPSONIC, scene classification | Industry R&D |
| Demant (Oticon) | Proprietary; sensor fusion DNN | Industry R&D |

## Clinical Validation Pipeline Challenges

The gap between research publications and clinical products is wide in hearing AI. Key friction points:

1. **Lack of standardized outcome measures** — Research uses heterogeneous measures (HINT, QuickSIN, APHAB, subjective ratings); hard to compare across studies

2. **Lab-to-real-world generalization** — DNN models trained on anechoic or controlled noise conditions often degrade in real-world reverberant environments; published results can be optimistic

3. **Small sample sizes** — Most hearing AI studies use 10–50 subjects; insufficient for clinical claims. The ACHIEVE study (n=977) is exceptionally large for the field.

4. **Device heterogeneity** — Research findings from one hearing aid platform rarely transfer directly to another due to proprietary DSP differences

5. **Regulatory pathway** — FDA Class II clearance for software-based diagnostic and fitting tools requires clinical data that most academic labs cannot generate

6. **Publication lag** — Commercial manufacturers are 2–4 years ahead of published literature in DNN architectures; the academic literature describes what industry deployed in 2021–2022

7. **AAD clinical trial design** — For neurosteering/AAD to advance to clinical use, a new class of clinical trials is needed (EEG-controlled, prospective, with patient-reported outcomes); none have yet been completed

## Clinical Evidence Building (April 2026 Update)

A notable shift is underway from marketing-driven AI claims toward clinical evidence:
- **Phonak NCT07526428** — First registered clinical trial for DNN noise reduction in moderate-to-severe hearing loss (April 2026)
- This signals the industry recognizing that clinical trial data will become necessary for regulatory claims, insurance reimbursement, and clinical guideline inclusion
- Expect more manufacturers to register DNN hearing aid clinical trials in 2026-2027

## Open-Source AI and Hearing Research

Open-source model releases (e.g., Qwen3.6-35B-A3B, April 2026 — 35B params, 3B active via MoE) are lowering barriers for hearing AI research:
- Academic labs can fine-tune large open-source models for audio/hearing tasks without access to proprietary training infrastructure
- MoE (mixture-of-experts) architecture is conceptually relevant to hearing aid ML: deploy scene-specific expert sub-networks
- The compression trajectory (175B GPT-3 in 2020 to 3B active in 2026) suggests hearing-aid-scale foundation models within the decade

## What This Means for the Field

- **2025–2027:** DNN noise reduction and fitting AI will be standard in all premium hearing aids; clinical trial evidence building begins; academic literature will catch up with commercial implementations
- **2027–2030:** AAD proof-of-concept in wearable hearing aids; in-ear EEG achieves reliable consumer-grade SNR
- **2030+:** Neurosteered hearing aids in clinical trials; large audio models routinely fine-tuned for individual hearing profiles at fitting

## Related Pages
- [[hearing-aid-ai-stack-2026]] — Commercial applications of the research themes
- [[hearing-loss-dementia-link]] — ACHIEVE study and Johns Hopkins research context (hearing-dementia connection)
- [[on-device-vs-cloud-ml]] — Architecture implications of research-to-product translation
- [[ai-hearing-aid-platforms-2026]] — Where commercial products currently stand

## Sources
- Scoping review of AI in audiology (2024, 91 studies, 2020–2024)
- Aarhus University Ear-EEG group publications
- Johns Hopkins ACHIEVE study publications
