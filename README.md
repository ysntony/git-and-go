# git-and-go

Language: English | [中文](README.zh-CN.md)

`git-and-go` is a Codex / Claude Code / Kimi Code skill that helps people turn everyday work into repo-first, reviewable, AI-readable project artifacts.

It is GitHub-first: it helps you set up or use a personal GitHub repo, organize ongoing work into files, review diffs, commit, push, and prepare pull request context.

## What It Helps With

- Turn scattered notes, files, links, and chat context into a repo project folder.
- Use a repo as the source of truth for project context, updates, links, and decisions.
- Create lightweight project artifacts such as `brief.md`, `updates.md`, `links.md`, and `decisions.md`.
- Learn the Git loop by doing: `status -> diff -> add -> commit -> push -> pull request context`.
- Bootstrap a personal GitHub repo with `gh` when needed.

## Install In Codex

Ask Codex:

```text
Please install the git-and-go skill.
The repo is: https://github.com/ysntony/git-and-go
Install it to ~/.codex/skills/git-and-go.
After installing, tell me whether I need to restart Codex.
```

Or install manually:

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/ysntony/git-and-go.git ~/.codex/skills/git-and-go
```

Then restart Codex.

## Install In Claude Code

Ask Claude Code:

```text
Please install the git-and-go skill.
The repo is: https://github.com/ysntony/git-and-go
Install it to ~/.claude/skills/git-and-go.
After installing, tell me whether I need to restart Claude Code.
```

Or install manually:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/ysntony/git-and-go.git ~/.claude/skills/git-and-go
```

Then restart Claude Code.

## Install In Kimi Code

Ask Kimi Code:

```text
Please install the git-and-go skill.
The repo is: https://github.com/ysntony/git-and-go
Install it to ~/.kimi-code/skills/git-and-go.
After installing, tell me whether I need to restart Kimi Code.
```

Or install manually:

```bash
mkdir -p ~/.kimi-code/skills
git clone https://github.com/ysntony/git-and-go.git ~/.kimi-code/skills/git-and-go
```

Then restart Kimi Code.

## Use It

After installing, talk to Codex, Claude Code, or Kimi Code naturally:

```text
Use git-and-go to repo-ize my current project.
If I do not have a GitHub repo yet, help me create or connect a personal repo-work repo first.
Then organize the project files, review the diff, commit, push, and prepare pull request context.
```

Example:

```text
Use git-and-go to repo-ize my home renovation planning project.
I have notes in a local folder and links in a cloud doc.
Create the project files, review the diff, commit, push, and prepare pull request context.
```

## Update

Ask Codex, Claude Code, or Kimi Code:

```text
Please update the git-and-go skill to the latest version.
If I use Codex, update ~/.codex/skills/git-and-go.
If I use Claude Code, update ~/.claude/skills/git-and-go.
If I use Kimi Code, update ~/.kimi-code/skills/git-and-go.
After updating, tell me whether I need to restart.
```

Or update manually:

```bash
cd ~/.codex/skills/git-and-go
git pull
```

or:

```bash
cd ~/.claude/skills/git-and-go
git pull
```

or:

```bash
cd ~/.kimi-code/skills/git-and-go
git pull
```

Then restart your agent.
