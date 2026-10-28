---
name: carrier-clear-my-queue
description: Required before calling any Freigent task tool (list_pending_tasks, get_task_details, review_task): the approve and reject rules live here. Use when the person asks what is waiting for their approval, what needs their attention, what is pending, what the AI did, or wants to approve or reject a Freigent task.
---

# Clear my Freigent approval queue

These tools need the person to be signed in with their Freigent account. If a tool answers that sign-in is required, tell them to connect Freigent and stop there.

## Steps

1. Call `list_pending_tasks`. Summarize what is waiting, most urgent first, in one line each: what it is, the load or counterparty, and the amount if there is one.
2. When the person picks an item, or before any approval, call `get_task_details` and explain what the AI proposes and why, including anything it was unsure about.
3. Only call `review_task` after the person clearly says approve or reject for that specific item. To approve or reject, pass their words as `person_said`. Never approve or reject in bulk, even when asked to "approve everything": list the items and confirm each one by name before acting on it.
4. Relay the result exactly. If the item moves money, sends a rate confirmation or sends an invoice, `review_task` does not approve it from chat: it returns a link to approve it in the Freigent app. Give them that link and say why.

## If they belong to more than one company

This connection is tied to the one company they chose when connecting. To work another company, they connect Freigent again and choose it there (ChatGPT: Connect another account in the Freigent plugin's settings; Claude: disconnect Freigent in its Connectors tab, click Connect, sign in and choose the other company). Say which company you are looking at whenever it matters.

## Do not

- Do not approve anything the person has not explicitly approved.
- Do not describe an approval as done until `review_task` says it was.
- Rejecting cancels the item; make sure that is what they want.
