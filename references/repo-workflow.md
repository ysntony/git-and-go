# Repo Workflow

Use this reference when the repo has no stronger local convention.

## Minimal Root Structure

```text
.
  AGENTS.md
  CLAUDE.md
  projects/
  knowledge/
  routines/
  templates/
  scripts/
```

Do not create all folders automatically. Create only what the current task needs.

## Personal Repo First

If there is no shared repo yet, a user's own GitHub repo is a valid starting point.

Prefer one personal workspace repo per person, for example:

```text
repo-work
```

Inside that repo, use the same structure:

```text
projects/
knowledge/
routines/
templates/
scripts/
```

This keeps the barrier low while still building repo-first habits. The personal repo can be the current source of truth until a shared repo exists. Later, project folders can be copied or migrated into the shared repo.

When the personal repo does not exist yet, use `references/github-repo-bootstrap.md` to create it with `gh` before organizing project files.

## Top-Level Meaning

- `projects/`: active or completed project-shaped work with owner, context, updates, links, and decisions.
- `knowledge/`: durable references, definitions, research notes, channel context, metrics notes, and tool notes.
- `routines/`: recurring workflows such as weekly reviews, feedback digests, reporting, or repeated operational checks.
- `templates/`: reusable source templates for project briefs, updates, reviews, and other artifacts.
- `scripts/`: helper scripts for repeatable tasks, including optional GitHub or cloud-tool helpers.

## Project Categories

Use project-area folders only as containers, not as strategy guides. Choose names that match the user's life and work:

```text
projects/
  work/
  personal/
  learning/
  home/
  creative/
  finance/
```

Use a new area only when it helps the user find work later.

## Project Folder Naming

Prefer date-prefixed, lowercase, hyphenated names:

```text
projects/work/2026-06-portfolio-refresh/
projects/home/2026-06-kitchen-planning/
projects/learning/2026-06-python-course/
```

If the work is not date-bound, omit the date:

```text
knowledge/metrics/activation-definitions.md
knowledge/tools/automation-notes.md
```

## Minimal Project Files

For a new project, create the smallest useful set:

```text
brief.md
updates.md
links.md
```

Use only `brief.md` if the user is still exploring. Add other files when they become useful. For existing work being moved into the repo, prefer all three files so the repo can immediately become working memory.

### `brief.md`

Capture what the user already knows. Do not invent strategy.

```markdown
# Project Name

## Owner

## Context

## Goal

## Current Thinking

## Open Questions

## Next Steps
```

### `updates.md`

Append dated updates:

```markdown
# Updates

## YYYY-MM-DD

- Progress:
- Decisions:
- Risks:
- Next:
```

### `links.md`

Track source and collaboration links:

```markdown
# Links

- Cloud docs:
- GitHub:
- Assets:
- Data:
- External:
```

## Repo as Source of Truth

Treat repo artifacts as the durable record for project state:

- `brief.md`: what this project is, who owns it, why it exists, current status, open questions, and next steps.
- `updates.md`: dated progress, decisions, risks, and next action.
- `links.md`: where source material, collaboration surfaces, assets, data, and deployed outputs live.
- `decisions.md`: optional dated decision log when decisions need a separate trail.

External tools are not ignored:

- cloud docs, sheets, chats, and meetings can be source material or human-facing collaboration surfaces.
- local folders can hold raw assets or exports, but the repo should record what they are and where they live.
- dashboards and external tools can remain systems of execution, but the repo should link to them and record the working interpretation supplied by the user.

When a fact changes, update the repo artifact first or in the same working session as the external update. Avoid leaving important project state only in chat, local desktop files, or memory.

## Knowledge Artifacts

Use `knowledge/` for durable facts that multiple projects may reference:

```text
knowledge/topics/
knowledge/people/
knowledge/metrics/
knowledge/tools/
```

Do not move active project work into `knowledge/` just because it contains notes.

## Routine Artifacts

Use `routines/` for repeated processes:

```text
routines/weekly-review/
routines/reading-notes/
routines/project-review/
```

A routine should contain source templates, scripts, and generated outputs only when needed.

## Agent Instructions

If creating repo-level agent files, keep them short:

- `AGENTS.md`: rules for Codex and other coding agents.
- `CLAUDE.md`: Claude Code-specific mirror or additions.
- Kimi Code uses `SKILL.md` skills too; add tool-specific mirror files only when the repo already uses them.

Both should reinforce:

- repo-first durable artifacts
- user-led work
- diff before commit
- GitHub repo creation with `gh` when needed
