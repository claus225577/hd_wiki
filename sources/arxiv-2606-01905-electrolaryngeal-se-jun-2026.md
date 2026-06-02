---
title: Advancing Electrolaryngeal Speech Enhancement Through Speech-Text Representation Learning
type: source
source_type: arxiv-preprint
publisher: arXiv (eess.AS)
date_published: 2026-06-02
date_accessed: 2026-06-02
url: https://arxiv.org/abs/2606.01905
arxiv_id: 2606.01905
authors: [Authors TBD on full-text read]
tags: [speech-enhancement, voice-conversion, seq2seq, electrolaryngeal, joint-modality, pathological-speech, foundation-models]
---

# Advancing Electrolaryngeal Speech Enhancement Through Speech-Text Representation Learning

Sequence-to-sequence voice conversion framework that jointly learns **speech and text representations** to reconstruct electrolaryngeal (EL) speech — the harsh, monotone, low-intelligibility speech produced by laryngectomees using an electromechanical voice prosthesis.

## What the Paper Does

- Integrates speech and text representations inside a seq2seq voice-conversion model trained to map EL speech → natural target-voice speech.
- Joint-modality learning addresses the four defining defects of EL speech: severe distortion, limited phonetic variation, unnatural prosody, temporal shifts.
- Targets improved mapping and reconstruction quality vs prior EL-SE work that operated on audio features alone.

## Why It Matters for Hearing-Care AI

While EL-SE is not mainstream HA speech enhancement, the architectural pattern is portable to **severely degraded pathological speech** more broadly — relevant for the HA-wearer subpopulation with co-morbid voice disorders (presbylaryngis, spasmodic dysphonia, post-stroke dysarthria).

More importantly, the paper is another data point in a **two-week cluster** of work — alongside Nakazawa CPC3 fusion (frame-aligned WavLM+Canary mid-fusion, May 27), MindVoice (frozen TTS backbone for non-invasive brain-to-speech, May 29), and Breaking the Pair (interaction-preservation evaluation, June 1) — reinforcing a common recipe:

> **Frozen pretrained backbone (speech or text or both) + small learned bridge.**

The lever for hearing-care speech reconstruction in 2026 has visibly stopped being "build a better custom encoder" and has become "fuse stable foundation-model representations and learn the bridge."

## Open Questions

1. Does the joint speech-text representation transfer to HA-wearer use cases where text-side priors come from companion-app context (calendar, conversation history)?
2. What is the latency profile? EL conversion is offline-friendly; HA speech enhancement is hard-real-time at sub-10 ms — the joint-modality recipe needs latency stripping before HA deployment.
3. Could the same architecture serve as a benchmark for dysarthric-speech HA SE, an under-studied use case?

## Related Threads

- `foundation-model-fusion-speech.md` — same architectural recipe at a different surface.
- `non-invasive-brain-to-speech.md` — same recipe applied to biosignal input.
- `linguistic-hallucination-speech-enhancement.md` — generative-SE risks the joint-modality framing inherits.
- `dyadic-interaction-preservation.md` — interaction-preservation evaluation axis that would apply if this were deployed in a HA dyad context.
