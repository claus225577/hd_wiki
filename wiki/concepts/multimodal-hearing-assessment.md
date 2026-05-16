---
title: Multimodal Hearing Assessment
type: concept
created: 2026-05-16
updated: 2026-05-16
sources: [gijbels-ecological-validity-fauot-mar-2026.md, apple-hearing-study-results-may-2026.md]
related: [subjective-objective-hearing-gap.md, automated-audiometry.md, longitudinal-hearing-phenotyping.md, speech-enhancement-neural-networks.md, llm-based-speech-enhancement.md, large-sensor-models.md, hearing-aid-prescription-formulas.md, care-partner-dyad-models.md, on-device-ml-hearing-aids.md]
tags: [multimodal, audiovisual, ecological-validity, hearing-assessment, outcome-measurement, lip-reading, comprehension, dyadic-conversation, speech-in-noise, real-world-evaluation]
---

# Multimodal Hearing Assessment

Hearing assessment that explicitly incorporates **non-audio** signals — visual context (lip movements, gaze, facial expression), comprehension and discourse-level understanding, interactive (dyadic) communication, and naturalistic ecological context — alongside audio measurement. The thesis is that the lived listener experience is multimodal and any assessment limited to the audio channel systematically under-measures real-world hearing function.

## The Motivating Finding

Gijbels, Anderson, Miller, Johnson and Lunner (Frontiers in Audiology and Otology, March 30 2026; n=26, ages 50–79, normal to moderate hearing loss) ran a comprehensive within-subjects battery:

1. Audiometry + otoscopy
2. Speech-in-babble, **audio-only and audiovisual** formats
3. Listening comprehension via podcasts
4. Dyadic conversation with vocal-effort tracking
5. Real-time and retrospective self-report

**Headline results:**
- Audiovisual intelligibility correlated with self-reported hearing experience **more strongly than audio-only** measures
- Listening comprehension in noise was robustly sensitive even in participants with **normal audiograms**
- Real-time self-report (in-task) strongly predicted objective performance
- Retrospective questionnaires showed limited correlation
- Dyadic vocal-intensity changes were **not** a reliable indicator of hearing-loss severity

>10% of normal-audiogram participants still struggled — audiovisual + comprehension assessments recovered them.

See [[../sources/gijbels-ecological-validity-fauot-mar-2026]].

## Population-Scale Confirmation

The Apple Hearing Study (n=160,000, May 2026) found **16% of WHO-normal-audiogram participants** rate their hearing as fair or poor. The Gijbels paper is the clinical-cohort counterpart with a richer assessment battery: the gap is not a self-report artifact, it is recoverable with the right test.

See [[subjective-objective-hearing-gap]] for the population-scale framing.

## Implications for AI Hearing-Aid Development

### 1. The audio-only loss function is misspecified

Modern AI hearing-aid pipelines optimize audio-only metrics — PESQ, STOI, HASPI, SI-SDR, signal-to-distortion. These reflect signal-side quality but not the multimodal information listeners integrate when they understand speech. A device that processes visual context would score the same on these metrics as one that does not.

### 2. Audiogram + audio EMA is still partial

Even augmenting the audiogram with audio-only ecological momentary assessment (EMA) misses the visual contribution. The next layer beyond perception self-report is multimodal-grounded assessment that captures the visual ground truth the listener was integrating.

### 3. The paired smartphone is the cheapest multimodal sensor

Hearing aids ship without cameras and won't get them at any realistic power budget. But the listener's phone is a camera at face-level during many of the hardest listening situations:

- Video calls (FaceTime, Teams, Zoom)
- Phone-on-table dinner conversations
- Group meetings with cameras visible

Phone-camera-side multimodal processing that shares output with the hearing aid is the natural deployment topology. The substrate is already there — see [[../sources/qvac-medpsy-edge-medical-llm-may-2026]] (parent: [[medical-domain-edge-llms]]) for the analog regulatory / privacy / compute story on the same substrate for a different model class.

### 4. The next outcome metric needs visual ground truth

A HASPI-equivalent metric that incorporates visual ground truth would change which devices score well. Candidates:

- Audiovisual speech-in-noise intelligibility under matched lighting/occluder conditions
- Lip-readability score of the target speaker
- Gaze concordance with the target speaker in the scene
- Comprehension at the discourse level, not word-recognition level

A "HASPI-AV" would also create an outcome axis on which **AR glasses + hearing aid co-systems** can score well, potentially unlocking that category for clinical validation.

## Relationship to Audiovisual Speech Enhancement

Audiovisual speech enhancement (AVSE) is the technical side of the same thesis. The CHiME3 lineage (2D-DCT lip features, cross-modal conformer, audio-visual feature synchronization) has been demonstrating consistent gains over audio-only SE for several years. Recent 2024–2026 work (e.g., "Bringing Multimodal Foundation Models to Hearing Aids," IEEE 2024; "Audio-Visual Feature Synchronization for Robust Speech Enhancement in Hearing Aids," August 2025) frames AVSE explicitly for hearing-aid deployment topologies.

The Gijbels paper is the **assessment-side** counterpart to AVSE. Together they form a closed loop:
- AVSE provides the *intervention* (audio + visual processing)
- Multimodal assessment provides the *outcome metric* (audiovisual intelligibility, comprehension)

Both are necessary; an audio-only outcome metric will continue to undersell an AVSE intervention.

## Adjacent Negative Result: Vocal-Intensity Tracking

Gijbels et al. report that **vocal intensity changes during conversation did NOT reliably indicate hearing-loss severity**. This is a clean negative result for one of the more frequently proposed passive monitoring signals (the Lombard-effect-as-biomarker idea). It does not rule out other dyadic signals — turn-taking dynamics, repair requests, conversation length — but it constrains the design space for [[care-partner-dyad-models]].

## Implementation Considerations

### Clinical Feasibility
The full Gijbels battery takes 2–3 hours, which is not viable for routine fitting visits. The authors flag three components as feasible additions to existing clinical workflows:

1. Audiovisual stimuli (lip + audio together) in speech-in-noise testing
2. Real-time self-report (during-task, not retrospective)
3. Dyadic conversation recording for offline analysis

### Sensor Minimization
Open question: what's the minimum sensor set that recovers most of the visual-context benefit?
- Lip-detection only (face landmarks at 68-point or 5-point density)?
- Eye-gaze tracking only?
- Talker-target visual saliency?
- Full audiovisual scene model?

### Privacy
A camera in the listener's environment, even on their own phone, is a privacy-sensitive sensor. On-device processing (no upload) and per-session opt-in are likely necessary for clinical and consumer acceptance.

## Related Pages

- [[subjective-objective-hearing-gap]] — Population-scale and clinical-cohort evidence that audio-only measurement undersells the experience
- [[automated-audiometry]] — The single-modality predecessor; multimodal assessment is its successor
- [[longitudinal-hearing-phenotyping]] — Multimodal ecological assessments are the next layer in this stack
- [[speech-enhancement-neural-networks]] — Audio-only SE; the partner concept needing multimodal expansion
- [[llm-based-speech-enhancement]] — LM-based SE is one path to a multimodal SE model class
- [[large-sensor-models]] — Multimodal foundation-model framing applies to assessment as much as to processing
- [[hearing-aid-prescription-formulas]] — NAL-NL3 and prescription targets currently optimize audio-only metrics
- [[care-partner-dyad-models]] — Dyadic-conversation framing; this study contains negative + positive evidence
- [[on-device-ml-hearing-aids]] — On-device processing constraints shape multimodal feasibility

## Sources

- [Gijbels et al. — Frontiers in Audiology and Otology, March 2026](../../sources/gijbels-ecological-validity-fauot-mar-2026.md) — n=26 within-subjects study showing audiovisual intelligibility and listening comprehension outperform audio-only measures
- [Apple Hearing Study — May 2026 Results](../../sources/apple-hearing-study-results-may-2026.md) — Population-scale 16% perception-measurement gap on normal audiograms
