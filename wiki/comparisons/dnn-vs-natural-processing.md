---
title: DNN vs Natural Processing in Hearing Aids
type: comparison
created: 2026-04-23
updated: 2026-04-23
sources: [korhonen-natural-vs-dnn-hearing-aids-april-2026.md]
related: [../concepts/dnn-in-hearing-aids.md, ../concepts/speech-enhancement-neural-networks.md, ../entities/ws-audiology-signia.md, ../concepts/on-device-ml-hearing-aids.md, ../comparisons/ai-hearing-aid-platforms-2026.md]
tags: [comparison, dnn, natural-processing, widex, speech-in-noise, clinical-evidence, snr]
---

# DNN vs Natural Processing in Hearing Aids

A comparison of DNN-based and classical DSP ("natural processing") approaches to noise reduction in hearing aids, informed by Korhonen et al. (Hearing Review, April 2026).

## The Study: Korhonen et al. 2026

### Design
- **29 adults** with sensorineural hearing loss (SNHL)
- **5 premium hearing aids** tested — Widex Allure (no DNN) vs. 4 DNN-based competitors
- **8-speaker realistic noise setup** (ezSRT test at SRT90)
- More ecologically valid than typical 2-4 speaker lab conditions

### Results

| Metric | Widex Allure (Natural) | DNN Competitors (avg) |
|--------|----------------------|----------------------|
| Word recognition | **80%** | 60-70% |
| SNR advantage (moderate HL) | **Up to 8.5 dB better** | Baseline |

Widex Allure outperformed all 4 DNN-based competitors by up to 8.5 dB SNR in speech reception thresholds for moderate hearing loss.

## Approach Comparison

| Dimension | Natural Processing (Widex) | DNN-Based (Competitors) |
|-----------|--------------------------|------------------------|
| **Core method** | Classical DSP preserving temporal speech cues | Learned noise masks from training data |
| **Temporal fine structure** | Preserved | May be partially suppressed by aggressive masking |
| **Training data dependency** | None | 12M-22M scenes; performance bounded by data coverage |
| **Generalization** | Physics-based; generalizes to any acoustic scene | Limited by training distribution; may struggle on out-of-distribution scenes |
| **Computational cost** | Low — runs on standard DSP | Higher — requires NPU or dedicated DNN accelerator |
| **Power consumption** | Lower | Higher (DNN inference adds power draw) |
| **Adaptability** | Fixed algorithms; limited adaptation | Can be updated with new training data and architectures |
| **Marketing narrative** | "Sound as nature intended" | "AI-powered hearing" |

## Why Natural Processing Can Win

1. **Temporal fine structure preservation:** Speech intelligibility depends heavily on temporal cues (voice onset time, formant transitions, amplitude modulation). DNN noise reduction may inadvertently smooth or suppress these cues when applying learned noise masks.

2. **Training data mismatch:** DNN models are trained on synthetic mixtures — if the real-world noise environment differs significantly from training conditions (e.g., 8 spatially distributed speakers), the model may not generalize well.

3. **Over-processing risk:** DNN noise reduction can over-suppress in ways that remove speech information alongside noise, particularly in complex multi-source environments.

4. **Decades of DSP optimization:** Classical algorithms like Widex's have been refined over 30+ years for specific acoustic scenarios; DNN approaches have had ~5 years of refinement.

## Why DNN Still Matters

1. **Non-stationary noise:** DNN models handle rapidly changing noise (traffic, babble) better than classical Wiener filters
2. **Scene classification:** DNN enables automatic detection of acoustic environment and program switching
3. **Scalability:** DNN performance improves with more training data; classical DSP has a fixed ceiling
4. **Complex scenes:** In some multi-talker conditions, DNN beam-forming assistance outperforms classical approaches
5. **Conv-TasNet evidence:** Schulz et al. (2026) showed +5.7 dB for CI users — DNN benefit is strongest for severe hearing loss

## Interpretation and Caveats

- **Manufacturer bias:** The study authors are affiliated with Widex/WS Audiology — the manufacturer of the "winning" device
- **Test conditions matter:** The 8-speaker setup may particularly favor natural processing; simpler noise conditions might show different results
- **Not a universal conclusion:** This does not prove natural processing > DNN in all conditions; it challenges the blanket assumption that DNN always wins
- **Population specificity:** Results may differ for severe vs. moderate hearing loss (Schulz et al. data suggests DNN benefit increases with hearing deficit)

## Implications for the Industry

- **Implementation > architecture:** How well a DNN is trained and deployed matters more than whether DNN is used at all
- **WSA strategic alignment:** The result aligns with WSA's dual-brand strategy — Widex (natural) vs. Signia (DNN-enhanced), allowing WSA to serve both preference segments
- **Clinical evidence gap:** More independent comparative studies needed across different noise conditions and hearing loss severities
- **Hybrid approaches:** The future may combine natural temporal preservation with targeted DNN enhancement (rather than applying DNN globally)

## Related Pages
- [[dnn-in-hearing-aids]] — History and current state of DNN in hearing aids
- [[speech-enhancement-neural-networks]] — Architecture details for DNN speech enhancement
- [[ws-audiology-signia]] — Manufacturer of both Widex (natural) and Signia (DNN) brands
- [[on-device-ml-hearing-aids]] — Compute constraints that shape DNN vs. DSP tradeoffs
- [[ai-hearing-aid-platforms-2026]] — Platform comparison including Widex approach

## Sources
- [Korhonen et al. — Natural Processing vs AI in Speech-in-Noise](../../sources/korhonen-natural-vs-dnn-hearing-aids-april-2026.md) — 29 adults, 5 HAs, Widex Allure outperformed 4 DNN competitors by up to 8.5 dB SNR
