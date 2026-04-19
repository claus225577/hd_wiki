---
title: "Karpathy Proposes 'Idea Files' for AI Agent Development"
source_type: news-article
url: https://www.simplenews.ai/news/andrej-karpathy-proposes-idea-files-as-new-paradigm-for-ai-agent-development-gnd3
date: 2026-04-04
accessed: 2026-04-16
tags: [karpathy, llm-wiki, idea-files, ai-agents, knowledge-management]
---

# Karpathy's "Idea Files" Paradigm

Andrej Karpathy introduced structured markdown specifications ("idea files") for AI agent development via a GitHub Gist titled 'LLM Wiki'.

## Key Extractions

- **Idea files**: Structured markdown specs describing system architectures without implementation code
- **Core philosophy:** "Share the idea, not the code — the agent builds it for your context"
- **Three-layer architecture**: Raw sources (immutable) -> Wiki (LLM-generated, continuously updated) -> Schema (configuration)
- **Three operations**: Ingest (process sources, update pages), Query (answer questions, file synthesis), Lint (health-checks)
- **The LLM Wiki** is the primary example of the idea file paradigm — a knowledge base maintained by LLMs rather than humans
- Karpathy's personal wiki: **~100 articles, 400,000 words** on a single research topic
- **Hacker News reception:** 246 points, 77 comments — sparked significant developer community adoption
- Represents shift from distributing finished code to sharing high-level specs that AI agents customize per context
- The paradigm assumes AI agents are capable enough to implement complex systems from architectural descriptions alone

## Also Noted

- Karpathy warns of growing gap between AI power users and skeptics — "two distinct user groups speaking past each other"
- Published "Karpathy Guidelines" for LLM programming standards
- This hearing-ai-wiki is itself an implementation of Karpathy's LLM Wiki concept
