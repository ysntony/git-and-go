# Feishu CLI

Feishu CLI is an optional collaboration tool. Use it when the user asks, when source context is in Feishu, or when it avoids repetitive manual work.

Do not publish repo artifacts to Feishu by default.

## Before Using Feishu CLI

Check:

- Is the user asking to read, create, update, or send something in Feishu?
- Is there a Feishu document, sheet, CRM, chat, meeting, or task URL/token to work from?
- Does the operation require permissions or identity selection?
- Should the resulting Feishu link be written back to a repo artifact?

## Common Recipes

### Read Feishu Context into Repo

Use when the user provides a Feishu doc, sheet, chat, meeting, or CRM context and wants it turned into a repo artifact.

1. Read the Feishu source with the appropriate lark/Feishu CLI or skill.
2. Summarize or structure the content without inventing business conclusions.
3. Create or update the repo artifact.
4. Add the Feishu source link in `links.md` or the artifact front matter.

### Create a Feishu Doc from Markdown

Use when the user explicitly wants a human-facing document.

1. Ensure the repo markdown source exists.
2. Convert or upload it with Feishu CLI.
3. Capture the Feishu URL.
4. Write the URL back to the relevant repo artifact when useful.

### Update a Feishu Sheet or CRM

Use when the user asks for structured operational updates.

1. Confirm target sheet/base/CRM record if not obvious.
2. Prefer structured rows or fields over prose.
3. Keep the repo source as the durable record when appropriate.
4. Record links or IDs back in the project folder.

### Send a Feishu Message

Use when the user asks to notify a group or person.

1. Draft the message from repo facts.
2. Keep it concise and action-oriented.
3. Send only after the user confirms the audience if not already specified.

## Useful Repo Patterns

Track Feishu links in:

```text
projects/<area>/<project>/links.md
```

or in markdown front matter:

```yaml
feishu_url: ""
```

## Guardrails

- Do not leak private data into public repo files.
- Do not send Feishu messages without a clear target.
- Do not create new Feishu docs just because a repo artifact changed.
- If Feishu auth or permission fails, explain the specific blocker and continue with repo work when possible.
