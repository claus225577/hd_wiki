---
title: Hearing-Care Funnel Attribution
type: concept
created: 2026-05-16
updated: 2026-05-16
sources: [listen-up-kentucky-may-2026.md, hearing-aids-market-14b-by-2030-april-2026.md, audiologist-shortage-asha-sciencedirect-2025.md]
related: [audiologist-workforce-shortage.md, otc-hearing-aids.md, hearing-aid-market-dynamics.md, closed-loop-data-flywheel.md, teleaudiology.md, ../entities/ws-audiology-signia.md, ../syntheses/hearing-aid-market-outlook.md]
tags: [public-health, marketing, attribution, top-of-funnel, awareness, demand-generation, market-penetration, state-pilots, hearing-care-access]
---

# Hearing-Care Funnel Attribution

The data-science layer that models how potential hearing-care patients move from **never thinking about their hearing** → **considering it** → **getting screened** → **consulting** → **fitting** → **wearing**. The hearing-care AI / signal-processing literature has heavily instrumented the late stages of this funnel (fitting, wearing, telemetry) and barely instrumented the early stages (awareness, search, screening). This is the largest unmeasured layer in the field's data stack.

## The Funnel

| Stage | Where the field has good data | Where the field has weak data |
|---|---|---|
| **Unaware** | — | Nearly no data; population estimates from WHO + national surveys |
| **Aware, not seeking** | — | Partial; some EU surveys; no per-DMA / per-zip data |
| **Searching** | — | Trace signal in Google Trends; not joined to outcomes |
| **Screening / hearing test** | National HHS / NHANES; some manufacturer data | Not linked back to awareness exposure |
| **Consult / fitting** | OEM and retail-chain data | Reasonably good per-chain; not linked to upstream marketing |
| **Wearing / outcomes** | Strong telemetry (Phonak DataLogging, Oticon, Signia, Starkey TeleHear) | Mature; the only well-instrumented layer |

The asymmetry is striking: a hearing aid wearer has minute-by-minute environment-classification telemetry, but the field has almost no data on what made them book the appointment in the first place.

## Why This Matters

### 1. The binding constraint is at the top

Roughly **80% of people with hearing loss never seek care** (figure widely cited by WHO and the International Hearing Society). The signal-processing and fitting literature has spent a decade optimizing the bottom 20%. The largest accessible TAM expansion is structurally **upstream of the device**.

### 2. Awareness is the under-modeled lever

Penetration uplift from awareness is the largest single TAM expansion lever in [[hearing-aid-market-dynamics]]. Yet no major OEM has published a peer-reviewed attribution model linking PSA exposure → screening conversion → fitting conversion → lifetime value.

### 3. Workforce shortage and awareness compound

[[audiologist-workforce-shortage]] frames the supply side; this page is the demand side. With 75% of U.S. counties in audiologist shortage and 80% of people with hearing loss not seeking care, the supply and demand levers must be modeled jointly. Closing awareness without expanding supply leads to bottleneck queues. Expanding supply without closing awareness leads to under-utilized capacity.

## Listen Up Kentucky as a State-Level A/B Framework

ADA + WSA + KAA launched **Listen Up Kentucky** in May 2026 for Better Hearing Month. The campaign is explicitly designed to be replicated in additional states, which makes it structurally an A/B framework if measurement is wired in.

| Dimension | Design |
|---|---|
| Treatment arm | Kentucky DMAs, May 2026 onward |
| Control arms | Adjacent states (Tennessee, Indiana, West Virginia) — unexposed until later phases |
| Treatment channels | TV PSAs, radio PSAs, audiologist outreach toolkits |
| Replication intent | ADA + WSA committed to additional state rollouts |
| Time horizon | Multi-year |

See [[../sources/listen-up-kentucky-may-2026]].

### What a Native Attribution Pipeline Would Capture

1. **Exposure** — DMA-level PSA placements, frequency, reach (Nielsen / Comscore-style)
2. **Search lift** — Google Trends / SEM uplift in "hearing test," "audiologist near me," "hearing loss treatment" by zip code
3. **Screening conversion** — local clinic call-volume, online appointment requests
4. **Fitting conversion** — downstream hearing-aid sales in the geography
5. **Demographic stratification** — age, urbanicity, SES, insurance status, primary language
6. **Message attribution** — PSA variant (radio voice-over vs. TV spot vs. clinic insert) → which lifts which outcome
7. **Channel substitution** — does Apple AirPods OTC eat the prescription conversion in some segments? See [[otc-hearing-aids]]

Consumer-tech and CPG marketing have had this attribution model for ~15 years. Hearing healthcare is just beginning to install it.

## Model Classes That Apply

- **Geo-uplift modeling** — synthetic control methods (Abadie et al.) and difference-in-differences for state-level rollouts
- **Multi-touch attribution** — Markov-chain and Shapley-value attribution for multi-channel awareness paths
- **Propensity scoring** — likelihood of conversion conditioned on demographics, geography, prior exposure
- **Survival analysis** — time-to-screening from first PSA exposure as a survival outcome
- **Causal forests** — heterogeneous treatment effects across demographic subgroups
- **Joint supply-demand modeling** — linking [[audiologist-workforce-shortage]] capacity constraints to demand-side awareness uplift; a fitting saturated by appointment availability won't show full conversion uplift even with strong awareness

## Why the OEM with the Best Attribution Model Wins the Next Decade

If on-chip AI is converging across OEMs (it is — see [[../comparisons/ai-hearing-aid-platforms-2026]]), the competitive variable migrates upstream. The OEM that can predict **which patients walk into which clinic with which awareness path** captures incremental fitting volume regardless of device sophistication.

WSA participating as the only OEM in Listen Up Kentucky is therefore strategically interesting: it positions WSA as the first major OEM with a state-scale dataset of PSA-driven hearing-care demand.

## Data-Science Skills That Become Relevant

Hearing-AI hiring has historically prioritized signal processing, ML for audio, and clinical-evidence statistics. Funnel attribution requires a different stack:

- Marketing-mix modeling (MMM)
- Bayesian hierarchical models for geo + time
- Privacy-preserving identity resolution
- A/B and quasi-experimental design
- Clickstream and search-volume analysis
- Geo-spatial analytics

These are common in consumer tech and CPG but rare inside hearing OEM R&D.

## Open Questions

- What is the cost per incremental fitting attributable to top-of-funnel awareness spend?
- Are PSA-driven conversions more or less valuable (LTV, retention, satisfaction) than walk-in or referral conversions?
- Does the demand-side uplift saturate against workforce supply, and at what point?
- Should OEMs build internal attribution capability, or buy it via partnership with marketing-services firms?

## Related Pages

- [[audiologist-workforce-shortage]] — Supply-side constraint; pairs with this demand-side page
- [[otc-hearing-aids]] — OTC bypasses the prescription funnel; substitution effect matters in any attribution model
- [[hearing-aid-market-dynamics]] — TAM math depends on penetration / awareness uplift
- [[closed-loop-data-flywheel]] — Device-telemetry flywheel is the bottom-of-funnel parallel
- [[teleaudiology]] — Remote screening as a conversion-accelerator within the funnel
- [[../entities/ws-audiology-signia]] — Participating OEM in the Kentucky pilot
- [[../syntheses/hearing-aid-market-outlook]] — Penetration / awareness as the largest TAM expansion lever

## Sources

- [Listen Up Kentucky — ADA + WSA + KAA, May 2026](../../sources/listen-up-kentucky-may-2026.md) — State-level pilot launching the public-health awareness layer
- [Hearing Aids Market $14B by 2030 — MarketsandMarkets, April 2026](../../sources/hearing-aids-market-14b-by-2030-april-2026.md) — Market size figures that make the awareness lever quantifiable
- [Audiologist Shortage — ASHA + ScienceDirect](../../sources/audiologist-shortage-asha-sciencedirect-2025.md) — Supply-side companion data
