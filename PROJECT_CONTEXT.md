# Git and Go Project Context

## Background

This project started from a Growth Team workflow initiative at Kimi / Moonshot AI.

The team is Growth Marketing-focused, with work spanning ads, creative, social media, KOL partnerships, brand marketing, and developer growth such as GitHub / open-source / developer ecosystem collaboration.

The broader goal is to help the team become more AI-native and repo-native. Many teammates already use Codex, Claude Code, or similar tools, but the team has not yet fully built a shared habit around projects, repos, commits, pushes, merge requests, deployment, CI, or repo-as-source-of-truth workflows.

## Core Intent

`git-and-go` is not a business strategy skill.

It should not teach domain experts how to do ads, KOL, brand, social, creative, or developer growth work. The user or teammate remains the domain owner.

The skill exists to coach the workflow:

- turn work into durable repo artifacts
- help people think in project folders and source files
- make the repo the source of truth
- review diffs before committing
- help with commit / push / GitLab MR habits
- make Feishu CLI discoverable as an optional tool

The concise framing is:

> Repo-first, Feishu-optional, domain-owner-led.

## Important Principles

### Repo-first

Durable, reusable, reviewable, or AI-readable work should live in the repo.

Feishu docs, messages, sheets, or CRM records may be useful, but they should not replace the repo as the team's long-term source of truth.

### Feishu-optional

Feishu CLI is important because the team heavily uses Feishu products. However, the workflow should not automatically publish or sync everything to Feishu.

Use Feishu CLI only when:

- the user explicitly asks
- source context is already in Feishu
- it clearly reduces repetitive manual work
- the output needs to reach people who work primarily in Feishu

### Domain-owner-led

The skill should respect teammates as experts in their own business areas.

It should help with structure, versioning, artifacts, Git workflow, and collaboration mechanics. It should not invent business conclusions or override domain judgment.

### Teach while doing

The skill should help teammates learn Git and repo-native work through action:

- explain `status`, `diff`, `add`, `commit`, `push`, and MR concepts briefly when useful
- keep the work moving
- avoid turning every task into a long Git lecture

## Skill Shape

We chose to start with one skill, not many.

The first version is:

```text
git-and-go/
  SKILL.md
  agents/openai.yaml
  references/
    repo-workflow.md
    gitlab-workflow.md
    feishu-cli.md
  assets/templates/
    project-brief.md
    project-updates.md
    project-links.md
```

The reason is that `git-and-go` is one coherent operating model, not a set of unrelated commands.

Future separate skills may be useful only if a workflow becomes large, frequent, and stable enough to deserve its own trigger.

## Current Skill Behavior

The main skill should trigger when helping Growth Marketing teammates:

- create or update project folders
- turn ideas, chat notes, Feishu context, or loose work into repo artifacts
- organize repo structure
- review diffs
- commit and push work
- prepare GitLab merge request context
- optionally use Feishu CLI

The skill should generally follow this workflow:

1. Orient in the repo.
2. Decide whether the user is starting work, updating work, recording knowledge, running a routine, or shipping.
3. Create or update the smallest useful artifact.
4. Review changed files and diffs.
5. Commit / push / prepare MR only when requested.
6. Use Feishu only when requested or clearly useful.

## Suggested Business-Area Containers

If no existing repo structure exists, project-shaped work may use:

```text
projects/
  ads/
  creative/
  social/
  kol/
  brand/
  developer-growth/
```

`developer-growth/` covers GitHub, open-source, developer ecosystem, technical community, and developer partnership work.

These folders are containers, not playbooks. They should not imply the skill is teaching those domains.

## Naming Decision

We considered names including:

- `growth-marketing-os`
- `growth-marketing-repo`
- `ship-it`
- `git-and-go`

We chose `git-and-go` because it feels practical, lightweight, and action-oriented. It suggests helping teammates get unstuck on Git and move their work forward without making the project sound like a heavy operating-system rollout.

## Open Questions

- Should this stay as a standalone Skill or later become a Plugin for easier team distribution?
- Should the project root remain the skill root, or should the skill move under a larger repo structure?
- What is the first real team workflow to test with a teammate?
- How should GitLab MR creation be handled: CLI, manual instructions, or helper script?
- Which Feishu CLI recipes should be implemented as scripts once repeated patterns emerge?

## Next Good Steps

1. Initialize this directory as a Git repo.
2. Commit the first version of the skill.
3. Test the skill on one realistic workflow, such as creating a developer-growth project folder.
4. Refine `references/repo-workflow.md` based on that test.
5. Add only the scripts that become repeated and stable.
