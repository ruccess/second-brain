---
name: second-brain-vault
description: Maintain this repository as a Git-managed Markdown second brain. Use when Codex needs to create, update, organize, connect, review, or validate notes, daily logs, TODOs, development notes, project notes, ADRs, Bases, Canvas maps, Obsidian vault settings, or agent instructions inside this vault.
---

# Second Brain Vault

Use this skill to work on this vault as a durable Markdown knowledge system, not as an app project.

## First Moves

1. Read `AGENTS.md` before making structural changes.
2. Check `git status --short --branch`.
3. Inspect existing notes with `rg --files` and targeted `rg` searches before creating new files.
4. Keep edits small, linked, and easy to review.
5. Do not commit unless the user explicitly asks.

## Source Of Truth

- Treat `.md`, `.base`, `.canvas`, and lightweight `.obsidian/*.json` files as source.
- Do not track downloaded plugin or theme code.
- Do not introduce a custom app, database, or build system unless the user explicitly changes direction.
- Keep the vault usable as plain Markdown even if Obsidian is unavailable.

## Folder Placement

- `00-inbox/`: rough captures and unprocessed thoughts.
- `01-daily/`: daily notes, daily goals, logs, reflections.
- `02-dev-notes/`: development knowledge, debugging notes, architecture notes.
- `03-projects/`: project pages and project task context.
- `04-areas/`: long-running responsibilities or themes.
- `05-resources/`: references, setup notes, external summaries.
- `06-snippets/`: commands, code snippets, reusable patterns.
- `07-decisions/`: ADR-style decision records.
- `08-maps/`: MOCs, `.base` views, `.canvas` maps.
- `90-templates/`: reusable note templates.
- `99-archive/`: inactive material.
- `assets/`: attachments used by notes.

## Note Creation

Use existing templates from `90-templates/` when they fit. Use lower-kebab-case filenames for durable notes.

Daily note:

```text
01-daily/YYYY-MM-DD.md
```

Development note:

```text
02-dev-notes/lower-kebab-case.md
```

Project note:

```text
03-projects/lower-kebab-case.md
```

Decision note:

```text
07-decisions/ADR-YYYY-MM-DD-short-topic.md
```

## Frontmatter

Use concise YAML properties so Bases can index notes.

```yaml
---
type: dev-note
status: draft
created: 2026-07-04
tags:
  - dev
---
```

Preferred `type` values:

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

Preferred `status` values:

- `draft`
- `seed`
- `active`
- `accepted`
- `paused`
- `done`
- `archived`

## Links And Graph Shape

- Use Obsidian wikilinks: `[[note-name]]` or `[[note-name|Readable Label]]`.
- Add links where a future reader would naturally continue.
- Keep `HOME.md` and relevant MOCs useful, but do not turn them into dumping grounds.
- Prefer meaningful connections over tag spam.
- When adding an important note, connect it from at least one of:
  - `HOME.md`
  - `08-maps/MOC-second-brain.md`
  - a project note
  - a daily note

## Tasks

- Keep tasks where the work context lives.
- Use `#task` for tasks meant to appear in task queries.
- Add due dates only for real commitments.

```markdown
- [ ] Write project review #task #second-brain 📅 2026-07-05
```

## Bases And Canvas

- Prefer Obsidian Bases over Dataview for new structured views.
- Store `.base` files in `08-maps/`.
- Store `.canvas` files in `08-maps/`.
- Validate `.base` files as YAML after editing.
- Validate `.canvas` files as JSON after editing.
- Use Canvas for visual maps, architecture sketches, and concept maps.

Validation examples:

```bash
ruby -ryaml -e 'ARGV.each { |f| YAML.load_file(f) }' 08-maps/*.base
ruby -rjson -e 'ARGV.each { |f| JSON.parse(File.read(f)) }' 08-maps/*.canvas
```

## Writing Style

- Use Korean for personal notes and user-facing notes unless the existing note is English or technical naming is clearer in English.
- Keep agent-facing instructions concise and in English unless Korean is explicitly requested.
- Preserve the user's personal wording in reflections and daily notes.
- Summarize raw logs into useful notes instead of pasting long dumps.

## Safe Git Practice

- Always check status before and after edits.
- Never discard or rewrite user changes.
- Keep plugin and theme code ignored.
- If the user asks for a commit, stage only intended files and use a plain message.

## Done Criteria

Before finishing:

1. Run `git status --short --branch`.
2. Validate changed `.base` and `.canvas` files.
3. Confirm important new notes are discoverable.
4. Tell the user what changed and whether anything remains uncommitted.

