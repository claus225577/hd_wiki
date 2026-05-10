---
title: "Virtual Speech Therapist: A Clinician-in-the-Loop AI Speech Therapy Agent"
authors: [Shakeel Sheikh, et al.]
date: 2026-05
arxiv_id: "2605.01101"
url: https://arxiv.org/abs/2605.01101
type: research-paper
tags: [speech-therapy, clinician-in-the-loop, llm-agent, aural-rehabilitation, accessibility, neurotone-adjacent]
---

# Virtual Speech Therapist — Clinician-in-the-Loop AI Agent (Sheikh et al., May 2026)

## Key Extraction

- **Question:** Can an LLM-driven agent administer structured speech therapy with clinician oversight, replicating the cadence and feedback loop of in-person care?
- **Method:** Builds an AI speech therapy agent where an LLM runs the session in real time, but a clinician supervises, edits exercises, and reviews outcomes asynchronously. The architectural pattern is "clinician-in-the-loop" — not autonomous, not pure tele-therapy.
- **Domain:** Primarily speech production / speech therapy; not directly hearing-aid focused.

## Why This Matters for Hearing AI

- **Same architectural pattern as aural rehab.** Neurotone AI's recently-announced thesis is identical: AI-administered structured rehab between fitting and 6-month outcome, with clinician supervision (Brian Taylor was hired specifically to formalize this loop). The Sheikh et al. paper is a peer-reviewable concrete instantiation of the same pattern in an adjacent domain.
- **The 1–6 month gap is the binding constraint.** As Brian Taylor articulated in his Neurotone announcement, audibility on day 1 doesn't translate to communication outcomes — the work happens in the post-fit weeks. AI agents with clinician oversight are the obvious scaling mechanism. Speech therapy is just the first vertical to publish at academic strength.
- **Workforce-shortage compatibility.** With audiologist shortages in 75% of US counties, asynchronous clinician supervision over an AI agent is the only mechanism that doesn't require more clinicians.

## Open Questions

- Does the paper benchmark against fully-autonomous LLM agents, or only vs. clinician-only baselines?
- What's the clinician time-per-patient overhead? The economic case for the loop hinges on this number.
- Generalization to aural rehab specifically — is the listening-fatigue / speech-in-noise rehab content amenable to LLM authoring, or does it need specialized audio tooling?

## Source

arXiv eess.AS, 2605.01101 — https://arxiv.org/abs/2605.01101
