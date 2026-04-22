---
title: WS Audiology / Signia
type: entity
created: 2026-04-15
updated: 2026-04-22
sources: [signia-ix-platform-2024.md, wsa-sound-preference-program-april-2026.md, sony-otc-hearing-aids-discontinued-april-2026.md]
related: [sonova-ag.md, demant-oticon.md, gn-hearing-resound.md, starkey.md, ../concepts/closed-loop-data-flywheel.md]
tags: [company, manufacturer, signia, widex, singapore, dnn, conversation-enhancement, multi-stream, personalization, sound-preference]
---

# WS Audiology / Signia

Formed in 2019 from the merger of Sivantos (Siemens hearing) and Widex. Headquartered in Singapore.

## Brands
- **Signia** — Premium brand (formerly Siemens)
- **Widex** — Premium brand known for sound quality and music processing
- **Rexton** — Mid-tier brand
- **Audio Service** — European brand

## Technology

### Signia IX Platform (Integrated Xperience)
Signia's flagship AI platform, expanded through 2025:

**Core Architecture: Multi-Stream Processing**
- Processes multiple independent audio streams simultaneously
- Enables different AI processing for different sound sources in the same environment

**RealTime Conversation Enhancement**
- AI co-processor enhancement for live conversations
- **8.1 dB SNR benefit** vs. unaided listening; **3.2 dB better** than nearest competitor
- **85% increase** in time users are willing to spend in noisy group conversation
- Cloud-based **Signia Assistant** — live DNN model accessible via app for real-time adjustments and personalization; delivers cloud-based DNN inference without requiring all compute on-device
- Processes conversation in real-time without perceptible latency

**Form Factor Expansion (2025)**
- Signia IX originally launched in RIC/RITE forms
- **Aug 2025**: Expanded with **Insio IX** (custom ITE/ITC) and **Motion Charge&Go IX** (BTE), bringing IX AI to all major form factors

**Battery / Power**
- Longest battery runtime among rechargeable superpower hearing aid devices (high-power category for severe/profound loss)

**Corporate Developments**
- **Feb 2025**: Launched **BestSound Center** in Pune, India — expanding clinical network presence in a major emerging market

### Other Technologies
- **TwinLink** — Dual-radio platform (Bluetooth Classic + proprietary near-field for ear-to-ear)
- **Widex MOMENT / PureSound** — Ultra-low latency processing pipeline; known for natural sound quality particularly for music
- **Own Voice Processing (OVP)** — ML classifier that separates the wearer's own voice from environmental sound in real-time for more natural self-perception
- **Active Scanning** — Processes 15 million data points per hour for acoustic classification

### Sound Preference Program (April 2026)
WSA launched a free **Sound Preference Program** and interactive **Sound Preference Tool** to quantify individual listening preferences:

- Research shows **~40% of users** have strong, consistent preferences for either "natural sound" or "enhanced sound"
- The tool uses **randomized audio comparisons** to identify preferences without requiring patients to describe what they hear
- Overcomes the vocabulary barrier in hearing care — patients don't need audiological language to express preferences
- Classifies users into preference types that are **consistent across sessions** for ~40% of the population
- Remaining ~60% show mixed or context-dependent preferences

**Strategic significance:**
- Creates a **structured data collection framework for personalization** — converts subjective experience into quantifiable, actionable data
- Aligns perfectly with WSA's dual-brand positioning: **Widex** (natural sound quality, PureSound) vs. **Signia** (enhanced processing, RealTime Conversation Enhancement)
- Free availability encourages broad adoption, generating preference data across WSA's customer base
- If integrated with **Signia Assistant** (cloud DNN), could enable preference-aware personalization at scale
- Represents a step toward a [[closed-loop-data-flywheel]] for WSA — preference data from fittings feeds back into product development and automated personalization

### Sony OTC Partnership — Discontinued (April 2026)
WSA partnered with Sony on the CRE series OTC hearing aids, leveraging Sony's consumer brand recognition with WSA's hearing technology. **Sales were discontinued in April 2026** due to:
- Premium OTC pricing ($999-$1,299) could not compete with AirPods Pro ($200-$249, FDA-cleared) and ultra-affordable OTC options (Ceretone at $165)
- Even Sony's strong consumer brand was insufficient to justify premium OTC pricing
- WSA signals continued OTC interest but needs a fundamentally different approach
- **Strategic implication:** WSA likely refocuses on Signia/Widex prescription AI features where margins are sustainable, rather than OTC brand licensing

## Signia vs. Competitors on AI Co-Processing
WSA claims 22% speech understanding advantage over "AI co-processor competitors" — this phrasing likely targets Phonak/Sonova (DEEPSONIC co-processor) and the framing is worth watching as independent verification becomes available. The metric is Signia's own published result.

## Notable Characteristics
- Widex historically considered best-in-class for music and high-fidelity sound (low latency via PureSound)
- OVP is a distinctive ML problem: must classify the wearer's own voice vs. external speech in real-time, separately process, and recombine — requires speaker-verification-adjacent techniques
- Cloud-based Signia Assistant represents a hybrid on-device + cloud AI model (contrasts with fully on-device competitors)

## Related Pages
- [[sonova-ag]] — Competitor; Signia's 22% speech claim targets co-processor designs like DEEPSONIC
- [[demant-oticon]] — Competitor
- [[gn-hearing-resound]], [[starkey]] — Other major competitors
- [[closed-loop-data-flywheel]] — Sound Preference Program as structured data collection for personalization feedback loop

## Sources
- Research notes on Signia IX platform, RealTime Conversation Enhancement, 2025 form factor expansion
- [WS Audiology Sound Preference Program (April 2026)](../../sources/wsa-sound-preference-program-april-2026.md) — 40% users have consistent natural vs. enhanced preference; randomized audio comparison tool
- [Sony OTC Hearing Aids Discontinued](../../sources/sony-otc-hearing-aids-discontinued-april-2026.md) — Premium OTC pricing failure, WSA ends Sony brand partnership
