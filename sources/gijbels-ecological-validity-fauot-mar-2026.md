---
title: Gijbels et al. — Striving Toward Ecological Validity in Hearing Science (Frontiers in Audiology and Otology, March 2026)
type: peer-reviewed-paper
date: 2026-03-30
doi: 10.3389/fauot.2026.1772008
url: https://www.frontiersin.org/journals/audiology-and-otology/articles/10.3389/fauot.2026.1772008/full
authors: [Liesbeth Gijbels, Melinda C. Anderson, Christi W. Miller, Khia A. Johnson, Thomas Lunner]
journal: Frontiers in Audiology and Otology
tags: [ecological-validity, audiovisual-speech, listening-comprehension, hearing-assessment, multimodal, outcome-measurement, real-world-evaluation, audiometry, speech-in-noise, lunner, dyadic-conversation]
---

# Striving Toward Ecological Validity in Hearing Science

## Citation

Gijbels L, Anderson MC, Miller CW, Johnson KA, Lunner T. "Striving toward ecological validity in hearing science: evaluating a variety of hearing assessments." *Frontiers in Audiology and Otology* 4: 1772008 (March 30, 2026). DOI: 10.3389/fauot.2026.1772008

(Surfaced into broader industry discussion at the Future of Hearing Healthcare 2026 virtual conference, May 13.)

## Study Design

- **Design:** within-subjects correlational study
- **N:** 26 English-speaking adults, ages 50–79 (13 female, 13 male)
- **Hearing profile:** normal to moderate hearing loss
- **Structure:** 11 dyads + 4 individuals paired with research assistants (dyadic conversation arm)
- **Duration:** 2–3 hours per participant

### Test Battery

1. Standard audiometry and otoscopy
2. **Speech-in-babble** — auditory-only and audiovisual formats (four-talker spatially-separated babble from podcast sources)
3. **Listening comprehension** — podcast playback with comprehension questions
4. **Dyadic conversation** — vocal-effort measurement during paired conversation
5. **Self-report** — both real-time and retrospective questionnaires

## Headline Findings

### What Predicted Self-Reported Hearing Experience Best

- **Audiovisual speech intelligibility** correlated more strongly with self-reported hearing experience than audio-only measures
- **Listening comprehension in noise** was robustly sensitive to hearing difficulties **even in participants with normal audiograms**
- **Real-time self-report** (in-task) strongly predicted objective performance

### What Did NOT Predict Self-Reported Hearing Experience Reliably

- **Vocal intensity changes during conversation** did not reliably indicate hearing-loss severity
- **Retrospective questionnaires** showed limited correlation with objective performance

### The Audiogram-Normal Subgroup

>10% of participants with normal audiograms still struggled in noise — but audiovisual and listening-comprehension assessments recovered them. This is consistent with the [Apple Hearing Study](apple-hearing-study-results-may-2026.md) 16% figure at population scale.

## Author Recommendations

Ecological validity requires assessments that combine:
1. **Visual information** (lip/face cues, gaze, gesture)
2. **Comprehension tasks** (not just word recognition)
3. **Interactive communication** (dyadic, real conversation)
4. **Naturalistic environments** (spatially separated, conversational noise)

No single factor is sufficient — the authors emphasize that **combined** modifications produce sensitivity. Audiovisual stimuli, real-time self-report measures, and recordings of dyadic conversations are flagged as feasible additions to existing clinical workflows.

## Implications for AI Hearing-Aid Development

### 1. The audio-only loss function is misspecified

Current hearing-aid AI is trained on audio-only objectives — PESQ, STOI, HASPI, SI-SDR — that reflect signal-side quality but not the multimodal experience listeners actually integrate. The Gijbels finding suggests these metrics systematically undersell devices that could process visual context, because the ground-truth experience already contains visual information.

### 2. Audiogram + audio-EMA is still partial

The [[../concepts/subjective-objective-hearing-gap]] page documents the population-scale 16% perception-measurement gap. Gijbels et al. show that even with self-report augmentation, **audio-only assessments miss real-world hearing function**. The next layer beyond perception self-report is **multimodal-grounded assessment**.

### 3. The paired smartphone is the cheapest multimodal sensor

Hearing aids ship without cameras and won't get them at any reasonable power budget. But the listener's phone has a camera the user is already pointing at faces during many of their hardest listening situations (FaceTime, group video calls, dinner-table conversations with a phone on the table). Audiovisual speech-enhancement research (CHiME3 lineage; 2024–2026 multimodal foundation-model papers; IEEE "Bringing Multimodal Foundation Models to Hearing Aids") points to phone-camera-side multimodal models that share output with the hearing aid.

### 4. The next outcome metric needs visual ground truth

A HASPI-equivalent metric that incorporates visual ground truth (lip-readability, gaze concordance with speaker, distractor visual occluders) would change which devices score well. This may unlock new product categories — e.g., AR glasses + hearing aid co-systems — by giving them an outcome axis they currently lose on by default.

## Connections to Existing Wiki Pages

- **[[../concepts/subjective-objective-hearing-gap]]** — Apple population-scale 16% gap; Gijbels paper is the clinical-cohort confirmation with a richer assessment battery and a recovery mechanism (audiovisual + comprehension)
- **[[../concepts/automated-audiometry]]** — extends the "automated audiometry" story to multimodal assessment
- **[[../concepts/longitudinal-hearing-phenotyping]]** — multimodal ecological assessments are the next data layer beyond passive audio telemetry
- **[[../concepts/speech-enhancement-neural-networks]]** — current SE methods are audio-only; this paper is part of the case for adding visual context
- **[[../concepts/llm-based-speech-enhancement]]** — multimodal LM SE (audio + visual) is an open research front; this paper articulates why
- **[[../concepts/large-sensor-models]]** — multimodal foundation models for sensors fit the same thesis
- **[[../concepts/hearing-aid-prescription-formulas]]** — NAL-NL3 and prescription targets are tuned to audio-only outcome metrics
- **[[../concepts/care-partner-dyad-models]]** — the dyadic-conversation arm of this study is direct evidence that the unit of analysis should be the dyad

## Related Wiki Pages to Update / Create

- New concept page: **`multimodal-hearing-assessment`** — synthesize Gijbels + adjacent audiovisual SE work
- Update **`subjective-objective-hearing-gap`** with this clinical-cohort confirmation
- Update **`care-partner-dyad-models`** with the dyadic vocal-effort finding (negative result is informative)
- Update **`speech-enhancement-neural-networks`** with multimodal SE as a research direction motivated by ecological validity

## Open Research Directions

1. Replication at larger N — 26 is too small to stratify by audiogram shape, age, or comorbidity.
2. Whether audiovisual intelligibility predicts long-term outcomes (adherence, social participation, dementia risk) better than audiometric pure-tone average.
3. Building an audiovisual HASPI-equivalent — what's the minimal sensor set (lip detection? eye gaze? facial landmarks?) that recovers most of the visual-context benefit?
4. Phone-camera audiovisual SE as a paired-companion product — latency, sync, and privacy tradeoffs.
5. Whether incorporating dyadic-partner self-report adds beyond solo self-report (the dyadic vocal-effort signal didn't, but dyadic *self-report* might).
