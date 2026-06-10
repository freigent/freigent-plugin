# Build your own skill

The Freigent MCP tools (`list_pending_tasks`, `execute_sql_query`, `lookup_carrier_authority`, …)
are your extension point. Once the plugin is installed, **any** skill can use them — so you can teach
Claude your own back-office routines without touching this plugin's code.

A "skill" is just a folder with a `SKILL.md` file. That's the whole thing.

## The no-code way (recommended)

You don't have to write the file yourself. Tell Claude your routine in plain English:

> "I want a skill that, when I ask about overdue invoices, lists unpaid invoices past their due
> date, oldest first, with the broker name and how many days late — but never sends anything."

Claude will generate the `SKILL.md` and save it to `~/.claude/skills/<name>/`. From then on it
triggers automatically when you ask, or you can run it with `/<name>`.

## The manual way

1. Make a folder: `~/.claude/skills/my-skill/`
2. Add `SKILL.md` with a two-line header and your instructions. Copy `aging-invoices/SKILL.md` in
   this folder as a starting template.
3. That's it — Claude discovers it on next launch.

```
---
name: my-skill
description: When this should fire — the clearer this is, the better Claude knows when to use it.
---

# Instructions
What you want Claude to do, and which Freigent tools to use. Plain English.
```

## The one rule that still applies

Your skills run as **you** — they inherit your Freigent permissions and can't exceed them. And the
**money guardrail is enforced on the server, not in the skill**: no skill, no matter what its
instructions say, can auto-approve a payment, rate-con, or anything that moves money. That always
requires you. So build freely — you can't write a skill that opens a security hole.

See `aging-invoices/SKILL.md` for a complete, working example.
