# git-and-go

语言：[English](README.md) | 中文

`git-and-go` 是一个可以在 Codex / Claude Code 里使用的 skill。它帮助你把日常工作整理成 repo 里的项目文件，让 repo 成为项目事实源，并带着你完成检查改动、提交、推送和准备 Pull Request 描述。

这个公开版本以 GitHub 为默认平台：如果你还没有 repo，它会优先帮助你用 GitHub 和 `gh` 创建或连接一个个人工作 repo。

## 它能帮你做什么

- 把散落的笔记、文件、链接、聊天上下文整理成 repo 里的项目目录。
- 把 repo 作为项目背景、进展、链接和决策的事实源。
- 创建轻量项目文件，例如 `brief.md`、`updates.md`、`links.md`、`decisions.md`。
- 在真实工作中学习 Git 流程：`status -> diff -> add -> commit -> push -> pull request context`。
- 需要时帮你用 `gh` 创建个人 GitHub repo。

## 在 Codex 里安装

直接对 Codex 说：

```text
请帮我安装 git-and-go skill。
仓库地址是：https://github.com/ysntony/git-and-go
请安装到 ~/.codex/skills/git-and-go。
安装完成后，请告诉我是否需要重启 Codex。
```

也可以手动安装：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/ysntony/git-and-go.git ~/.codex/skills/git-and-go
```

然后重启 Codex。

## 在 Claude Code 里安装

直接对 Claude Code 说：

```text
请帮我安装 git-and-go skill。
仓库地址是：https://github.com/ysntony/git-and-go
请安装到 ~/.claude/skills/git-and-go。
安装完成后，请告诉我是否需要重启 Claude Code。
```

也可以手动安装：

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/ysntony/git-and-go.git ~/.claude/skills/git-and-go
```

然后重启 Claude Code。

## 如何使用

安装后，直接用自然语言和 Codex / Claude Code 对话：

```text
使用 git-and-go 帮我把当前项目 repo 化。
如果我还没有 GitHub repo，请先帮我创建或连接一个个人 repo-work repo。
然后帮我整理项目文件，检查 diff，commit，push，并准备 Pull Request 描述。
```

例如：

```text
使用 git-and-go 帮我把我的租房整理项目 repo 化。
我有一些本地笔记和云文档链接。
请帮我创建项目文件，检查 diff，commit，push，并准备 Pull Request 描述。
```

## 如何更新

直接对 Codex / Claude Code 说：

```text
请帮我把 git-and-go skill 更新到最新版。
如果我使用 Codex，请更新 ~/.codex/skills/git-and-go。
如果我使用 Claude Code，请更新 ~/.claude/skills/git-and-go。
更新完成后，请告诉我是否需要重启。
```

也可以手动更新：

```bash
cd ~/.codex/skills/git-and-go
git pull
```

或者：

```bash
cd ~/.claude/skills/git-and-go
git pull
```

然后重启你正在使用的 agent。
