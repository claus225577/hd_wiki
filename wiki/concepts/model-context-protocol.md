---
title: Model Context Protocol (MCP)
type: concept
created: 2026-04-19
updated: 2026-04-19
sources: [mcp-dev-summit-97m-installs-april-2026.md, karpathy-idea-files-april-2026.md]
related: [../syntheses/ai-understanding-gap-hearing-industry.md, small-language-models-edge-ai.md, on-device-ml-hearing-aids.md, teleaudiology.md, automated-audiometry.md]
tags: [mcp, protocol, agentic-ai, anthropic, open-standard, tool-use, interoperability, infrastructure]
---

# Model Context Protocol (MCP)

An open protocol for connecting AI models to external tools, data sources, and services. Originally developed by Anthropic, MCP has become the de facto standard for AI agent tool use — analogous to how HTTP standardized web communication or how USB standardized peripheral connectivity.

## Key Facts

| Metric | Value |
|--------|-------|
| Monthly SDK downloads | **97 million** (April 2026) |
| First Dev Summit (North America) | NYC, April 2-3, 2026 |
| Dev Summit sessions | **95+** |
| Governance | Agentic AI Foundation (Linux Foundation) |
| Co-founders | Anthropic, Block, OpenAI |
| Supporting members | Google, Microsoft, AWS |
| Donated to Linux Foundation | December 2025 |

## What MCP Does

MCP provides a standardized way for AI models to:
1. **Discover** available tools and data sources
2. **Invoke** tools with structured inputs/outputs
3. **Access** contextual data from external systems
4. **Compose** multi-step workflows across different services

Without MCP, every AI integration required custom API adapters. MCP standardizes the interface layer, enabling any MCP-compatible AI model to use any MCP-compatible tool.

## Governance and Ecosystem

The donation to the Linux Foundation's Agentic AI Foundation (December 2025) was a significant strategic move:
- Ensures no single company controls the protocol
- Co-founded by Anthropic (creator), Block, and OpenAI — notably including competitors
- Google, Microsoft, and AWS as supporting members means cloud platform neutrality
- Linux Foundation governance provides the institutional stability that healthcare and medical device integration requires

## Relevance to Hearing + AI

### Near-Term Applications
- **Audiological tooling:** MCP servers wrapping audiometer software, fitting systems, and EHR interfaces would allow AI agents to perform hearing assessments and adjust hearing aids programmatically
- **Teleaudiology automation:** AI agents using MCP to access patient records, run hearing tests, adjust fitting parameters, and schedule follow-ups
- **Clinical decision support:** AI models accessing patient audiograms, medical history, and fitting databases through MCP to provide fitting recommendations

### Medium-Term Applications
- **Interoperable hearing AI:** MCP as the standard interface between hearing aid manufacturer platforms and third-party AI services
- **Multi-manufacturer compatibility:** A teleaudiology AI agent could use MCP to interact with Phonak, Oticon, ReSound, and Starkey fitting software through a unified interface
- **Research automation:** MCP-connected AI agents could automate literature search, data extraction, and meta-analysis for audiology research

### Why This Matters for Hearing Care
The audiologist workforce shortage (75% of US counties are shortage areas) creates urgent demand for AI-assisted hearing care. MCP provides the infrastructure layer that makes scalable AI audiological tools possible:
- Standardized protocol means hearing AI tools built once work everywhere
- Linux Foundation governance provides the long-term stability needed for medical device integration
- 97M monthly downloads indicates the developer ecosystem is mature enough to build on

## Connection to Karpathy's Idea Files

MCP and Karpathy's "idea files" paradigm represent complementary developments:
- **MCP** standardizes how AI agents *act* on the world (tool use protocol)
- **Idea files** standardize how humans *instruct* AI agents (structured specifications)
- Together, they form the infrastructure layer for agentic AI: instructions (idea files) -> reasoning (LLM) -> action (MCP tools)
- This hearing-ai-wiki is itself an idea file implementation (Karpathy's LLM Wiki pattern) that could be served to AI agents via MCP

## Related Pages
- [[ai-understanding-gap-hearing-industry]] — MCP as infrastructure for bridging the gap between AI capabilities and clinical practice
- [[small-language-models-edge-ai]] — SLMs on hearing aid chips could use lightweight MCP-like protocols for cloud communication
- [[on-device-ml-hearing-aids]] — On-device processing that may communicate with cloud services via standardized protocols
- [[teleaudiology]] — AI-powered teleaudiology as a primary use case for MCP in hearing care
- [[automated-audiometry]] — Automated hearing tests as MCP tool endpoints

## Sources
- [MCP Dev Summit + 97M Installs](../sources/mcp-dev-summit-97m-installs-april-2026.md)
- [Karpathy Idea Files](../sources/karpathy-idea-files-april-2026.md) — Complementary paradigm for AI agent instructions
