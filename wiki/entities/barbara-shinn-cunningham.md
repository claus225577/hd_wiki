---
title: Barbara Shinn-Cunningham
type: entity
created: 2026-06-24
updated: 2026-06-24
sources: [vcca-2026-main-programme-june-2026.md, vcca2026-conference.md]
related: [../concepts/auditory-attention-decoding.md, ../concepts/lalm-selective-auditory-attention.md, ../concepts/turn-taking-prediction-hearing-ai.md, ../concepts/dyadic-interaction-preservation.md, ../concepts/communication-accessibility-metric.md, vcca-computational-audiology.md]
tags: [person, researcher, cmu, carnegie-mellon, neuroscientist, auditory-attention, cocktail-party, prediction, vcca-2026-keynote, neuroscience-institute]
---

# Barbara Shinn-Cunningham

Director of the **Neuroscience Institute at Carnegie Mellon University**, with a long-running research programme on **auditory attention** in complex listening environments — the neural and behavioural mechanisms by which listeners select one voice from many in cocktail-party scenes.

## 2026 Recognition

**VCCA 2026 Day 1 Keynote (Jun 25, 2026):** *"Hijacking and helping auditory attention: How interruptions and prediction shape everyday communication."*

The framing — *hijacking* (interruptions that drag attention against the listener's intent) and *helping* (prediction that pre-allocates attention to expected content) — names two distinct levers on the same attention substrate. *Hijacking* maps onto the multi-party-conversation / interruption case that turn-taking prediction and dyadic-interaction-preservation work has been operationalising on the ML side ([[../concepts/turn-taking-prediction-hearing-ai]], [[../concepts/dyadic-interaction-preservation]]). *Helping* maps onto the predictive-attention / pre-cued-listening case that closed-loop AAD and brain-aligned-foundation-models work has been operationalising ([[../concepts/auditory-attention-decoding]], [[../concepts/lalm-selective-auditory-attention]]).

## Structural Contributions to the Field

### 1. The cocktail-party / auditory-attention programme

Three decades of research establishing how the auditory system selects, sustains, and switches attention across simultaneous talkers. Key contributions include:
- Behavioural and neural measurement of attentional capture by unexpected sounds.
- Object-based theories of auditory attention — attention selects *streams* (perceptual objects), not raw acoustic features.
- The role of spatial cues, voice characteristics, and semantic prediction in attentional selection.

### 2. Bridging cognitive neuroscience and hearing-care engineering

Long-running advocacy that the cognitive neuroscience of attention is directly relevant to hearing-aid design — that the lived experience of difficulty in noise is fundamentally an attentional, not just acoustic, problem. This framing has been the intellectual precursor to the modern AAD / neuro-steered-hearing-aid programme.

### 3. CMU Neuroscience Institute leadership

As director of the Neuroscience Institute at Carnegie Mellon, anchors a substantial computational-neuroscience programme that sits at the intersection of cognitive neuroscience, ML, and engineering — exactly the substrate the AAD-on-hearing-aid programme depends on.

## Why This Matters for Hearing AI / Data Science

### Attention is the missing variable between signal and outcome

The hearing-AI optimisation stack measures signal (PESQ / STOI / HASPI), lexical content (WER), and increasingly neural attention (AAD). Shinn-Cunningham's framework provides the *cognitive-neuroscience grounding* for the attention layer: what counts as a valid attentional capture event (hijacking) vs a valid attentional pre-allocation (helping), and how both vary with listener state and context.

### Prediction as a measurable hearing-AI substrate

The "prediction shape[s] everyday communication" framing maps directly onto the speech-foundation-model / brain-aligned-loss programmes that have been emerging through 2026 (Whisper-ECoG layer selection, FAConformer's predictive AAD, the closed-loop ML cluster). Shinn-Cunningham's neural-mechanism work supplies the substrate against which these ML systems' predictive performance can be compared to human performance.

### Interruptions as a real-world failure mode the metric stack does not yet capture

The "hijacking" half of the talk names a failure mode the current SE evaluation stack has no metric for: how much an unexpected sound drags attention away from a target the listener cares about. This is structurally adjacent to the dyadic-interaction-preservation diagnostic (Nilabh & Sharma 2026 speaker-switch test) and to the multi-party turn-taking-prediction line (ModeratorLM 2026) — but Shinn-Cunningham's framing supplies the neural-mechanism layer underneath.

## Related Pages

- [[../concepts/auditory-attention-decoding]] — AAD operationalises the neural-attention substrate Shinn-Cunningham's basic-science programme characterises.
- [[../concepts/lalm-selective-auditory-attention]] — LALM benchmark for selective auditory attention as the foundation-model-side analogue.
- [[../concepts/turn-taking-prediction-hearing-ai]] — The "prediction" half of the keynote as a hearing-AI primitive.
- [[../concepts/dyadic-interaction-preservation]] — The "hijacking" half of the keynote as a measurable failure mode.
- [[../concepts/communication-accessibility-metric]] — Where attentional capture / prediction sits in the missing interactional-metric layer.
- [[vcca-computational-audiology]] — VCCA 2026 keynote context.

## Sources

- [VCCA 2026 Main Programme](../../sources/vcca-2026-main-programme-june-2026.md) — Day 1 keynote.
- [VCCA 2026 Conference Overview](../../sources/vcca2026-conference.md) — Programme structure.
