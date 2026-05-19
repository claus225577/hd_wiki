---
title: Listening Effort as a First-Class Hearing-AI Metric
type: concept
created: 2026-05-18
updated: 2026-05-19
last_change: 2026-05-19 — cross-linked to the new speech-enhancement-evaluation-stack-cracks-may-2026 synthesis and the asr-too-good-to-be-true ASR-as-SE-eval source; ASR-derived effort proxy from Behringer is now in tension with the de Oliveira finding that the same noise-robust ASR systems hide acoustic damage on the intelligibility side
sources: [codec-intelligibility-se-behringer-arxiv-2026.md, l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md, korhonen-natural-vs-dnn-hearing-aids-april-2026.md, gijbels-ecological-validity-fauot-mar-2026.md, asr-too-good-to-be-true-arxiv-may-2026.md]
related: [speech-enhancement-neural-networks.md, subjective-objective-hearing-gap.md, multimodal-hearing-assessment.md, dnn-in-hearing-aids.md, cortical-reorganization-hearing-aids.md, auracast-bluetooth-le-audio.md, companion-phone-speech-pipeline.md, linguistic-hallucination-speech-enhancement.md, ../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026.md]
tags: [listening-effort, evaluation-metrics, cognitive-load, fatigue, outcome-measurement, audiology-metrics, pupillometry, ssq, neurosci-eval, codec-evaluation]
---

# Listening Effort as a First-Class Hearing-AI Metric

The hearing-aid AI evaluation stack has spent two decades optimising for **speech intelligibility** — PESQ, STOI, HASPI, SI-SNR, DNS-MOS. But the outcome that actually drives **device abandonment** is **listening effort**: the cognitive cost a user pays to extract meaning from sound. Two systems that score identically on intelligibility can diverge sharply on effort.

## Why It Matters
- **Fatigue is the cardinal patient complaint** after acoustic comfort. Effort is what produces it.
- Intelligibility measures **whether** the message was understood. Effort measures **at what cost**.
- A codec, speech-enhancer, or fitting strategy that ties on intelligibility but doubles effort is, for the user, the worse system. The current evaluation stack cannot tell us that.

## Sources of Evidence

### Behringer et al. (arXiv:2605.03776, May 2026)
First codec-level demonstration that listening-effort metrics **reveal differences invisible to intelligibility measurements**. Classical vs. neural speech codecs evaluated under clean and noisy conditions with and without speech-enhancement preprocessing; effort metrics separated systems that intelligibility metrics did not. ASR metrics correlated strongly with subjective effort ratings — a usable automatic proxy.

### Korhonen / Kuk / Slugocki (Widex, Apr 2026)
The "natural processing beats DNN by up to 8.5 dB SNR" finding implicitly leans on the effort/intelligibility distinction — natural processing preserves spectral structure that reduces cognitive load even when SNR-equivalent.

### Becker et al. MEG study (Apr 2026)
12-week cortical reorganization from HA wear correlated with **individual** speech-in-noise improvement, not population mean. Cortical efficiency is the upstream neural substrate of subjective effort.

### L3-SE linguistic hallucination (Wang et al., May 9 2026)
Effort is also the channel through which hallucinated SE output is detectable — listeners cannot tell whether words are wrong but they pay more cognitive cost. Faithfulness and effort are likely correlated failure modes for generative SE.

## Measurement Approaches

| Method | Pros | Cons |
|--------|------|------|
| **Subjective scales (NASA-TLX, SSQ-effort, single-item Likert)** | Cheap, fast, deployable | Subjective; affected by demand characteristics |
| **Pupillometry (peak pupil dilation, mean pupil size)** | Quantitative, well-validated | Lab equipment; lighting / arousal confounds |
| **Dual-task paradigms** | Captures cognitive resources | Task choice changes the effort signature |
| **EEG / fNIRS** | Direct cortical signal | Setup cost; signal-to-noise |
| **Behavioral surrogates (response time, fatigue at end of day)** | Ecologically valid | Indirect |
| **ASR-derived proxies** | Automatic; scales to large evaluations | Validity vs. human effort unproven across conditions; same noise-robustness that helps the effort proxy *hides* acoustic damage when ASR is reused as an intelligibility metric (see [[asr-too-good-to-be-true-arxiv-may-2026]]) |

## The Pipeline Gap
- **Codecs:** evaluated for bitrate × intelligibility. Behringer et al. argue effort must be added.
- **Speech enhancement (classical):** PESQ / STOI default. Effort rarely reported.
- **Speech enhancement (DNN):** DNS-MOS / HASPI / HASQI. Same gap.
- **Speech enhancement (LM-based / generative):** intelligibility scores can stay high while linguistic hallucination raises effort sharply.
- **Fitting prescription (NAL / DSL / OEM):** prescription validation studies report intelligibility, REM targets, and self-report. Effort rarely an outcome.

## What "First-Class" Would Mean
1. Effort reported alongside intelligibility in **every** SE / codec / fitting evaluation.
2. A standardised effort metric (or a small set with cross-mapping) the field agrees on.
3. **HASPI-equivalent for effort** — an objective predictor validated against pupillometry / behavioral data, runnable on a dev workstation.
4. Effort as an **acceptance criterion** in regulatory submissions for generative-SE SaMD.
5. Telemetry-side effort proxies (interaction patterns, end-of-day adherence drop-off) used for closed-loop personalization.

## Open Questions
- Does ASR-effort correlation hold for hearing-impaired listeners, or only for normal-hearing?
- Effort under generative SE that hallucinates linguistically vs. effort under classical SE that distorts spectrally — same units, comparable?
- Telemetry-derived effort proxies vs. lab pupillometry — calibration mapping?

## Related Pages
- [[speech-enhancement-neural-networks]] — the architectures whose evaluation needs effort upgraded
- [[subjective-objective-hearing-gap]] — adjacent measurement-gap concept on the perception side
- [[multimodal-hearing-assessment]] — alternative axis for capturing what audio-only misses
- [[cortical-reorganization-hearing-aids]] — neural substrate of effort
- [[linguistic-hallucination-speech-enhancement]] — effort as channel for detecting hallucinated SE output
- [[companion-phone-speech-pipeline]] — codec choice is now a phone-side decision, effort applies there too

## Sources
- [Behringer et al. — Speech Codec Intelligibility & Effort (arXiv:2605.03776, May 5 2026)](../../sources/codec-intelligibility-se-behringer-arxiv-2026.md)
- [Korhonen, Kuk & Slugocki — Natural vs DNN Hearing Aids (Hearing Review, April 2026)](../../sources/korhonen-natural-vs-dnn-hearing-aids-april-2026.md)
- [Gijbels et al. — Ecological Validity in Hearing Science (Frontiers, Mar 2026)](../../sources/gijbels-ecological-validity-fauot-mar-2026.md)
- [Wang et al. — L3-SE Linguistic Hallucination in LM-Based SE (arXiv:2605.08608, May 9 2026)](../../sources/l3-se-linguistic-hallucination-llm-speech-enhancement-may-2026.md)
- [de Oliveira, Peer & Gerkmann — Too Good to Be True: Modern ASR for SE Evaluation (arXiv:2605.12107, May 12 2026)](../../sources/asr-too-good-to-be-true-arxiv-may-2026.md)

## See Also
- [[../syntheses/speech-enhancement-evaluation-stack-cracks-may-2026]] — synthesis covering the three cracks in the SE evaluation stack identified in May 2026 (effort, linguistic faithfulness, ASR-yardstick).
