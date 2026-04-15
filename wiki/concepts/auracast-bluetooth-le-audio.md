---
title: Auracast / Bluetooth LE Audio
type: concept
created: 2026-04-15
updated: 2026-04-15
sources: [auracast-hearing-accessibility-2026.md]
related: [on-device-ml-hearing-aids.md, ../entities/gn-hearing-resound.md]
tags: [bluetooth, accessibility, connectivity, infrastructure]
---

# Auracast / Bluetooth LE Audio

Auracast is a broadcast audio feature within the Bluetooth LE Audio specification that enables a single audio source to stream directly to an unlimited number of compatible hearing aids simultaneously — without pairing.

## How It Works
- Based on Bluetooth Low Energy (BLE) with the LC3 codec
- A transmitter (installed in a venue) broadcasts an audio stream
- Any Auracast-compatible hearing aid within range can tune in
- No pairing step required — similar to tuning into a radio station

## Why It Matters for Hearing Accessibility
- Eliminates the need for hearing loops (telecoil/T-coil infrastructure)
- No special equipment requests at front desks — reduces stigma
- Works in theaters, airports, lecture halls, houses of worship, transit
- Potentially the most significant connectivity standard for hearing accessibility in decades

## Current Status (April 2026)
- **Device support:** ReSound Vivia and Nexia ship with Auracast. Other manufacturers following.
- **Venue adoption:** Very limited. Bluetooth SIG/ABI Research project meaningful adoption by 2029.
- **The gap:** Hearing aids are ready; venues lag ~3 years behind.

## Data Science Angle
- Usage analytics could build the business case for venue investment
- Opportunity to measure real-world accessibility impact for the first time
- Could generate rich location-context data for hearing aid personalization

## Open Questions
- Who pays for venue infrastructure? Hearing aid companies, venues, or government mandates?
- Will Auracast coexist with or replace telecoil/hearing loop systems?
- How will discovery work — how do users find available broadcasts?

## Related Pages
- [[on-device-ml-hearing-aids]] — Auracast audio needs on-device processing
- [[gn-hearing-resound]] — First mover with Auracast-ready devices
