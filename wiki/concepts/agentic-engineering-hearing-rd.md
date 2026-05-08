---
title: Agentic Engineering in Hearing R&D
type: concept
created: 2026-05-06
updated: 2026-05-06
sources: [karpathy-sequoia-ascent-2026.md, karpathy-idea-files-april-2026.md, karpathy-claude-md-template-viral-april-2026.md]
related: [../syntheses/ai-understanding-gap-hearing-industry.md, ../concepts/dnn-in-hearing-aids.md, ../concepts/on-device-ml-hearing-aids.md, ../concepts/model-context-protocol.md, ../syntheses/hearing-ai-research-landscape-2025.md]
tags: [agentic-engineering, software-3, karpathy, llm-agents, r-and-d, taste, understanding]
---

# Agentic Engineering in Hearing R&D

Agentic engineering — the Software 3.0 paradigm Karpathy outlined at Sequoia AI Ascent 2026 — applied to the constrained, high-stakes domain of hearing-aid and audiology research.

## Definition

In Karpathy's framing:
- **Software 1.0:** explicitly written code
- **Software 2.0:** trained neural networks
- **Software 3.0:** prompting an LLM interpreter; natural language as the programming surface

Agentic engineering is the human role in Software 3.0: orchestrating LLM agents that handle execution while the engineer concentrates on *taste, judgment, and definition of what is worth building*.

## Why Hearing R&D Is a Strong Fit

- **Bounded search spaces.** Compression curves, beamformer parameters, fitting protocols, DSP block configurations — all closed-form, well-instrumented spaces ideal for autonomous experimentation (see also: Karpathy's autoresearch).
- **Measurable objectives.** SII, intelligibility scores, latency budgets, mW power envelopes are computable. Reward signals are clean enough for agentic loops.
- **High cycle count.** Each chip generation runs many ablations; LLM agents can drive parameter sweeps and write up the results.
- **Regulatory boilerplate.** AI/ML SaMD submissions, predetermined change control plans, and clinical study reports are template-rich — precisely the kind of work agents accelerate.

## What Agents Can Already Do (May 2026)

- Drive grid/random search over compression and noise-reduction parameters
- Run audibility simulation pipelines and summarise results
- Cross-reference candidate algorithms against existing patent / literature corpora
- Draft clinical study writeups, IRB submissions, and 510(k) sections
- Produce first drafts of regulatory documentation aligned to FDA AI/ML guidance

## What Still Requires Human Understanding

This is the operational meaning of *"you can outsource your thinking, but not your understanding"* in hearing R&D:

- Recognising that a 0.5 dB SII improvement is an artefact of training-set leakage of impulsive transients
- Knowing which audiogram is the *wrong* dataset to validate on for a given pathology
- Catching when an agent's "improvement" violates a real-chip bandwidth or power budget
- Asking why a model degrades at 70 dB SPL but not 65 — and recognising the loudness-recruitment fingerprint
- Sensing when a benchmark gain will not translate to a fitted patient in a real living room

These judgments are built from clinical exposure, hand-coding signal processing primitives, listening-test experience, and breaking your own models.

## Implications for Sonova / Industry R&D

- The competitive moat shifts from "who has the most ML headcount" to "who has the most *calibrated* hearing-domain judgment paired with effective agent infrastructure"
- Mid-career hearing-aid DSP engineers and audiologists become disproportionately valuable as taste arbiters
- Junior training paths must be redesigned: deep clinical/DSP exposure first, agent orchestration second — otherwise the next generation has no calibrated priors to evaluate agent output
- Internal tooling investment — wiki-style knowledge bases, idea files, MCP-style tool servers exposing fitting databases — becomes infrastructure, not optional

## Open Questions

- What is the right "taste curriculum" for a 2026-vintage hearing-aid scientist?
- How should hearing companies structure agent oversight for regulatory-grade work?
- Can audiologist domain expertise be captured into idea files that guide agentic fitting systems at scale?
- Where is agentic engineering already net-negative in hearing R&D today (e.g. ambiguous clinical contexts where false confidence is dangerous)?

## Related Pages

- [[../syntheses/ai-understanding-gap-hearing-industry]] — The understanding gap on the consumer side; this page is the engineering-side counterpart
- [[dnn-in-hearing-aids]] — What AI actually does in hearing aids today
- [[on-device-ml-hearing-aids]] — Edge constraints that bound what agents can suggest
- [[model-context-protocol]] — Tool infrastructure that makes hearing-domain agents practical
- [[../syntheses/hearing-ai-research-landscape-2025]] — Broader landscape this concept fits into

## Sources

- [Karpathy — Sequoia AI Ascent 2026](../../sources/karpathy-sequoia-ascent-2026.md) — primary source for the Software 3.0 / understanding-vs-thinking framing
- [Karpathy idea files](../../sources/karpathy-idea-files-april-2026.md) — knowledge specifications for agents
- [Karpathy CLAUDE.md template](../../sources/karpathy-claude-md-template-viral-april-2026.md) — agent behavioural guardrails
