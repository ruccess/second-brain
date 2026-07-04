# Claude Instructions

This is a Git-managed Markdown second brain. The user expects agents to use and maintain this vault more often than they do manually.

Read `AGENTS.md` first and follow it as the source of truth for vault operations.

## Core Behavior

- Treat Markdown files as the durable source of truth.
- Keep notes portable and readable outside Obsidian.
- Use Obsidian links, tags, YAML properties, Bases, and Canvas to improve navigation.
- Use Korean-only filenames and H1 titles for graph-visible knowledge notes.
- Prefer `Bases` over `Dataview` for new structured views.
- Do not install or change plugins unless the user asks.
- Do not commit unless the user asks.

## Quick Paths

- Main dashboard: `홈.md`
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
- New dev note: `02-dev-notes/한국어 노트 제목.md`
- New project: `03-projects/한국어 프로젝트명.md`
- New decision: `07-decisions/의사결정 YYYY-MM-DD 한국어 주제.md`
- New rough capture: `00-inbox/한국어 캡처 제목.md`

Use templates from `90-templates/` whenever possible.

Obsidian graph labels come from filenames, so do not create new graph-visible notes with English slugs such as `git-managed-markdown.md` unless the user explicitly asks.

## Validation

After editing:

- Check Git status.
- Validate `.base` files as YAML if changed.
- Validate `.canvas` files as JSON if changed.
- Make sure important new notes are discoverable from `홈.md`, a relevant MOC, or a linked project note.
