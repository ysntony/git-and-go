# GitLab Workflow

Use this reference when the user asks to commit, push, create a merge request, or ship work.

## Safety Rules

- Never discard user changes unless explicitly asked.
- Inspect `git status` before staging.
- Stage only files related to the current task.
- Review meaningful diffs before committing.
- Do not commit secrets, tokens, private customer data, or accidental local artifacts.

## Ship Loop

Use this loop to make repo-first work visible and reviewable:

```bash
git status --short
git diff
git add <relevant-files>
git diff --cached
git commit -m "<type>: <short summary>"
git push
```

Use the repo's existing branch and commit conventions if present.

If the branch has no upstream yet, push with:

```bash
git push -u origin <branch>
```

If no remote exists, ask for the GitLab repository URL, then add it as `origin`. If there is no shared team repo, a personal internally visible GitLab repo is acceptable.

For a first personal workspace, suggest a simple repo name such as:

```text
growth-work
```

The GitLab URL will often look like:

```text
https://dev.msh.team/<username>/growth-work
```

## What to Ship

Stage only files related to the current work. For repo-onboarding or marketing operations, this often means:

- project folder files such as `brief.md`, `updates.md`, `links.md`, and optional `decisions.md`
- templates or workflow docs created for this task
- scripts that the task actually needs

Do not stage unrelated local notes, exports, screenshots, credentials, or generated clutter.

## Commit Messages

Prefer short, concrete messages:

```text
docs: add GitHub developer growth project brief
docs: update weekly growth review
chore: add repo-first workflow instructions
```

Useful prefixes:

- `docs:` for markdown, specs, notes, and reviews
- `chore:` for repo structure or workflow setup
- `feat:` for user-facing tools or automations
- `fix:` for correcting broken scripts, workflows, or docs

## Merge Request Context

If creating or preparing a GitLab MR, include:

```markdown
## What changed

## Why

## How to review

## Follow-ups
```

For non-engineering artifacts, "How to review" should tell reviewers what judgment is needed, not just which files changed.

For existing work that was newly repo-ized, reviewers should usually check factual accuracy:

```markdown
## What changed

Added repo source files for an in-progress project.

## Why

Move scattered project context, links, status, and next steps into the repo as the durable working record.

## How to review

Please check whether the owner, current status, links, open questions, and next steps are accurate.

## Follow-ups

Continue recording project updates in `updates.md`.
```

## Teaching Notes

When teammates are learning Git, keep explanations short:

- `status` shows what changed.
- `diff` shows exact edits.
- `add` chooses what goes into the commit.
- `commit` records a checkpoint.
- `push` sends local work to GitLab.
- MR asks others to review before merging.
