---
title: User-Controlled On-Demand AI in Hearing Aids
type: concept
created: 2026-05-21
updated: 2026-05-21
sources: [widex-allure-ai-may-2026.md, korhonen-natural-vs-dnn-hearing-aids-april-2026.md, wsa-sound-preference-program-april-2026.md]
related: [../entities/ws-audiology-signia.md, dnn-in-hearing-aids.md, dnn-architectures-hearing-aids.md, closed-loop-data-flywheel.md, on-device-ml-hearing-aids.md, ../comparisons/dnn-vs-natural-processing.md, hearing-aid-chip-architectures.md]
tags: [on-demand-ai, user-control, clarity-boost, widex, hybrid-architecture, dedicated-co-processor, labeled-telemetry, scene-labels, hearing-aids]
---

# User-Controlled On-Demand AI in Hearing Aids

A design pattern in which a hearing aid runs a classical (non-DNN) processing pipeline by default and engages a dedicated AI co-processor **only when the wearer explicitly enables it**, typically via a physical button or app toggle. The wearer becomes the gate on AI inference, rather than an always-on scene classifier.

This page treats the pattern as both a **product architecture** and a **labeled-training-signal generator**. The latter is the structurally novel piece — every button press is a labeled scene event of the form *"this was a moment that warranted AI processing, in the wearer's own judgement"* tied to acoustic features, the scene-classifier state, time, and streaming source.

## Reference Implementation

**Widex Allure AI RIC (May 20, 2026).** First commercial implementation. Architecture:

- **Default path:** Widex PureSound with ZeroDelay — classical "natural sound" pipeline; temporal-fidelity-preserving DSP, no DNN.
- **On-demand path:** "Clarity Boost" engaged via user button; dedicated AI co-processor on the W1 chip runs audio-domain neural network.
- **Claimed performance when engaged:** up to 6 dB higher output SNR vs competitor AI hearing aids (manufacturer-published).
- **Battery budget:** 32 h total runtime including up to 6 h of AI-on use or streaming — i.e., the AI path is **explicitly power-budgeted as the minority of the day**, not the dominant operating mode.
- See [widex-allure-ai-may-2026 source](../../sources/widex-allure-ai-may-2026.md).

## Counter-Positioning Against Always-On AI

The four other Big Six AI flagships in 2026 are all **always-on**:

| OEM | Flagship | AI mode |
|-----|----------|---------|
| Sonova / Phonak | Sphere Infinio | Always-on; DEEPSONIC co-processor |
| GN / ReSound | Vivia | Always-on; 360+DNN |
| Demant / Oticon | Zeal / Intent | Always-on; DNN 2.0 on Sirius single-chip |
| Starkey | Omega AI | Always-on |
| WS Audiology / Widex | **Allure AI RIC** | **User-toggled (Clarity Boost)** |

This is a deliberate counter-positioning move. WS Audiology runs a dual-brand strategy — Signia (DNN-enhanced) and Widex (PureSound natural) — and the Allure AI RIC is the **bridge product** that refuses to pick a side: classical default, AI when the wearer asks for it. See [[../entities/ws-audiology-signia]].

This also stacks coherently with two earlier WSA datapoints:
- The **WSA Sound Preference Program (Apr 2026)** found that ~40% of wearers have stable, consistent preferences for either "natural" or "enhanced" sound.
- **Korhonen et al. (Apr 2026)** showed the non-AI Widex Allure outperformed 4 DNN-based competitors by up to 8.5 dB SNR on speech-in-noise for moderate hearing loss.

The on-demand AI pattern is the architectural expression of those two findings: ship the natural path as the default, but make the AI path one button press away when the user disagrees with the default in a given scene.

## Why On-Demand Generates Structurally Better Telemetry

An always-on AI system that adapts its behavior via scene classification is **its own oracle**: it both decides what scene it is in and what to do about it. The training signal is largely synthesized (paired clean / noisy mixtures) and the in-field telemetry is heavily entangled with the model's own decisions.

A user-controlled AI button breaks that loop:

- **Every press is a labeled scene event.** The wearer has acted as a real-world annotator, declaring this scene worth the extra power, latency, and processing artefacts that AI mode brings. Pressing the button is a **positive label**; not pressing it in a similar scene is an **implicit negative**.
- **The labels are paired with the full acoustic feature vector** at the moment of the press — scene-classifier output, mic-level acoustics, time of day, streaming source, recent button history.
- **The classifier's threshold is not the only decision boundary** any more. The wearer's threshold is a second, behavioural one — and the gap between the two becomes a measurable error signal.
- **Negative-class scenes are reachable.** Always-on AI systems rarely see "scenes where the user did not want AI" because they never offered the alternative. A toggleable system surfaces the negative class continuously.

This is structurally analogous to the labeled vs. unlabeled distinction in classical ML: an always-on system has lots of audio but no labels of wearer intent; a toggle system attaches a binary intent label to a subset of every wearing day.

The implication is that, **if the OEM closes the loop**, a toggle-architecture device can produce a richer personalization dataset per wearer-hour than an always-on equivalent — not because it sees more audio, but because it sees labels.

## The Compass Cloud 2.0 Connection

Widex announced the Allure AI RIC alongside **Compass Cloud 2.0**, a cloud-based fitting platform with Adaptation Manager, SmartSpeak, expanded Data Logging, Sound Class Adjustments, Transfer Settings, and 99.9%+ uptime. This is the platform half of the architecture.

The button-press telemetry described above is only useful if it can be **collected, versioned, and fed into a retraining loop**. Compass Cloud 2.0 is the candidate substrate. As of launch, Widex has not publicly confirmed that button-press telemetry will be surfaced into the cloud as a personalization or retraining signal — but the architecture makes it natural.

See [[closed-loop-data-flywheel]] for the broader flywheel framing.

## Tradeoffs and Open Questions

- **Cognitive load.** Asking the wearer to manage an AI button is itself a feature design risk; many wearers will never press it. Whether the labeled-telemetry gain outweighs the silent-majority who never engage is an open empirical question.
- **Power-budget honesty.** The "32 h total / 6 h AI-on" framing is honest about AI processing as a power-expensive minority mode. This stands in contrast to always-on AI marketing that elides the integrated power cost.
- **Scene-class coverage.** Wearers will press the button most in scenes where they currently feel underserved by the natural path. The label distribution will be heavily skewed toward those scenes — a feature for personalization, but a bias for population-level retraining.
- **Comparability to always-on benchmarks.** Performance benchmarks comparing the Allure AI RIC's Clarity Boost mode to always-on AI competitors are manufacturer-published. Independent replication pending.
- **Generalization beyond Widex.** Whether other OEMs adopt the pattern (or treat it as a Widex-specific differentiation move) will determine whether on-demand AI becomes a recognised category alongside always-on.

## Implications for Data Science

- **Annotation budget reframed.** The on-demand button is, in effect, a **zero-cost annotation interface** running 24/7 on every device. The annotation tooling problem the field has been working on (label real-world acoustic scenes for HA training) is partially solved by the product design itself.
- **Negative-class mining.** The non-press scenes are negative-class examples of "AI not needed here". Combined with sampled acoustic features, they could provide the kind of contrastive supervision that synthetic mixtures cannot.
- **Personalization at the wearer level.** Per-wearer button-press history can train per-wearer Clarity Boost defaults — a thin personalization layer above the population-level model.
- **Bridge to AAD.** Where attention decoding (see [[../concepts/auditory-attention-decoding]]) provides a **continuous** intent signal from biology, the AI button provides a **discrete** intent signal from behavior. Both are wearer-intent telemetry, at different sampling rates.

## Related Pages
- [[../entities/ws-audiology-signia]] — Reference manufacturer; dual-brand strategy and bridge product
- [[dnn-in-hearing-aids]] — Always-on DNN baseline being counter-positioned against
- [[dnn-architectures-hearing-aids]] — Dedicated AI co-processor as architectural pattern
- [[closed-loop-data-flywheel]] — Where button-press telemetry feeds back into product development
- [[on-device-ml-hearing-aids]] — Power-budget context for AI-on as a minority mode
- [[../comparisons/dnn-vs-natural-processing]] — Natural vs DNN performance evidence that motivates the hybrid approach
- [[hearing-aid-chip-architectures]] — W1 chip + AI co-processor as a chip-level realization

## Sources
- [Widex Allure AI RIC (May 2026)](../../sources/widex-allure-ai-may-2026.md) — Reference implementation; user-toggled Clarity Boost; W1 chip with dedicated AI co-processor; up to 6 dB SNR vs competitor AI HAs; Compass Cloud 2.0 companion platform
- [Korhonen et al. — Natural vs DNN (Apr 2026)](../../sources/korhonen-natural-vs-dnn-hearing-aids-april-2026.md) — Non-AI Widex Allure outperformed 4 DNN competitors by up to 8.5 dB SNR
- [WSA Sound Preference Program (Apr 2026)](../../sources/wsa-sound-preference-program-april-2026.md) — ~40% of wearers show stable natural-vs-enhanced preference, supporting the hybrid-with-user-control design rationale
