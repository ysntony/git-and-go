# GitLab Workflow

Use this reference when the user asks to commit, push, create a merge request, or ship work.

## Safety Rules

- Never discard user changes unless explicitly asked.
- Inspect `git status` before staging.
- Stage only files related to the current task.
- Review meaningful diffs before committing.
- Do not commit secrets, tokens, private customer data, or accidental local artifacts.

## Basic Flow

```bash
git status --short
git diff
git add <relevant-files>
git diff --cached
git commit -m "<type>: <short summary>"
git push
```

Use the repo's existing branch and commit conventions if present.

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

## Teaching Notes

When teammates are learning Git, keep explanations short:

- `status` shows what changed.
- `diff` shows exact edits.
- `add` chooses what goes into the commit.
- `commit` records a checkpoint.
- `push` sends local work to GitLab.
- MR asks others to review before merging.
