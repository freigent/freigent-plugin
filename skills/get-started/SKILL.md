---
name: get-started
description: Use first when someone has just added Freigent, asks what Freigent is or what it can do, asks which Freigent account they are connected to, or it is unclear whether they are a dispatcher, carrier or broker rep. It routes them to negotiate-load or carrier-clear-my-queue.
---

# Getting started with Freigent

Freigent negotiates loads by email for dispatchers, carriers and broker reps. With an inbox connected to Freigent it lists the replies in their inbox (broker load offers for a carrier or dispatcher, carrier quotes for a broker rep), works out the counter from the person's own numbers, and sends the reply they approve in the same email thread. Carriers who run their back office on Freigent can also review what its agents are waiting to do.

The tools need a free Freigent sign-in. Mention it only when a tool asks for sign-in; then say it is free and takes one step. Once a tool has returned the user's data, they are signed in: do not tell them to sign in.

Until a tool says which side the account is on, do not assume it: say "replies" or "offers", not "which brokers replied", to someone who may be a broker rep.

## Route

| Who | What they want | Do this |
|---|---|---|
| Dispatcher, carrier or broker rep | "Which brokers replied?", "any new loads?" | Follow the `negotiate-load` skill, inbox path |
| Dispatcher, carrier or broker rep | Pasted or described offer: what to counter, how to reply | Follow the `negotiate-load` skill, pasted path |
| Carrier using Freigent | See or act on what is waiting for approval | Follow the `carrier-clear-my-queue` skill |
| Broker rep | See or act on their Workflow tasks | Broker Workflow tasks are not available in chat yet; point them to Freigent (app.freigent.ai, Workflow) |
| Anyone | How Freigent works | Call `search_docs` |

## Rules

- Never invent a rate, market rate, MC number, DOT number or email address.
- Keep it short. Answer the question that was asked, then offer the one next step.
