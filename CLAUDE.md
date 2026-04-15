# Hearing + AI LLM-Wiki

An LLM-maintained knowledge wiki tracking the intersection of hearing aid technology, audiology, AI/ML, and data science. Inspired by [Karpathy's LLM-wiki concept](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

## Architecture

### Layer 1: Raw Sources (`sources/`)
Immutable references to ingested documents — papers, articles, news items. Each source gets a YAML-frontmatter markdown file with metadata and a brief extraction. The LLM reads these but never modifies them after creation.

### Layer 2: The Wiki (`wiki/`)
LLM-generated and LLM-maintained markdown pages organized by type:
- `wiki/concepts/` — Technical concepts (e.g., beamforming, NAL-NL2, Auracast, edge AI)
- `wiki/entities/` — Companies, products, people, organizations (e.g., Sonova, Oticon Real, WHO)
- `wiki/comparisons/` — Side-by-side analyses (e.g., on-device vs cloud ML, HA chip architectures)
- `wiki/syntheses/` — Cross-cutting analyses, trend reports, emerging patterns
- `wiki/index.md` — Master catalog of all wiki pages, organized by category
- `wiki/log.md` — Append-only chronological record of all operations

### Layer 3: This Schema (CLAUDE.md)
Defines structure, workflows, and conventions.

## Page Format

Every wiki page uses this template:

```markdown
---
title: <Page Title>
type: concept | entity | comparison | synthesis
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: [source-file-1.md, source-file-2.md]
related: [page1.md, page2.md]
tags: [tag1, tag2]
---

# <Page Title>

<Content organized with clear headings>

## Related Pages
- [[related-page]] — brief description of relationship

## Sources
- [Source Title](../sources/source-file.md) — what was used from this source
```

## Operations

### Ingest
When processing a new source (paper, article, news):
1. Create a source file in `sources/` with metadata + key extraction
2. Check if relevant wiki pages already exist — update them with new information
3. Create new wiki pages for genuinely new concepts/entities
4. Update cross-references (`related:` fields) across affected pages
5. Update `wiki/index.md` with any new pages
6. Append to `wiki/log.md`

Target: touch 5-15 wiki pages per source ingested.

### Query
When answering questions using the wiki:
1. Search relevant wiki pages
2. Synthesize an answer with citations to wiki pages and underlying sources
3. If the query reveals a gap, create or update wiki pages to fill it
4. Append to `wiki/log.md`

### Lint
Periodic health check:
1. Find orphan pages (no incoming links)
2. Detect contradictions between pages
3. Flag stale claims (source > 6 months old, fast-moving topic)
4. Verify all cross-references resolve
5. Check for duplicate concepts that should be merged
6. Append findings to `wiki/log.md`

## Integration Points

- **Daily LinkedIn posts**: After generating posts, ingest the researched sources into this wiki
- **Daily hearing+AI digest**: After compiling the email digest, ingest sources here
- **Ad-hoc research**: Any hearing/AI research done in conversation should be ingested

## Conventions
- Filenames: kebab-case, descriptive (e.g., `auracast-bluetooth-le-audio.md`, `sonova-ag.md`)
- Keep pages focused — one concept/entity per page, split if too broad
- Prefer updating existing pages over creating near-duplicates
- Always include at least one `related:` link — orphan pages are a smell
- Dates in ISO 8601 (YYYY-MM-DD)
- Tags use lowercase, hyphenated (e.g., `speech-enhancement`, `edge-ai`, `otc-hearing-aids`)
