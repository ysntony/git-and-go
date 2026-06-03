# Git and Go Skill Rollout

## Owner

Yu Shengnan

## Context

`git-and-go` is a Codex skill for helping Growth Marketing teammates work in a repo-first way.

The project started because teammates already use Codex, Claude Code, Feishu, GitLab, and local files, but many active projects have not yet been organized as durable repo artifacts with commit, push, and MR habits.

The current skill package includes:

- `SKILL.md` for the core behavior
- `references/` for repo, GitLab, Feishu, and existing-work onboarding workflows
- `assets/templates/` for project artifacts
- `agents/openai.yaml` for Codex UI metadata

## Goal

Make it easy for teammates to turn existing work into repo-based project folders, use the repo as the working source of truth, and run the ship loop:

```text
status -> diff -> add -> commit -> push -> MR context
```

## Current Thinking

- The skill should coach workflow, not business strategy.
- Existing projects are the most important onboarding case because many teammates already have work scattered across Feishu, local files, chats, and dashboards.
- A personal internally visible GitLab repo is enough to start before a shared Growth Marketing repo exists.
- Feishu should remain optional: useful as a source or publishing surface, but not the default source of truth.
- This repo is being used as the first self-test of the workflow.

## Current Status

- The skill package exists and has been pushed to GitLab.
- The skill has been installed locally at `/Users/moonshot/.codex/skills/git-and-go/`.
- The workflow has been strengthened for existing-work onboarding, repo-as-source-of-truth, ship loops, and personal GitLab repo workspaces.
- This project folder is the first repo artifact created by using the skill on itself.

## Open Questions

- Should this stay as a standalone skill or become a plugin later?
- What is the first real teammate workflow to test after this self-test?
- Should MR creation be handled manually, through GitLab CLI/API, or with a helper script?
- Does the skill need deploy workflow guidance for landing pages, sites, or tools?
- Should the project category remain `developer-growth`, or should future internal workflow projects use a separate category?

## Next Steps

- Review this project folder as a real user experience test.
- Commit and push this repo checkpoint.
- Prepare MR context that asks reviewers to check factual accuracy and usefulness.
- Use the skill on one real active Growth Marketing project next.
