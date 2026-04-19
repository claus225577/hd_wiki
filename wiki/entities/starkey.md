---
title: Starkey
type: entity
created: 2026-04-15
updated: 2026-04-17
sources: [starkey-omega-ai-launch-2025.md, starkey-cto-bhowmik-aimbe-april-2026.md]
related: [sonova-ag.md, demant-oticon.md, ../concepts/on-device-ml-hearing-aids.md, apple-hearing-features.md]
tags: [company, manufacturer, usa, health-monitoring, fall-detection, genesis-ai, npu, dnn, achin-bhowmik, aimbe]
---

# Starkey

American hearing aid manufacturer, headquartered in Eden Prairie, Minnesota. The only major hearing aid manufacturer still based in the US. Privately held. Differentiating through health and fitness tracking features embedded in hearing aids.

## Products
- **Starkey Omega AI** — Latest flagship platform (Oct 2025); G3 Gen AI Neuro Processor with integrated NPU
- **Genesis AI** — Previous flagship platform (health + hearing integration)
- **Evolv AI** — Earlier generation

## Genesis AI Platform

### Health & Safety Features
**Fall Detection (First and Only in Hearing Aids)**
- Uses **3D motion sensors** (3-axis accelerometer/gyroscope) to detect falls
- Automatic alert to designated contacts when a fall is detected
- One of the most clinically meaningful health monitoring features in a hearing device — falls are a leading cause of injury in older adults

**Health & Fitness Tracking**
- **Activity differentiation**: distinguishes walks, runs, biking, and aerobic activity (not just step count)
- Tracks minutes of physical activity per type
- **Hear Share app** — Companion app for sharing health metrics, hearing insights, and progress with family/caregivers

### Hardware
- **51-hour battery life** (RIC RT form factor) — among the longest in the rechargeable RIC category

### Hearing AI Features
- **Edge AI** — Starkey's brand for on-device ML capabilities
- **Edge Mode** — On-demand acoustic optimization triggered by user (manual ML inference call)
- Automatic environment classification and adaptation

## Strategic Position
- Positioned as a **health tech company that makes hearing aids**, not just a hearing aid company
- Most aggressive push into health monitoring features beyond hearing among the Big 6 manufacturers
- Fall detection is a genuine clinical differentiator — no direct competitor has matched this
- Privately held (unlike Sonova, Demant, GN Group, WSA — all publicly traded or PE-backed)
- **Starkey Hearing Foundation** — Strong philanthropic brand; distributes hearing aids globally, generates goodwill and brand recognition

## How Starkey Fits the Broader AI Hearing Landscape
While competitors (Phonak, Oticon, ReSound) focus primarily on AI for audio/speech quality, Starkey's AI investments are split between:
1. Traditional hearing enhancement (Edge AI, scene classification)
2. Health sensing (fall detection, activity tracking, biometrics)

This creates a different value proposition — particularly for older adults, caregivers, and healthcare systems that want hearing aids to serve as a continuous health monitoring platform.

## Data Science Relevance
- Fall detection: accelerometer + ML classification on-device (supervised learning, activity recognition domain)
- Activity type differentiation (walk vs. run vs. bike vs. aerobic): richer feature engineering than simple step count
- Hear Share creates a social/caregiver data loop — health trends shared with family members
- Edge Mode is notable UX: user explicitly triggers an ML optimization call, providing implicit feedback signal on when existing models aren't sufficient
- Multi-modal health sensing opens hearing aids as a platform for longitudinal health data collection

## Leadership

### Achin Bhowmik — CTO & EVP of Engineering
- **Background:** Previously VP at Intel (perceptual computing division)
- **AIMBE Fellowship (April 2026):** Inducted into the American Institute for Medical and Biological Engineering College of Fellows — recognition of AI-driven hearing innovation leadership
- **Significance:** Bhowmik is the only major hearing aid company CTO from the consumer AI/computing world; his Intel background reflects cross-pollination of consumer tech AI talent into the hearing industry
- AIMBE fellowship validates Starkey's health-tech positioning: their CTO is recognized for medical/biological engineering innovation, not just consumer electronics

## Competitive Gap
As of 2026, Starkey is the only manufacturer with FDA-cleared fall detection in a hearing aid. Competitors have not matched this. The gap may close as health monitoring becomes a competitive requirement rather than a differentiator.

## Related Pages
- [[apple-hearing-features]] — Apple Watch also tracks falls; different form factor but overlapping health monitoring territory
- [[sonova-ag]] — Competitor; no fall detection
- [[demant-oticon]] — Competitor; no fall detection
- [[on-device-ml-hearing-aids]] — Starkey's Edge AI as implementation example

## Sources
- Research notes on Genesis AI platform, 3D sensor fall detection, battery specs, Hear Share app
- [Starkey CTO Bhowmik AIMBE Induction](../sources/starkey-cto-bhowmik-aimbe-april-2026.md) — AIMBE fellowship recognition
