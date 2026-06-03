# GitLab Repo Bootstrap

Use this reference when a teammate needs a GitLab repo before repo-izing work.

## Default Position

Prefer one personal workspace repo per teammate, usually:

```text
growth-work
```

Use an internally visible GitLab repo when possible. Individual projects should usually become folders inside this repo, not separate repos.

## Preferred Path: `glab`

Use GitLab CLI (`glab`) first when available.

1. Check whether `glab` exists:

```bash
glab --version
```

2. Check auth:

```bash
glab auth status --hostname dev.msh.team
```

3. If not authenticated, guide the user through login:

```bash
glab auth login --hostname dev.msh.team
```

If the user has a personal access token and wants non-interactive login, use stdin instead of putting the token in the command:

```bash
glab auth login --hostname dev.msh.team --stdin
```

4. Create the personal workspace repo:

```bash
GITLAB_HOST=dev.msh.team glab repo create growth-work --internal --readme README.md
```

If `--internal` is unsupported by the installed `glab` version, inspect `glab repo create --help` and choose the matching visibility flag. If visibility cannot be set from CLI, create the repo and ask the user to confirm or adjust visibility in GitLab.

5. Clone or connect:

```bash
git clone https://dev.msh.team/<username>/growth-work.git
```

For an existing local folder:

```bash
git remote add origin https://dev.msh.team/<username>/growth-work.git
```

## Fallback Path: GitLab API Token

Use the API only when `glab` is unavailable or unsuitable.

Security rules:

- Never ask the user to paste a token into repo files.
- Prefer environment variables or stdin.
- Do not echo tokens in terminal output, docs, commits, or chat summaries.
- Use the minimum scope that can create projects. If unsure, ask the GitLab admin or use `api` only for the bootstrap step.

Create a project owned by the authenticated user:

```bash
curl --request POST \
  --header "PRIVATE-TOKEN: $GITLAB_TOKEN" \
  --header "Content-Type: application/json" \
  --data '{"name":"growth-work","path":"growth-work","visibility":"internal","initialize_with_readme":true}' \
  --url "https://dev.msh.team/api/v4/projects"
```

Then clone:

```bash
git clone https://dev.msh.team/<username>/growth-work.git
```

## First Commit In A New Workspace

If the repo was created without a README or first commit, create the first useful artifact instead of committing empty folders:

```bash
mkdir -p projects
printf "# Growth Work\n\nRepo-first workspace for Growth Marketing work.\n" > README.md
git status --short
git add README.md
git commit -m "chore: initialize repo-first workspace"
git push -u origin main
```

Only create folders that are useful immediately. Git does not track empty folders, so prefer a useful starter markdown file over `.gitkeep` unless local convention requires `.gitkeep`.

## Failure Handling

- If repo creation fails because the repo exists, clone or connect the existing repo.
- If authentication fails, explain whether `glab auth login`, token scope, or GitLab permission is the blocker.
- If push fails, check remote URL, branch name, and Git credentials before changing files.

## Official References

- `glab auth login`: https://docs.gitlab.com/cli/auth/login/
- `glab repo create`: https://docs.gitlab.com/cli/repo/create/
- GitLab Projects API: https://docs.gitlab.com/api/projects/
