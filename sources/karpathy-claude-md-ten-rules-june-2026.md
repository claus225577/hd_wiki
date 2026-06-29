---
title: "Karpathy CLAUDE.md Grows to Ten Rules — New Self-Check Protocol for AI Coding Loops"
url: https://www.techtimes.com/articles/319214/20260628/karpathy-claudemd-grows-ten-rules-new-self-check-protocol-ai-coding-loops.htm
date: 2026-06-28
type: article
tags: [karpathy, claude-md, ai-agents, agentic-engineering, named-failure-modes, ml-ops, verification, self-check]
---

# Karpathy CLAUDE.md Grows to Ten Rules

## Provenance and authenticity
- A six-rule extension to the four-rule Forrest Chang / andrej-karpathy-skills template started circulating on X on Friday 27 Jun 2026.
- Attributed to **Andrej Karpathy** via a contact on his pre-training team at Anthropic (he joined Anthropic ~5 weeks earlier — May 19 2026).
- Authenticity has **not been independently confirmed**. Karpathy has not publicly commented.
- Reported by Tech Times on 28 Jun 2026; readers told to treat it as practitioner-sourced guidance, not as confirmed canon.
- Original four-rule template: `forrestchang/andrej-karpathy-skills` and `multica-ai/andrej-karpathy-skills` (~200k combined GitHub stars by late June 2026).

## The six new rules (the additions over the original four)
- **Verification before fixing.** No "fix" without a passing test that demonstrates the fix. The fix must change the test result, not just the symptom.
- **Debugging discipline.** Reproduce, isolate, then change. Don't add print statements as the first reflex.
- **Dependency hygiene.** Don't import what you don't use; don't add what you can compute.
- **Three of the named failure modes** are encoded as recognition rules — the agent should recognise the pattern in its own loop and abort.

## The four named failure modes
- **Kitchen Sink.** Piling on options/features/losses/checks without ablating; the number goes up but nobody knows why.
- **Wrong Abstraction.** Building a clean abstraction layer over the part of the stack that should stay messy; the abstraction hides the actual bug-prone surface.
- **Optimistic Path.** Declaring victory on the easy case (the canonical test set, the happy path) and ignoring the field/edge cases where the change actually breaks.
- **Runaway Refactor.** A small change cascades into rewriting adjacent code that wasn't broken; integration tests start failing in unrelated subsystems.

## Why the rules matter more in agent loops
- A verification rule that requires a passing test before declaring a bug "fixed" carries far more weight when the loop runs for hours without human review than when a developer is watching every step.
- Named failure modes give the loop a vocabulary for recognising when it is about to compound a mistake rather than correct one.
- Operationalises the Karpathy line: *"You can outsource your thinking, but not your understanding."*

## Relevance to Hearing + AI

### Hearing-aid ML R&D as agent loops
The four named failure modes map onto hearing-aid SE / AGC / beamforming R&D pipelines:
- **Kitchen Sink** = adding a third multi-resolution STFT loss on top of perceptual loss and differentiable-cochlear loss without ablating.
- **Wrong Abstraction** = wrapping the chip-vendor SDK in a clean OOP layer so the SE engineer never sees the int8 quantisation boundary.
- **Optimistic Path** = STOI improves on VoiceBank-DEMAND, declare victory, wearer commute recordings sound worse.
- **Runaway Refactor** = SE branch needs a tensor shape change; three weeks later the WDRC fitting interface has been rewritten.

### Verification substrate in hearing aids is unusually strong
- HASPIv2 (objective intelligibility).
- The new Sabin et al. (arXiv:2606.26342, 24 Jun 2026) listener-rated benchmark (Whisper + MLP, 0.92 correlation vs HASPIv2's 0.83).
- In-situ wearer telemetry from connected hearing aids.
- Behavioural-audiometry probes from the differentiable-cochlea / DAL program (arXiv:2606.04103).
- Implication: HA teams have more verification surface than most ML applications, but typically optimise the surrogate the agent watches, not the metric the wearer feels.

## Relevance to existing wiki concepts
- `concepts/agentic-engineering-hearing-rd` — direct extension; add ten-rule template + named failure modes as a new section.
- `concepts/closed-loop-data-flywheel` — verification-before-fix as the closed-loop check.
- `concepts/product-level-ha-listener-rated-evaluation` — Sabin et al. benchmark as the Optimistic-Path detector.
- `concepts/differentiable-cochlear-models` — behavioural-audiometry probes as one verification surface.
