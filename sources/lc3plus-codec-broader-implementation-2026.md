---
title: LC3plus Codec Broader Implementation for LE Audio Music Streaming
source: Industry news
date: 2026-04-25
ingested: 2026-04-25
tags: [lc3plus, le-audio, bluetooth, codec, music-streaming, audio-quality]
---

# LC3plus Codec Broader Implementation

## Key Facts
- LC3plus codec seeing broader implementation across LE Audio devices
- Improved audio quality over standard LC3 codec for music streaming
- Part of the Bluetooth LE Audio ecosystem alongside Auracast
- Relevant for hearing aid users who stream music via Bluetooth

## Significance for Hearing AI
- **LC3 is the baseline codec** for Bluetooth LE Audio / Auracast — LC3plus extends this with higher quality for music
- Music streaming quality matters for hearing aid users: hearing aids must process the decoded audio, and codec artifacts can interact poorly with hearing aid processing (amplification, compression)
- **LC3plus vs LC3:**
  - LC3plus supports higher bitrates and lower latency modes
  - Better handling of music content (LC3 was primarily optimized for speech)
  - Backward compatible with LC3 infrastructure
- As Auracast venues deploy, the codec quality affects the end-user experience through hearing aids
- Hearing aid manufacturers implementing LE Audio must decide whether to support LC3plus (higher quality, more compute) or LC3 only (simpler, lower power)

## Context
- LC3 (Low Complexity Communication Codec) is the mandatory codec for Bluetooth LE Audio
- LC3plus is an enhanced version offering better quality at higher bitrates
- Both are standardized by the Bluetooth SIG
- Auracast broadcast audio uses LC3 as the baseline; LC3plus support is optional

## Relevance to Wiki
- Updates [[auracast-bluetooth-le-audio]] — codec quality layer
- Relevant to [[hearing-aid-chip-architectures]] — codec decode compute requirements
- Relevant to consumer audio quality expectations for hearing aid streaming
