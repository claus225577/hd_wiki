---
title: Anthropic Releases Claude Opus 4.8 — user-controlled "effort" slider and dynamic workflows
type: source
source_type: company-announcement
publisher: Anthropic / TechCrunch / Axios / 9to5Mac / MacRumors / GitHub Changelog
date_published: 2026-05-28
date_accessed: 2026-06-01
url: https://www.anthropic.com/news/claude-opus-4-8
secondary_url: https://techcrunch.com/2026/05/28/anthropic-releases-opus-4-8-with-new-dynamic-workflow-tool/
tags: [anthropic, claude, opus-4-8, effort-controls, dynamic-workflows, llm, agentic, frontier-model, listening-effort, karpathy]
---

# Claude Opus 4.8 — Effort Controls & Dynamic Workflows (May 28, 2026)

Anthropic released **Claude Opus 4.8** on May 28, 2026, nine days after Andrej Karpathy joined Anthropic's pre-training team under Nick Joseph.

## What Shipped

### User-controlled "effort" parameter
- Users on claude.ai (and via API) can now **dial how much compute Claude spends on a task**.
- **Fast mode:** 2.5× the previous speed; 3× cheaper than prior Opus pricing for the same operating point.
- **High-effort mode (default):** Spends comparable tokens to Opus 4.7 on coding tasks but with materially better performance.
- The cost / quality / latency trade-off is surfaced **explicitly to the user** as a control, not hidden in the routing layer.

### Dynamic workflows (Claude Code)
- New "dynamic workflows" feature: lets Claude Code tackle very large-scale problems via hundreds of parallel sub-agents coordinated mid-task.
- Messages API now accepts **system entries inside the messages array** — developers can update Claude's instructions mid-task.

### Benchmarks (per Anthropic)
- Agentic coding: 64.3% → 69.2%
- Multidisciplinary reasoning with tools: 54.7% → 57.9%
- Agentic computer use: 82.8% → 83.4%
- Knowledge work score: 1753 → 1890

### Honesty / calibration claims
- Anthropic describes 4.8 as having "sharper judgement, more honesty about its progress, and the ability to work independently for longer than its predecessors."
- Early testers report 4.8 is **more likely to flag uncertainties** and **less likely to make unsupported claims** vs. 4.7.

## Pricing & Availability

- Same price as Opus 4.7: $5/M input, $25/M output (full effort).
- Available across Claude products, API, Amazon Bedrock, Google Vertex AI, Microsoft Foundry, GitHub Copilot.

## Strategic Significance

This is the first major frontier-LLM release to ship **explicit, user-controlled cognitive-effort dosing** as a first-class product feature — not a backend cost-routing decision.

The framing matters: prior models hid effort behind opaque routing (Claude's "extended thinking" tag, OpenAI's reasoning models). 4.8 makes the effort/cost/quality trade-off a UI primitive the user directly controls.

## Relevance to Hearing-Aid AI

The LLM industry has just operationalized **effort as a user-controlled, continuous, cost-trade-off-aware dosing parameter**. This is the construct hearing-care audiology has been arguing should be the primary objective function for ~30 years (Pichora-Fuller FUEL framework, 2016; ISA Aram Glorig Award at WCA 2026 Seoul, May 26 2026).

Concrete parallels:

| LLM (Claude 4.8) | Hearing-aid analog (today) |
|------------------|----------------------------|
| Continuous effort slider | Binary AI on/off (Widex Allure Clarity Boost button, May 20 2026) |
| Cost trade-off explicit | Battery cost implicit / hidden |
| User controls dosing | Adaptive routing decides |
| Effort measurable in tokens | Listening effort not first-class measured |

The hearing-aid product equivalent — "high-effort mode for 30 min in a noisy restaurant, low-effort default elsewhere, battery cost surfaced honestly" — is conceptually obvious and operationally absent.

## Open Questions for Hearing-Care Roadmaps

1. Should the next premium hearing aid's UX expose a continuous effort slider (battery-vs-clarity) rather than scene presets or binary AI toggles?
2. What is the hearing-aid analog of "tokens spent" — battery joules per minute? DNN MAC ops? On-chip vs. paired-phone offload share?
3. Does an effort slider require a real-time listening-effort estimate on the device? Pupillometry from earbud sensors? EEG from in-ear electrodes? Behavioral proxies?
4. Does the regulatory frame (FDA 510(k) / EU MDR) treat a user-adjustable processing intensity as a class-changing variable, or as an existing settings analog?

## Karpathy Context

Karpathy joined Anthropic on May 19 to lead a new pre-training team focused on using Claude to accelerate pre-training research. 4.8 is the first model release post-Karpathy. The "effort dosing" framing aligns with his public commentary on the field needing to make compute / quality trade-offs legible to users rather than hide them in router logic.
