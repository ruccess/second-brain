# Agent Instructions

This repository is a Git-managed Markdown second brain. The user will usually rely on agents to maintain structure, create notes, connect knowledge, and keep the vault tidy.

## Priorities

1. Preserve Markdown files as the source of truth.
2. Keep the vault portable across Obsidian and plain text tools.
3. Prefer small linked notes over large monolithic documents.
4. Use Git carefully; never discard user changes.
5. Make the graph useful with clear links, tags, and properties.

## Internal Skill

- Repository-local skill: `skills/second-brain-vault/SKILL.md`.
- Use it when maintaining this vault's notes, tasks, links, Bases, Canvas maps, templates, or agent instructions.
- This skill is intentionally kept inside the repository so agents can inspect it even when it is not globally installed.

## Repository Layout

- `00-inbox/`: rough capture, temporary notes, unprocessed ideas.
- `01-daily/`: daily notes, daily goals, logs, reflections.
- `02-dev-notes/`: development concepts, debugging notes, architecture notes.
- `03-projects/`: active or paused projects.
- `04-areas/`: long-running responsibilities and themes.
- `05-resources/`: references, setup notes, external knowledge summaries.
- `06-snippets/`: commands, code snippets, reusable patterns.
- `07-decisions/`: ADR-style decision records.
- `08-maps/`: MOCs, `.base` views, `.canvas` visual maps.
- `90-templates/`: reusable Obsidian/Templater templates.
- `99-archive/`: inactive or historical material.
- `assets/`: images, files, and attachments used by notes.

## Note Rules

- Use YAML frontmatter for structured notes.
- Use Obsidian wikilinks: `[[note-name]]` or `[[note-name|Readable Label]]`.
- For graph-visible knowledge notes, the filename and H1 title must be Korean.
- Use natural Korean filenames with spaces when that makes the graph easier to read.
- Use ISO dates: `YYYY-MM-DD`.
- Keep tags lowercase and purposeful.
- Use Markdown checkboxes for tasks.
- Use the Tasks plugin due-date style when dates matter: `📅 YYYY-MM-DD`.

Examples:

- Good: `02-dev-notes/리액트 상태 설계.md`
- Good: `03-projects/세컨드 브레인.md`
- Good: `07-decisions/의사결정 2026-07-04 깃으로 마크다운 관리.md`
- Avoid for graph-visible notes: `git-managed-markdown.md`, `react-state-design.md`

Exceptions:

- Date notes such as `01-daily/2026-07-04.md`.
- Agent/system files such as `README.md`, `AGENTS.md`, `CLAUDE.md`, and `SKILL.md`.
- Machine-readable support files such as `.base`, `.canvas`, `.json`, and ignored plugin/theme files.
- Code identifiers, commands, package names, and official product names inside note bodies.

## Common Frontmatter

```yaml
---
type: dev-note
status: draft
created: 2026-07-04
tags:
  - dev
---
```

Recommended `type` values:

- `daily`
- `dev-note`
- `project`
- `area`
- `resource`
- `snippet`
- `decision`
- `retrospective`
- `moc`
- `dashboard`

Recommended `status` values:

- `draft`
- `active`
- `seed`
- `accepted`
- `paused`
- `done`
- `archived`

## Agent Workflow

When adding or editing notes:

1. Inspect existing notes before creating new structure.
2. Reuse templates from `90-templates/` when appropriate.
3. Add links to related notes in both the body and frontmatter tags when useful.
4. Update `HOME.md` or an MOC only when the change should be discoverable from the main dashboard.
5. Put rough, unclassified material in `00-inbox/`.
6. Put long-term, organized material in the correct numbered folder.

## Daily Notes

- Create daily notes in `01-daily/YYYY-MM-DD.md`.
- Use the local calendar date.
- Daily notes should contain:
  - purpose
  - tasks
  - log
  - reflection
  - links
- Connect daily notes to projects, dev notes, and decisions mentioned that day.

## Development Notes

Development notes belong in `02-dev-notes/`.

Good dev notes include:

- the problem or concept
- why it matters
- examples or commands
- related project links
- related decision links

Avoid dumping huge unstructured logs into dev notes. Summarize, link, and move raw material to `00-inbox/` or `assets/` when needed.

## Decisions

Use `07-decisions/` for ADR-style records.

Filename pattern:

```text
의사결정 YYYY-MM-DD 한국어 주제.md
```

Decision notes should include:

- context
- decision
- consequences
- links

## Tasks

- Keep tasks in the note where the work belongs.
- Use `#task` for tasks that should be collected by the Tasks plugin.
- Use due dates only when they are real commitments.
- Do not create a separate task database unless the user asks.

Example:

```markdown
- [ ] Write project review #task #second-brain 📅 2026-07-05
```

## Bases And Canvas

- `.base` files live in `08-maps/`.
- `.canvas` files live in `08-maps/`.
- Validate `.base` files as YAML after editing.
- Validate `.canvas` files as JSON after editing.
- Prefer Bases over Dataview for default structured views.
- Use Canvas for visual maps, architecture sketches, and conceptual layouts.

## Obsidian Settings

- Track lightweight vault settings when they help reproduce the system.
- Do not track downloaded plugin or theme code.
- `.obsidian/plugins/`, `.obsidian/themes/`, and workspace files are ignored.
- Do not install, enable, or remove plugins unless the user asks.

## Git Rules

- Check `git status --short --branch` before and after significant edits.
- Never run destructive Git commands unless the user explicitly asks.
- Do not commit unless the user asks.
- If committing, keep messages plain and descriptive.
- Do not rewrite or clean up the user's personal writing without permission.

## Writing Style

- Keep notes concise and reusable.
- Prefer clear headings over heavy formatting.
- Preserve the user's language when editing personal notes.
- Use Korean for graph-visible filenames and H1 titles.
- Use Korean for user-facing personal notes unless preserving a direct technical term is necessary.
- Do not over-automate the vault; make the next useful thing simple.
