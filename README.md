# Wavenote for Claude Code

Reach your Wavenote library (getwavenote.com) from Claude Code: find a meeting and list its decisions, save a note, file it in a Space, add a task to Next, or read today's focus.

Your notes stay on your Mac or in your iCloud Drive. A request goes to getwavenote.com, the Wavenote gateway on your Mac answers it, and the server deletes the request and its answer an hour later.

The plugin adds the Wavenote MCP server (`https://getwavenote.com/api/v1/mcp`) and one skill. With it, Claude finds a note before reading it, waits for the Mac's answer, and asks before anything is deleted.

## Install

```
/plugin marketplace add heyramzi/wavenote-plugin
/plugin install wavenote@wavenote
```

Then run `/mcp`, pick `wavenote` and choose Authenticate. Your browser opens getwavenote.com: sign in with your Wavenote email, pick the Mac and press Allow.

You need:

- The Wavenote app on a Mac, and a Wavenote account. Get it at [getwavenote.com](https://getwavenote.com).
- The Wavenote gateway running on that Mac.
- The Mac awake. When it's asleep, a request waits 5 minutes, then expires, and nothing changes.

## Try

- "Find my notes about the pricing call and list every decision in them."
- "Save the ideas from this chat as a note in Wavenote."
- "Add a task to follow up with Dana, then show me what's in Next."
- "What's my focus today?"

## Limits

It can't record a meeting, take dictation or write a Wavenote+ summary. Those happen in the app. It can't read any file outside your Wavenote library either.

## Help

[getwavenote.com/support](https://getwavenote.com/support) or hello@getwavenote.com. Privacy: [getwavenote.com/privacy](https://getwavenote.com/privacy).

## Source

This folder lives at `products/wavenote/distribution/claude-plugin/` in the apple-apps monorepo. `skills/wavenote` there is a link to the OpenAI plugin's skill, so both plugins ship the same text. Publish it to `heyramzi/wavenote-plugin` with the link followed:

```bash
rsync -aL --delete --exclude .git products/wavenote/distribution/claude-plugin/ ../wavenote-plugin/
```
