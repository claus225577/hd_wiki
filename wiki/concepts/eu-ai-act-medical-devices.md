---
title: EU AI Act and Medical Device Regulation
type: concept
created: 2026-04-25
updated: 2026-04-25
sources: [eu-ai-act-medical-device-compliance-2026.md]
related: [hearing-aid-market-dynamics.md, otc-hearing-aids.md, dnn-in-hearing-aids.md, ../entities/sonova-ag.md, ../entities/demant-oticon.md, ../entities/starkey.md, ../entities/ws-audiology-signia.md, ../syntheses/hearing-aid-ai-stack-2026.md]
tags: [regulation, eu-ai-act, medical-device, class-iia, compliance, ai-regulation, market-access]
---

# EU AI Act and Medical Device Regulation

The EU AI Act introduces the first binding regulatory framework for artificial intelligence in medical devices, including AI-powered hearing aids. Class IIa provisions are entering their compliance period in 2026, requiring hearing aid manufacturers to meet new transparency, risk management, and documentation standards for their AI/ML components.

## Classification

AI-powered hearing aids are classified as **Class IIa medical devices** under the EU AI Act — "medium risk." This applies to any hearing aid that uses AI/ML algorithms for clinical functions:
- DNN-based noise reduction affecting speech intelligibility
- AI scene classification driving automatic program selection
- ML-based fitting recommendations
- Health monitoring features with clinical claims (fall detection, heart rate)

## Compliance Requirements

Manufacturers selling AI hearing aids in the EU must address:

### Documentation
- Full documentation of training data, model architecture, and validation procedures
- Records of DNN training datasets (e.g., the 13M-22M sound scenes used by major manufacturers)
- Model performance characterization across intended user populations

### Risk Assessment
- Risk analysis for AI-driven clinical decisions (e.g., automatic amplification changes based on scene classification)
- Failure mode analysis for AI components — what happens when the DNN misclassifies a scene?
- Assessment of bias: does the DNN perform equally across languages, accents, and hearing loss profiles?

### Transparency
- Users may need to be informed when AI is making processing decisions
- Disclosure of AI involvement in clinical functions

### Post-Market Monitoring
- Ongoing monitoring of AI performance after deployment
- Implications for over-the-air (OTA) model updates: firmware updates that change DNN behavior may require re-certification or conformity assessment

## Impact on the Industry

### Model Update Velocity
- OTA DNN updates (like Phonak's "18x more training data" firmware update) may require regulatory review before deployment in the EU
- Could create a gap between EU and non-EU device capabilities if updates are delayed by compliance review
- Incentivizes manufacturers to build robust validation pipelines that can rapidly clear regulatory review

### Competitive Effects
- **Advantages large manufacturers:** Sonova, Demant, and others with strong R&D documentation practices and clinical trial infrastructure (e.g., Phonak NCT07526428) are better positioned to comply
- **Barrier for OTC entrants:** Smaller OTC brands with AI features may lack regulatory resources, potentially limiting competition in the EU market
- **Apple and consumer tech:** AirPods Pro with FDA OTC clearance in the US face additional EU AI Act requirements for European sales if classified as medical devices

### AI-Powered vs Non-AI Devices
- Creates a formal regulatory distinction between hearing aids with and without AI
- "Natural processing" approaches (e.g., Widex Allure with no DNN) avoid AI-specific compliance burdens
- May incentivize some manufacturers to limit or defer AI features in EU-marketed devices

## Connection to Other Regulations
- **EU Medical Device Regulation (MDR):** AI Act requirements layer on top of existing MDR requirements for hearing aids
- **European Accessibility Act (2025):** Drives Auracast and accessibility standards alongside AI regulation
- **FDA OTC regulations (US):** No equivalent AI-specific requirements yet — creates regulatory asymmetry between US and EU markets

## Open Questions
- How will regulators assess DNN performance for hearing-specific use cases? Standard ML metrics (PESQ, STOI) may not satisfy clinical evidence requirements
- Will "AI hearing aid" become a distinct regulatory category separate from "hearing aid"?
- How will federated learning or on-device personalization be regulated — if the model changes on each user's device?

## Related Pages
- [[hearing-aid-market-dynamics]] — Regulatory burden as market barrier and competitive factor
- [[otc-hearing-aids]] — OTC AI devices facing EU compliance requirements
- [[dnn-in-hearing-aids]] — The DNN systems subject to regulation
- [[sonova-ag]], [[demant-oticon]], [[starkey]], [[ws-audiology-signia]] — Affected manufacturers
- [[hearing-aid-ai-stack-2026]] — Regulatory layer in the AI stack

## Sources
- [EU AI Act Medical Device Compliance](../../sources/eu-ai-act-medical-device-compliance-2026.md) — Class IIa provisions, compliance timeline, manufacturer impact
