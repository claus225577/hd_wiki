---
title: Medical-Domain Edge LLMs (Hearing-Care Companion Substrate)
type: concept
created: 2026-05-15
updated: 2026-05-15
sources: [qvac-medpsy-edge-medical-llm-may-2026.md, google-gemma-4-open-models-april-2026.md]
related: [small-language-models-edge-ai.md, on-device-ml-hearing-aids.md, digital-therapeutics-tinnitus.md, audiologist-workforce-shortage.md, ../entities/sonova-ag.md, ../entities/google-research.md]
tags: [edge-ai, medical-llm, on-device, companion-app, smartphone, digital-therapeutics, privacy, fda-saMD]
---

# Medical-Domain Edge LLMs

Compact, medical-specialized language models small enough to run fully on a smartphone (no cloud round-trip) yet competitive with much larger general-purpose models on clinical reasoning benchmarks. Distinct from the **on-chip hearing-aid AI** lane: the deployment target here is the **paired phone**, not the device.

## Why This Class Exists Now (May 2026)

Three trends collided:
1. **Open-weight base models** matured (Qwen3, Gemma 4, Llama family).
2. **Quantization** (Q4/Q3, BitNet-style ternary, GGUF) made 4B-class models fit on consumer phones.
3. **Domain-specialization pipelines** (SFT + RL on medical Q&A; e.g. AlphaMedQA) push much smaller models past general-purpose giants on closed-ended medical tasks.

QVAC MedPsy (May 7, 2026) is the cleanest current example: a 4B model that beats Google MedGemma-27B on average across MedQA-USMLE / MedMCQA / MMLU Health / MMLU-Pro Health / MedXpertQA / AfriMedQA / PubMedQA at ~7× smaller parameter count.

## What This Unlocks for Hearing Care

The hearing aid chip itself remains far too small to host a model in this class (1+ GB working memory). The relevant deployment surface is the **paired smartphone**, where every major OEM already runs a companion app.

Historically the companion app has been a thin shell — fitting controls, environment selectors, self-tests, a few coaching screens. Anything richer (counseling, education, conversational triage) required:
- **cloud LLMs** — slow regulatory / privacy approval under EU MDR and FDA SaMD; data-residency complications across markets, or
- **rule-based scripts** — no personalization; brittle to user variation.

A medical-domain edge LLM collapses both barriers in one drop.

### Concrete Workflows

| Workflow | Why on-device LLM helps |
|---|---|
| Tinnitus iCBT counseling | Adherence (see [[digital-therapeutics-tinnitus]]) is partly a trust problem; "no cloud" is a real product feature |
| Plain-language audiogram explanation | At fitting moment; literacy- and language-adaptive |
| Post-fit Q&A | Replaces the most repetitive 30 minutes of the audiologist visit |
| Conversational triage | Audiologist-shortage geographies (see [[audiologist-workforce-shortage]]) |
| First-fit onboarding | Adapts to user's literacy, language, prior device experience |
| Care-partner counselling | Multi-user data schema (see [[care-partner-dyad-models]]) |

## What Shifts from Compute to Domain Alignment

The bottleneck in productizing this class for hearing care is **not** compute or weights — both are now commodity. It is **hearing-care domain alignment**:

- General medicine has decades of structured Q&A corpora (MedQA, USMLE, MedMCQA). Audiology has a fraction of that — fitting protocols, patient counseling scripts, manufacturer documentation are mostly unstructured PDFs.
- Tinnitus iCBT scripts are protocolized (CBT manual format) and could anchor a fine-tune.
- The interesting research direction: **synthetic Q&A generation from manufacturer fitting guides + clinical practice guidelines** as a curriculum stage on top of MedPsy-class base models.

## Risks and Open Questions

- **Hallucination in medical advice** — closed-ended benchmarks reward correctness; open-ended counseling rewards calibrated uncertainty. HealthBench Hard helps but is not hearing-specific.
- **Liability framing** — companion-app advice that crosses the SaMD threshold pulls the manufacturer into a regulated path they may not want for the app layer.
- **Update cadence** — base model improvements ship monthly; hearing-care fine-tune cycles must keep pace.
- **Multilingual coverage** — MedPsy benchmark mix includes AfriMedQA but most evaluation is English; hearing-care companion apps need 20+ languages.
- **Voice modality gap** — MedPsy is text-only. The natural hearing-care UX is voice. Bridging requires Voxtral- / Liquid-LFM-class audio in/out alongside.

## Related Pages

- [[small-language-models-edge-ai]] — Broader SLM landscape; MedPsy is a domain-specialized member
- [[on-device-ml-hearing-aids]] — Sister concept for the on-chip lane
- [[digital-therapeutics-tinnitus]] — Adherence problem MedPsy could partially address
- [[audiologist-workforce-shortage]] — Conversational triage as a workforce-gap mitigation
- [[../entities/sonova-ag]] — Owns SilentCloud; companion-app substrate strategically central
- [[../entities/google-research]] — Gemma 4 / Gemini Nano 4 are the baseline this class compares against

## Sources

- [QVAC MedPsy edge medical LLM (May 2026)](../../sources/qvac-medpsy-edge-medical-llm-may-2026.md) — 4B model beating MedGemma-27B at 7× smaller; Apache 2.0; runs on smartphone in ~2.7 GB
- [Google Gemma 4 open models (April 2026)](../../sources/google-gemma-4-open-models-april-2026.md) — Multimodal base from which medical specializations like MedGemma are built
