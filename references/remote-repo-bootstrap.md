# Remote Repo Bootstrap

Use this reference when a user needs a GitHub or GitLab repo before repo-izing work.

## Default Position

Prefer one personal workspace repo per person, usually:

```text
repo-work
```

Individual projects should usually become folders inside this repo, not separate repos. This keeps the barrier low while still building repo-first habits.

## Preferred Path: GitHub CLI (`gh`)

Use GitHub CLI when the user wants a GitHub repo and `gh` is available.

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

## Preferred Path: GitLab CLI (`glab`)

Use GitLab CLI when the user wants a GitLab repo and `glab` is available.

1. Check whether `glab` exists:

```bash
glab --version
```

2. Check auth:

```bash
glab auth status
```

For self-managed GitLab:

```bash
glab auth status --hostname <gitlab-host>
```

3. If not authenticated, guide the user through login:

```bash
glab auth login
```

For self-managed GitLab:

```bash
glab auth login --hostname <gitlab-host>
```

4. Create the personal workspace repo:

```bash
glab repo create repo-work --private --readme README.md
```

For self-managed GitLab, set the host if needed:

```bash
GITLAB_HOST=<gitlab-host> glab repo create repo-work --private --readme README.md
```

If the user wants an internal company repo and the GitLab instance supports internal visibility, use `--internal`.

5. Clone or connect:

```bash
git clone <remote-url>
```

For an existing local folder:

```bash
git remote add origin <remote-url>
```

## Fallback Path: Provider API Token

Use provider APIs only when `gh` or `glab` is unavailable or unsuitable.

Security rules:

- Never ask the user to paste a token into repo files.
- Prefer environment variables or stdin.
- Do not echo tokens in terminal output, docs, commits, or chat summaries.
- Use the minimum scope that can create repos/projects.

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

## Failure Handling

- If repo creation fails because the repo exists, clone or connect the existing repo.
- If authentication fails, explain whether CLI login, token scope, or provider permission is the blocker.
- If push fails, check remote URL, branch name, and Git credentials before changing files.

## Official References

- GitHub CLI repo create: https://cli.github.com/manual/gh_repo_create
- GitHub CLI auth login: https://cli.github.com/manual/gh_auth_login
- GitLab CLI repo create: https://docs.gitlab.com/cli/repo/create/
- GitLab CLI auth login: https://docs.gitlab.com/cli/auth/login/
