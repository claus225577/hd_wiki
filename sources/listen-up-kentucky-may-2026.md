---
title: Listen Up Kentucky — ADA + WSA + KAA State-Level Hearing-Health Awareness Pilot (May 2026)
type: industry-news
date: 2026-05-11
url: https://hearinghealthmatters.org/hearing-news-watch/2026/ada-wsa-listen-up-kentucky/
secondary_url: https://www.wkyt.com/video/2026/05/11/better-living-listen-up-kentucky-campaign-memorial-day-travel/
tags: [public-health, awareness, marketing, hearing-care-access, ws-audiology, ada-academy-doctors-audiology, kentucky-audiology-association, state-pilot, better-hearing-month, top-of-funnel]
---

# Listen Up Kentucky — Hearing-Health Public-Awareness Pilot

## Key Extractions

- **Launch date:** May 2026, timed to Better Hearing Month (officially "National Speech-Language-Hearing Month" 2026 — ASHA theme "Speech and Hearing Hero").
- **Partners:**
  - **ADA** — Academy of Doctors of Audiology
  - **WSA** — WS Audiology (parent of Widex, Signia, Audibel-adjacent)
  - **KAA** — Kentucky Academy of Audiology
- **Mechanics:**
  - Locally targeted PSAs (TV and radio) for placement across Kentucky media markets
  - Audiologist outreach toolkits — content licensed for use in patient education and community outreach
  - Focus on prevention, early intervention, and "lifelong importance" of hearing health
- **Scale design:** explicitly framed as a **scalable model** for adaptation to other states and territories. ADA and WSA plan additional state rollouts following the Kentucky pilot.
- **Surfacing:** Hearing Health & Technology Matters (May 2026) coverage; WKYT (Lexington, KY) "Better Living" segment May 11, 2026; Kentucky New Era state press; Beshear (KY Governor) recommendation for hearing evaluation during May.

## Adjacent Better Hearing Month 2026 Activity (Context)

| Initiative | Operator | Mechanism |
|---|---|---|
| **Listen Up Kentucky** | ADA + WSA + KAA | State-level PSA + clinic toolkits |
| **31-in-31 hearing-aid giveaway** | Beltone | 31 hearing aids in 31 days, free screenings across ~1,200 clinics |
| **"Speech and Hearing Hero" campaign** | ASHA | National theme for SLPs and audiologists |
| **State proclamations** | Various governors | Encouraged hearing evaluations during May |

## Why This Matters (Data-Science Framing)

### 1. The missing top-of-funnel layer

Roughly 80% of people with hearing loss never seek care (figure widely cited by WHO and IHS). The hearing-care AI / data-science stack has spent a decade optimizing the **bottom** of the funnel (chip architectures, DNN noise reduction, fitting algorithms, real-ear measurement, ecological telemetry) and almost no instrumentation has been built for the **top** (awareness → search → screening → consult → fit).

Listen Up Kentucky is one of the first explicitly engineered top-of-funnel data-collection vehicles in U.S. hearing care.

### 2. A state-level A/B framework

By design, the pilot has the structural properties of a randomized rollout:

- **Single-geography treatment arm** — Kentucky exposed first; comparison states unexposed until later phases.
- **Multi-channel media buy** — TV and radio PSAs at the DMA (designated market area) level, plus audiologist-driven community outreach. Channel-level attribution is in principle possible if exposure logs and screening conversions are linked.
- **Scalable rollout plan** — the explicit intent to replicate in additional states creates a phased treatment-vs-control design across years 1–3.

### 3. What the missing measurement pipeline would look like

A native data-science layer beneath the campaign would instrument:

- **Exposure** — DMA-level PSA placements, frequency, reach (Nielsen / Comscore equivalents)
- **Search behavior** — Google Trends / SEM lift in "hearing test" and "audiologist near me" queries by zip code
- **Screening conversion** — local clinic call-volume and online appointment requests
- **Fitting conversion** — downstream hearing-aid sales in the geography
- **Demographic stratification** — age, urbanicity, SES, insurance status
- **Message attribution** — PSA variant (radio voice-over vs. TV spot vs. clinic insert) → which lifts which outcome

Consumer-tech and CPG marketing have had this attribution model for ~15 years; hearing healthcare is just beginning to install it.

### 4. The competitive variable that emerges

If the top-of-funnel attribution model gets built, the next-decade competitive variable for hearing manufacturers may shift from "best on-chip DNN" to **"best attribution model on top-of-funnel marketing"**. The OEM that can predict which patients walk into which clinic with which awareness path captures incremental fitting volume regardless of device sophistication.

WSA participating as the only manufacturer in Listen Up Kentucky is therefore strategically interesting: it positions WSA as the first OEM with a state-scale dataset of PSA-driven hearing-care demand.

## Connections to Existing Wiki Pages

- **[[../concepts/audiologist-workforce-shortage]]** — workforce is the supply-side constraint; awareness/demand is the demand-side constraint. A workforce shortage with a closed-loop awareness pipeline still leads to bottleneck queues; a workforce shortage with leaky awareness leads to under-utilized capacity.
- **[[../concepts/otc-hearing-aids]]** — OTC removes the audiologist from the conversion path. Listen Up Kentucky is for prescription channel awareness specifically.
- **[[../concepts/hearing-aid-market-dynamics]]** — market growth has been gated by penetration (adoption) more than by addressable population.
- **[[../entities/ws-audiology-signia]]** — WSA is the participating OEM.
- **[[../syntheses/hearing-aid-market-outlook]]** — penetration uplift from awareness is the largest single TAM expansion lever.

## Related Wiki Pages to Update / Create

- New concept page: **`hearing-care-funnel-attribution`** (top-of-funnel data layer; new).
- Update **`audiologist-workforce-shortage`** with the demand-side framing.
- Update **`hearing-aid-market-dynamics`** to add penetration/awareness as a distinct lever.
- Update **`ws-audiology-signia`** entity page with the Listen Up Kentucky pilot listing.

## Open Research Directions

1. Linking PSA exposure to hearing-test booking conversion at zip-code granularity in pilot states.
2. Modeling adherence to follow-on care (consult → fit → wear) as a downstream funnel stage.
3. Estimating elasticity: what is the cost per incremental fitting attributable to top-of-funnel awareness spend?
4. Comparing prescription-channel vs. OTC-channel conversion rates from the same awareness uplift.
5. Whether geographic patterns of conversion correlate with audiologist-density (supply-side) or with media-spend (demand-side).
