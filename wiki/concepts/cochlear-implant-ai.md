---
title: AI in Cochlear Implants
type: concept
created: 2026-04-15
updated: 2026-06-18
last_change: 2026-06-18 — Added "Foundational Layer Recognition — 2026 Merkin Prize" section after the Merkin Prize was announced June 17 2026 to Clark, Hochmair, Hochmair, Merzenich, Wilson. Framed Blake Wilson's 1989 CIS strategy as the persistent fixed-rule signal-processing primitive on top of which the ML/AI layer (Cochlear Nucleus Nexa Jan 2026, BiEAR/FAConformer/BASENet June 2026 band-axis cluster) is being built. Cross-referenced to the new source file merkin-prize-cochlear-implant-pioneers-june-2026.md and to the band-axis synthesis.
sources: [deep-learning-framework-cochlear-implants-2025.md, avse-ecs-audiovisual-ci-2025.md, ml-ci-speech-perception-multicenter-2025.md, pediatric-ci-language-prediction-transfer-learning-2025.md, ai-cochlear-implant-innovations-review-2025.md, advanced-bionics-research-collaboration-ci-april-2026.md, dnn-noise-reduction-intelligibility-2026.md, completely-implantable-cochlear-implants-april-2026.md, dat-cftnet-ci-speech-enhancement-icassp-2026.md, tokense-mamba-ci-speech-enhancement-2026.md, end-to-end-audiovisual-ci-sound-coding-arxiv-2026.md, otarmeni-fda-gene-therapy-approval-april-2026.md, harvard-mass-eye-ear-gene-therapy-otof-nature-2026.md, cochlear-nucleus-nexa-smart-implant-2026.md, lucia-bilateral-ci-trial-may-2026.md, jamia-open-ci-eligibility-audiogram-2026.md, merkin-prize-cochlear-implant-pioneers-june-2026.md]
related: [dnn-architectures-hearing-aids.md, on-device-ml-hearing-aids.md, speech-enhancement-neural-networks.md, auditory-attention-decoding.md, ../entities/vcca-computational-audiology.md, ../entities/advanced-bionics.md, ../entities/sonova-ag.md, precision-drug-delivery-inner-ear.md, ../entities/envoy-medical.md, hearing-aid-chip-architectures.md, compute-in-memory.md, state-space-models.md, mamba-architecture.md, gene-therapy-hearing.md, ../entities/regeneron.md, ../entities/cochlear-ltd.md, software-defined-medical-implants.md, longitudinal-hearing-phenotyping.md, ../entities/aci-alliance-ci2026.md, ../syntheses/cochlear-implant-access-economics.md, ../syntheses/band-axis-shared-coordinate-system-june-2026.md]
tags: [cochlear-implant, ci, deep-learning, speech-recognition, outcomes-prediction, sound-coding, pediatric, advanced-bionics, fully-implantable, gene-therapy, cis-strategy, merkin-prize, foundational-layer]
---

# AI in Cochlear Implants

Cochlear implants (CIs) are surgically implanted devices that bypass damaged hair cells and directly stimulate the auditory nerve via an electrode array. AI and deep learning are being applied across the CI pipeline: from pre-surgical outcome prediction, to signal processing, to post-surgical rehabilitation.

## Foundational Layer Recognition — 2026 Merkin Prize

On **June 17, 2026**, the $400,000 Richard N. Merkin Prize in Biomedical Technology was awarded jointly to five cochlear-implant pioneers — Graeme Clark, Erwin Hochmair, Ingeborg Hochmair, Michael Merzenich, and Blake Wilson — for the foundational work underpinning every CI shipping today. The award sits at the **base of the CI stack** that current ML/AI work is layering on top of.

Key contributions:
- **Hochmair & Hochmair (1977)** — first multi-channel microelectronic CI, implanted in Vienna December 16, 1977. The hardware substrate the Cochlear Nucleus Nexa system, MED-EL, and Advanced Bionics all extend.
- **Graeme Clark (1985)** — first FDA-approved multi-channel implant; speech-coding insights enabling spoken-language understanding without lipreading.
- **Michael Merzenich** — established the neurophysiological basis; led commercialization through what became **[[../entities/advanced-bionics]]** (now a Sonova subsidiary).
- **Blake Wilson (1989)** — developed **Continuous Interleaved Sampling (CIS)**, the sound-coding strategy that pushed mean speech understanding past 80% across CI users. **CIS remains the default in every shipping CI 35+ years later** — the canonical example of a fixed-rule signal-processing primitive that ML extensions wrap rather than replace.

### Why This Matters for AI/ML Work in CIs
The Merkin Prize announcement is the right reference point for framing where ML adds value in CIs: **a learnable shell on top of a foundational primitive that was right the first time.** Concretely:

| Layer | Foundational (Merkin-recognized) | ML/AI Extension (2026) |
|-------|----------------------------------|------------------------|
| Hardware substrate | Hochmair multi-channel implant (1977) | Cochlear Nucleus Nexa on-implant ML chip (Jan 2026); fully-implantable candidates (April 2026) |
| Sound coding | Wilson CIS (1989) | DAT-CFTNet, TokenSE-Mamba, end-to-end audiovisual CI sound coding (2026 arXiv) |
| Band-axis processing | Clark speech-coding insights | BiEAR / FAConformer / BASENet band-axis cluster (June 2026); see [[../syntheses/band-axis-shared-coordinate-system-june-2026]] |
| Outcome / referral | Merzenich neurophysiology + early trials | JAMIA Open CI eligibility from audiograms (2026); JAMA pre-implant MRI language-outcome prediction (2025) |
| Commercialization | Merzenich → Advanced Bionics | [[../entities/sonova-ag]] CI division; Spiral Therapeutics drug-delivery investment (Apr 2026) |

Source: [[../../sources/merkin-prize-cochlear-implant-pioneers-june-2026]]. Ceremony scheduled September 2026.

## What Makes CI Different from Hearing Aids

| Feature | Hearing Aid | Cochlear Implant |
|---------|-------------|-----------------|
| Mechanism | Amplifies acoustic sound | Direct electrical stimulation of auditory nerve |
| Indication | Mild-severe hearing loss | Severe-profound hearing loss |
| Reversible | Yes | No (implant is permanent) |
| Sound quality | Close to natural | Degraded — users hear ~20 spectral channels vs ~3,500 in normal hearing |
| Fitting | Audiogram-based | Threshold measurement per electrode |
| AI potential | Noise reduction, scene classification | Outcome prediction, sound coding, rehabilitation |

## AI for Outcome Prediction

### Predicting Language Outcomes in Children
- **Study:** 278 children across 3 languages (English, Mandarin, Portuguese)
- **Input:** Pre-implant MRI structural brain scans
- **Method:** Deep learning on MRI features to predict post-implant language development
- **Accuracy:** 92% accuracy in predicting language outcome category (good/poor)
- **Significance:** Enables better surgical counseling, earlier rehabilitation planning, and identification of children needing intensive post-implant therapy

### Why Prediction Matters
CI outcomes vary enormously: some children achieve near-normal language; others plateau at poor speech intelligibility. Predicting outcomes before surgery helps:
- Set realistic family expectations
- Prioritize rehabilitation resources
- Inform surgical timing decisions (earlier implantation generally better)
- Identify children who may benefit from additional therapeutic support

### LUCIA Trial — A New Cohort for Adult Bilateral CI Modelling (May 2026)
A national UK RCT announced 6 May 2026 (Cambridge / Birmingham, 14 NHS hospitals, n > 250) will randomize profoundly deaf adults to one vs two cochlear implants — the first system-scale interventional comparison of bilateral vs unilateral CI in late-deafened adults. Existing bilateral evidence is registry- and case-series-based; LUCIA generates the labeled cohort that pre-implant outcome-prediction models (e.g., the JAMA / Northwestern preimplant-MRI deep-transfer-learning approach above) need to extend from "will this child benefit from one CI?" to "who benefits from a second implant?" The trial does not propose any new AI technology — it is purpose-built to produce the missing dataset.

See [[../../sources/lucia-bilateral-ci-trial-may-2026]] and [[../syntheses/cochlear-implant-access-economics]].

### AI for CI Eligibility / Referral (JAMIA Open, 2026)
Only ~5–10% of CI-eligible adults in the US are actually implanted — the gap is largely a **referral** problem, not a surgical capacity problem. A JAMIA Open paper (2026) trains an ML model to flag CI-eligible adults directly from routine audiograms, materially outperforming current referral heuristics (e.g., the "60/60 rule"). Framed as a **clinical-utility / deployment lessons paper**, not a benchmark race — the value is the audit trail of pushing a CI-eligibility classifier into clinician workflow. Eligibility prediction is a distinct ML problem from outcome prediction (will this person benefit?) and the field needs both; the audiogram-as-input substrate is realistic, every audiologist already collects it. Pairs with the [[automated-audiometry]] thread and the [[audiologist-workforce-shortage]] response. See [[../sources/jamia-open-ci-eligibility-audiogram-2026]].

## AI for Speech Processing (Sound Coding)

### ANNs Matching Best Human CI Users
Artificial neural networks applied to CI sound coding have achieved:
- Speech recognition scores matching the **best-performing human CI users** in quiet conditions
- Sound localization accuracy comparable to top CI performers
- These are research benchmarks, not yet deployed in commercial CI processors

### Ultra-Low Latency DNN Noise Reduction
- CI users face the same noise challenges as hearing aid users, but worse — fewer spectral channels means less redundancy
- DNN-based noise reduction adapted for CI (operating pre-stimulation) shows significant improvement in noisy environments
- Latency constraints are similar to hearing aids: < 10ms algorithmic delay
- See [[dnn-architectures-hearing-aids]] for applicable architectures

### Conv-TasNet Listener Group Study (Schulz et al. 2026)
Schulz et al. (Frontiers in Audiology and Otology, Jan 2026) tested Conv-TasNet with 1ms latency across three groups and found **CI users gained the most from DNN noise reduction**:
- **CI users: +5.7 dB** SNR improvement — the largest benefit of any group tested
- Hearing-impaired: +0.8 dB; normal-hearing: slightly degraded
- **Key insight:** DNN benefit inversely correlates with baseline hearing deficit — CI users have the worst baseline and gain the most
- **Product implication:** DNN noise reduction should be a priority feature for CI sound processors, where it delivers the highest ROI

### DAT-CFTNet: Attention-Based Dual-Path RNN for CI (ICASSP 2026)
Mamun & Hansen (arXiv:2604.06744) propose an attention-based dual-path RNN specifically for CI speech enhancement:
- **Outperforms CFTNet and DCCRN** — established baselines for real-time SE
- **Eliminates musical artifacts** — a critical CI-specific problem where spectral processing remnants are highly disruptive through electrode stimulation
- Validates dual-path RNN + attention as viable for CI-constrained enhancement

### TokenSE: Mamba-Based Speech Enhancement for CI (April 2026)
Chiang & Hansen (arXiv:2604.12246) — first selective state space model (Mamba) applied to CI speech enhancement:
- **O(n) linear complexity** vs O(n^2) for Transformers — critical for CI processor compute budgets
- Operates on **discrete speech tokens** for compression before SSM processing
- **Subjective tests with actual CI users** confirm intelligibility gains
- Demonstrates Mamba as viable for CI-specific enhancement; see [[mamba-architecture]]

### End-to-End Audio-Visual CI Sound Coding (arXiv, April 2026)
New end-to-end system (arXiv:2508.13576v1) combining audio and visual modalities for CI sound coding:
- **Combines microphone audio with lip-reading video** to produce CI electrodograms directly
- **End-to-end learning** — jointly optimizes audio processing, visual processing, and electrodogram generation
- **Noise-robust:** visual signal provides independent information when audio is degraded — CI users' core challenge
- Learns to weight audio vs. visual signals based on noise conditions (audio dominates in quiet; visual gains weight in noise)
- **Practical deployment path:** Most likely first as a smartphone app processing audio-visual input and streaming optimized audio to the CI processor
- Advances prior work (AVSE-ECS, 2025) with true end-to-end learning rather than separate A/V stages
- This formalizes computationally what CI users already do naturally: rely on lip-reading as a compensatory strategy

## AI for Personalized Rehabilitation

### Adaptive Fitting
- Standard CI fitting is time-intensive (multiple audiologist sessions to map each electrode)
- ML models that predict optimal electrode maps from user characteristics could reduce fitting burden
- Active area of clinical AI research

### Rehabilitation Guidance
- AI-powered speech training apps can adapt difficulty based on user performance
- Analysis of usage patterns to identify users at risk of poor adherence to rehabilitation programs
- Personalized exercise sequences informed by speech error patterns

## Research Trend: Increasing ML Publications

ML-in-CI publications have grown substantially since 2018, tracking the broader deep learning research surge:
- Pre-2018: primarily adaptive signal processing, limited neural network applications
- 2018-2021: DNN noise reduction, outcome classification models
- 2022-present: End-to-end sound coding, foundation model approaches, large-scale outcome prediction

## Key Manufacturers

- **Cochlear Ltd. (Australia)** — Nucleus systems; largest CI manufacturer globally (~50% U.S. market share, 700,000+ devices implanted). Launched Nucleus Nexa (2025), the world's first cochlear implant with upgradeable firmware and on-implant memory — see [[../entities/cochlear-ltd]] and [[software-defined-medical-implants]]. Available to U.S. veterans through VA (Jan 2026); featured at AAA 2026. 21 years R&D on a separate fully implantable CI with subcutaneous mic.
- **MED-EL (Austria)** — Extensive electrode array designs, strong in fine structure processing; developing TICI (Totally Implantable CI) with subcutaneous mic
- **Envoy Medical (USA)** — Acclaim fully implantable CI; piezoelectric incus sensor, no magnet, chest battery (10-15 yr); FDA approval anticipated late 2027/early 2028. See [[envoy-medical]].
- **Advanced Bionics (USA, Sonova subsidiary)** — HiRes sound coding, Naida processor; announced next-gen CI research collaboration (April 2026) — see [[advanced-bionics]]
- **Oticon Medical (Demant subsidiary)** — Neuro 2 processor

### Advanced Bionics + Spiral Therapeutics (April 2026)
AB announced an equity investment + R&D collaboration with **Spiral Therapeutics** (precision drug delivery for inner ear) as part of Spiral's $27M Series B. The collaboration investigates drug delivery during cochlear implant surgery — a new therapeutic axis combining device + pharmacology. Potential applications include residual hearing preservation during electrode insertion, anti-inflammatory treatment, and neural survival enhancement. This is significant because it expands CI innovation beyond electronics into pharmacotherapy. See [[precision-drug-delivery-inner-ear]].

Sonova's dual-track strategy now spans three domains: hearing aid AI (DEEPSONIC/Phonak), CI electronics (AB), and CI pharmacotherapy (Spiral partnership).

## Fully Implantable Cochlear Implants (April 2026)

Three companies are developing **completely implantable CIs** with no external processor — representing the ultimate edge AI challenge for hearing technology:

| Company | Device | Sound Capture | Battery | Status |
|---------|--------|---------------|---------|--------|
| **Envoy Medical** | Acclaim | Piezoelectric at incus | Chest, 10-15 yr | Pivotal trials; FDA late 2027/early 2028 |
| **Cochlear Ltd.** | Unnamed | Subcutaneous mic | Behind ear | 21 years R&D |
| **MED-EL** | TICI | Subcutaneous mic | Not disclosed | In development |

### AI Implications for Fully Implantable CIs
- **Sub-microwatt inference budgets:** 10-15 year battery life with continuous operation requires power levels orders of magnitude below current hearing aid chips (1-5 mW)
- **Novel input signals:** Envoy's piezoelectric ossicular vibration is fundamentally different from acoustic microphone input — ML preprocessing pipelines may not transfer directly
- **No external update path:** Firmware updates require wireless over-skin programming or surgical intervention
- **Thermal constraints:** All compute within biocompatible housing; tissue damage above ~2C rise
- Technologies like [[compute-in-memory]] and [[state-space-models]] are particularly relevant — ultra-low-power inference could enable AI in fully implantable devices
- See [[envoy-medical]] for Envoy Medical details

## Challenges and Open Questions

- **Spectral resolution ceiling:** CIs provide ~20 channels of spectral information; AI can optimize coding but cannot exceed this physical limit
- **Music perception:** Remains very poor for most CI users; AI approaches show some improvement but it's a hard problem
- **Individual variability:** Why some CI users do dramatically better than others is not fully understood; AI may help decode this variability
- **Regulatory pathway:** AI-based sound coding changes require FDA/CE clearance, slowing deployment relative to research advances
- **Power constraints:** CI sound processors have battery/power constraints similar to hearing aids

## Recent Academic Advances (2024–2026)

### Deep Learning Framework with 3D-Printed Cochleae (2025)
Co-modelling framework combining 3D-printed biomimetic cochleae with ML for interpreting electric field imaging (EFI) profiles. Predicts patient-specific anatomy and tissue resistivity for personalized CI fitting. Published in PMC.

### AVSE-ECS: Audio-Visual CI Sound Coding (2025)
Novel system using audio-visual speech enhancement (lip reading + audio) as pre-processing for deep-learning-based ElectrodeNet-CS sound coding. End-to-end learning from multimodal input to electrode stimulation patterns. arXiv.

### Largest CI Outcome Prediction Study (2025)
4,046 patients across 32 US institutions (Ear and Hearing, September 2025). Assesses ML feasibility for predicting post-implant speech perception — unprecedented scale for CI outcome prediction.

### Pediatric Language Prediction via Transfer Learning (2025)
278 pediatric CI recipients, 3 languages, pre-implant MRI → 92.39% accuracy in forecasting spoken language improvement using bilinear attention-based deep transfer learning.

## Related Pages
- [[dnn-architectures-hearing-aids]] — Same DNN architectures (CRN, transformer) apply to CI processors
- [[on-device-ml-hearing-aids]] — Shared edge inference constraints between HAs and CI processors
- [[speech-enhancement-neural-networks]] — Core enhancement pipeline applicable to CI pre-processing
- [[auditory-attention-decoding]] — AAD research often conducted with CI users who have implanted electrodes
- [[vcca-computational-audiology]] — CI research is a core VCCA track
- [[advanced-bionics]] — Sonova's CI subsidiary; Spiral Therapeutics collaboration
- [[sonova-ag]] — Parent company of Advanced Bionics
- [[precision-drug-delivery-inner-ear]] — Drug delivery during CI surgery; new therapeutic axis
- [[gene-therapy-hearing]] — Gene therapy (Otarmeni, April 2026) may reduce CI candidacy for some OTOF-mutation patients
- [[regeneron]] — Manufacturer of Otarmeni, first gene therapy for hearing loss
- [[envoy-medical]] — Acclaim fully implantable CI; piezoelectric sensor, no external components
- [[compute-in-memory]] — Ultra-low-power hardware relevant to fully implantable CI constraints
- [[state-space-models]] — Efficient model architecture for power-constrained CI processors
- [[../entities/cochlear-ltd]] — Largest CI manufacturer; Nucleus Nexa smart implant
- [[software-defined-medical-implants]] — Concept formalized by the Nexa system; MLOps for in-vivo devices
- [[longitudinal-hearing-phenotyping]] — Measurement substrate for tracking CI outcomes over years

## Sources
- [DL Framework for CI with 3D Cochleae](../sources/deep-learning-framework-cochlear-implants-2025.md)
- [AVSE-ECS Audio-Visual CI Coding](../sources/avse-ecs-audiovisual-ci-2025.md)
- [ML CI Speech Perception — 4,046 patients](../sources/ml-ci-speech-perception-multicenter-2025.md)
- [Pediatric CI Language Prediction](../sources/pediatric-ci-language-prediction-transfer-learning-2025.md)
- [AB Next-Gen CI Research Collaboration](../sources/advanced-bionics-research-collaboration-ci-april-2026.md)
- [Schulz et al. Conv-TasNet Listener Groups](../sources/dnn-noise-reduction-intelligibility-2026.md) — CI users gain +5.7 dB from DNN noise reduction, most benefit of any group
- [Completely Implantable Cochlear Implants](../sources/completely-implantable-cochlear-implants-april-2026.md) — Three companies developing fully implantable CIs; Envoy Acclaim with piezoelectric sensor
- [DAT-CFTNet CI Speech Enhancement](../sources/dat-cftnet-ci-speech-enhancement-icassp-2026.md) — Attention dual-path RNN, eliminates musical artifacts (ICASSP 2026)
- [TokenSE Mamba CI Speech Enhancement](../sources/tokense-mamba-ci-speech-enhancement-2026.md) — First Mamba-based SE for CI with subjective validation
- [FDA Approves Otarmeni](../sources/otarmeni-fda-gene-therapy-approval-april-2026.md) — First gene therapy for hearing loss; may reduce CI candidacy for OTOF mutations
- [Harvard/Fudan OTOF Nature Study](../sources/harvard-mass-eye-ear-gene-therapy-otof-nature-2026.md) — 90% improvement, 50% normal hearing at 2.5 years
- [Cochlear Nucleus Nexa Smart Implant](../sources/cochlear-nucleus-nexa-smart-implant-2026.md) — World's first CI with upgradeable firmware and on-implant memory
- [JAMIA Open — ML for CI Eligibility Prediction](../sources/jamia-open-ci-eligibility-audiogram-2026.md) — Audiogram-based ML referral model; clinical-utility framing
