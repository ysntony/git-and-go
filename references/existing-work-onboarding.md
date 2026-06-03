# Existing Work Onboarding

Use this reference when a teammate already has an active project but it has not been organized as repo-first work.

## Goal

Convert scattered work into a small, durable repo workspace, then help the teammate start the Git loop.

Common sources:

- Feishu docs, sheets, bases, tasks, meetings, or chat threads
- local folders, screenshots, exports, creative assets, CSVs, or notes
- links to ad platforms, dashboards, landing pages, GitLab, Figma, or asset storage
- verbal context from the teammate

## Default Flow

1. **Find the current shape**
   - Identify project name, owner, business area, current status, important links, and next action.
   - Ask only for missing information that blocks organizing the repo artifact.
   - Keep unknowns explicit instead of filling them in.

2. **Create the project workspace**
   - Use the repo's existing convention if present.
   - Otherwise use `projects/<area>/<yyyy-mm-project-name>/`.
   - Start with `brief.md`, `updates.md`, and `links.md`.
   - Add `decisions.md` only when decisions need their own log.

3. **Migrate facts, not strategy**
   - Capture what the teammate provided or what the source documents say.
   - Do not invent performance conclusions, creative judgments, channel strategy, or business recommendations.
   - Record source links in `links.md`.
   - Record ambiguous or missing context under `Open Questions`.

4. **Set the working memory**
   - `brief.md`: owner, context, goal, current status, open questions, next steps.
   - `updates.md`: dated progress and next action.
   - `links.md`: Feishu, GitLab, assets, data, landing pages, dashboards, external references.
   - `decisions.md`: dated decisions, rationale, owner, and source when useful.

5. **Ship the first repo checkpoint**
   - Show changed files and meaningful diff.
   - Commit and push when the user asks to ship.
   - Prepare MR context that asks reviewers to check factual completeness and accuracy.

## Example User Request

```text
Use $git-and-go to repo-ize my current ads project.
It is the June search landing test. The context is in this Feishu doc and this local asset folder.
Create the project files, then help me commit, push, and prepare an MR.
```

## Review Standard

For onboarded existing work, reviewers should check:

- Is the project folder in the right area?
- Are owner, status, links, and next steps accurate?
- Are open questions honest instead of guessed?
- Are source links and local asset references enough for another teammate or agent to continue?
