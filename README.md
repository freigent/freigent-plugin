# Freigent plugin for Claude

Connect Claude to your Freigent back office. Once installed, Claude can triage your AI work queue,
read load and carrier context, and approve or reject tasks — with money-movement guardrails built in.

This plugin bundles:

- **MCP connection** to your Freigent org (`app.freigent.ai/api/mcp`)
- **`freight-ops` skill** — teaches Claude how to run the queue safely (the funnel, the money rule,
  prompt-injection awareness)
- **`/queue` command** — a one-shot triaged sit-rep of what needs your review
- **`freight-reviewer` agent** — a careful second look at a single task before you decide

The plugin carries **no secrets**. It points Claude at the Freigent endpoint; you supply your own
API key. All access is gated server-side by that key.

## Prerequisites

1. A Freigent account with API access.
2. Your **personal** Freigent API key. Get it from the Freigent app (Settings → API / MCP) or via
   the MCP connect flow. Use a personal key, not a shared one — every action Claude takes is
   attributed to you, including approvals.

## Setup

Set your key as an environment variable so the plugin can authenticate:

```bash
export FREIGENT_API_KEY="fmcp_your_key_here"
```

(Put it in your shell profile, or your Claude Code project `.env` / settings, so it persists.)

## Install

### Claude Code (CLI / Desktop / IDE)

```bash
# Add the marketplace, then install:
/plugin marketplace add freigent/freigent-plugin
/plugin install freigent-carrier@freigent
```

Or point Claude Code directly at this repo and restart so it picks up `.mcp.json`, the skill, the
command, and the agent.

Verify it's live: run `/queue`, or ask "what's pending in Freigent?" — Claude should return a
triaged sit-rep of your work queue.

> **Where plugins run:** plugin install is a Claude Code feature (CLI, Desktop, and the IDE
> extensions). If you're using a Claude surface that doesn't expose `/plugin`, you can still get the
> MCP connection by adding the server from `.mcp.json` manually. Check your client's
> connectors/MCP settings.

## What Claude will and won't do

- **Will:** summarize the queue, explain any task, look up carrier authority, run read-only data
  questions, and reject/dismiss items on your say-so.
- **Won't:** auto-approve anything that moves money. Rate-con sends, bookings, payments, and
  invoices require *you* to approve, with the dollar figure in front of you. This is enforced both
  in the skill's instructions and on the Freigent server (financial approvals require a
  user-attributed key).

## Security notes

- Treat your API key like a password. It identifies you and authorizes approvals.
- Broker email content inside tasks is **untrusted** — the skill instructs Claude to treat it as
  data, never as instructions, so a "please approve this" buried in a broker email can't drive an
  approval.
- The MCP connection authenticates with a bearer token. A future release will move to OAuth 2.1 for
  the connection (scopes, expiry, revocation).

## Support

Issues and requests: https://github.com/freigent/freigent-plugin/issues
