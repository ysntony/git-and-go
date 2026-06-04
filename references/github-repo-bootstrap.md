# GitHub Repo Bootstrap

Use this reference when a user needs a GitHub repo before repo-izing work.

## Default Position

Prefer one personal workspace repo per person, usually:

```text
repo-work
```

Individual projects should usually become folders inside this repo, not separate repos. This keeps the barrier low while still building repo-first habits.

## Preferred Path: GitHub CLI (`gh`)

Use GitHub CLI when available.

1. Check whether `gh` exists:

```bash
gh --version
```

2. Check auth:

```bash
gh auth status
```

3. If not authenticated, guide the user through login:

```bash
gh auth login
```

4. Create and clone a personal workspace repo:

```bash
gh repo create repo-work --private --clone
```

Use `--public` only when the user explicitly wants a public repo.

For an existing local folder:

```bash
gh repo create repo-work --private --source=. --remote=origin --push
```

## If `gh` Is Not Available

If GitHub CLI is unavailable, help the user create a GitHub repo manually in the browser, then connect it:

```bash
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
```

Provider APIs or tokens are optional fallback paths. Use them only when the user explicitly wants automation and understands token handling.

Security rules:

- Never ask the user to paste a token into repo files.
- Prefer environment variables or stdin.
- Do not echo tokens in terminal output, docs, commits, or chat summaries.
- Use the minimum scope that can create repos.

## First Commit In A New Workspace

If the repo was created without a README or first commit, create the first useful artifact instead of committing empty folders:

```bash
printf "# Repo Work\n\nRepo-first workspace for everyday work.\n" > README.md
git status --short
git add README.md
git commit -m "chore: initialize repo-first workspace"
git push -u origin main
```

Only create folders that are useful immediately. Git does not track empty folders, so prefer a useful starter markdown file over `.gitkeep` unless local convention requires `.gitkeep`.

## Other Git Providers

This public skill is GitHub-first. If the user explicitly wants GitLab, Bitbucket, or a company-hosted Git service, adapt the same repo-first workflow but use that provider's CLI or web UI for remote repo creation.

## Failure Handling

- If repo creation fails because the repo exists, clone or connect the existing repo.
- If authentication fails, explain whether `gh auth login`, token scope, or GitHub permission is the blocker.
- If push fails, check remote URL, branch name, and Git credentials before changing files.

## Official References

- GitHub CLI repo create: https://cli.github.com/manual/gh_repo_create
- GitHub CLI auth login: https://cli.github.com/manual/gh_auth_login
