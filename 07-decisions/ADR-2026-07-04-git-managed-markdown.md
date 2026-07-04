---
type: decision
status: accepted
created: 2026-07-04
area: tooling
tags:
  - adr
  - git
  - markdown
  - obsidian
---

# ADR-2026-07-04 Git-managed Markdown

## Context

The system needs to support developer notes, TODO, daily goals, reflection, graph views, desktop use, and mobile reading.

## Decision

Use Markdown files as the source of truth and manage them with Git. Use Obsidian as the interface for graph, Canvas, Bases, backlinks, and mobile access.

## Consequences

- The vault remains portable.
- Git history is clear and inspectable.
- Obsidian-specific files such as `.base` and `.canvas` can be tracked when they describe the knowledge system.
- Mobile Git workflows should stay simple; serious Git operations are better on desktop.

## Links

- [[git-managed-markdown]]
- [[second-brain]]

