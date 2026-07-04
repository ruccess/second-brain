# Claude Instructions

This is a Git-managed Markdown second brain. The user expects agents to use and maintain this vault more often than they do manually.

Read `AGENTS.md` first and follow it as the source of truth for vault operations.

## Core Behavior

- Treat Markdown files as the durable source of truth.
- Keep notes portable and readable outside Obsidian.
- Use Obsidian links, tags, YAML properties, Bases, and Canvas to improve navigation.
- Prefer `Bases` over `Dataview` for new structured views.
- Do not install or change plugins unless the user asks.
- Do not commit unless the user asks.

## Quick Paths

- Main dashboard: `HOME.md`
- Daily notes: `01-daily/`
- Dev notes: `02-dev-notes/`
- Projects: `03-projects/`
- Areas: `04-areas/`
- Resources: `05-resources/`
- Snippets: `06-snippets/`
- Decisions: `07-decisions/`
- Maps, Bases, Canvas: `08-maps/`
- Templates: `90-templates/`

## Default Creation Rules

- New daily note: `01-daily/YYYY-MM-DD.md`
- New dev note: `02-dev-notes/lower-kebab-case.md`
- New project: `03-projects/lower-kebab-case.md`
- New decision: `07-decisions/ADR-YYYY-MM-DD-short-topic.md`
- New rough capture: `00-inbox/lower-kebab-case.md`

Use templates from `90-templates/` whenever possible.

## Validation

After editing:

- Check Git status.
- Validate `.base` files as YAML if changed.
- Validate `.canvas` files as JSON if changed.
- Make sure important new notes are discoverable from `HOME.md`, a relevant MOC, or a linked project note.

