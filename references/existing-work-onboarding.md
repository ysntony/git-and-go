# Existing Work Onboarding

Use this reference when a user already has an active project but it has not been organized as repo-first work.

## Goal

Convert scattered work into a small, durable repo workspace, then help the user start the Git loop.

Common sources:

- cloud docs, sheets, tasks, meetings, or chat threads
- local folders, screenshots, exports, creative assets, CSVs, or notes
- links to dashboards, websites, GitHub, GitLab, Figma, or asset storage
- verbal context from the user

## Default Flow

1. **Find the current shape**
   - Identify project name, owner, project area, current status, important links, and next action.
   - Ask only for missing information that blocks organizing the repo artifact.
   - Keep unknowns explicit instead of filling them in.

2. **Create the project workspace**
   - Use the repo's existing convention if present.
   - Otherwise use `projects/<area>/<yyyy-mm-project-name>/`.
   - Start with `brief.md`, `updates.md`, and `links.md`.
   - Add `decisions.md` only when decisions need their own log.

3. **Migrate facts, not strategy**
   - Capture what the user provided or what the source documents say.
   - Do not invent conclusions, judgments, strategy, or recommendations.
   - Record source links in `links.md`.
   - Record ambiguous or missing context under `Open Questions`.

4. **Set the working memory**
   - `brief.md`: owner, context, goal, current status, open questions, next steps.
   - `updates.md`: dated progress and next action.
   - `links.md`: GitHub/GitLab, cloud docs, assets, data, websites, dashboards, external references.
   - `decisions.md`: dated decisions, rationale, owner, and source when useful.

5. **Ship the first repo checkpoint**
   - Show changed files and meaningful diff.
   - Commit and push when the user asks to ship.
   - Prepare PR/MR context that asks reviewers to check factual completeness and accuracy.

## Example User Request

```text
Use $git-and-go to repo-ize my current project.
It is a home renovation planning project. The context is in this cloud doc and this local folder.
Create the project files, then help me commit, push, and prepare PR/MR context.
```

## Review Standard

For onboarded existing work, reviewers should check:

- Is the project folder in the right area?
- Are owner, status, links, and next steps accurate?
- Are open questions honest instead of guessed?
- Are source links and local asset references enough for another person or agent to continue?
