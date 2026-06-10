---
name: aging-invoices
description: Surface overdue / aging accounts-receivable. Use when the user asks about unpaid invoices, overdue brokers, AR aging, "who owes us money", or collections priorities.
---

# Aging invoices — AR follow-up

When the user asks about overdue money owed to them, pull it from the Freigent MCP tools and present
it as a prioritized collections list — oldest and largest first.

1. Use `execute_sql_query` to read unpaid invoices that are past due. (org scope is automatic — do
   not add org_id.) Pull the broker/customer, invoice number, amount, due date, and days overdue.
2. Sort by **days overdue, then amount** — the oldest, biggest debts surface first.
3. Summarize: total outstanding, count, and the top few that need a call/email today. One line each:
   "Acme Logistics — $3,200, 41 days overdue."
4. Stop there. Do **not** send anything or take action — collections outreach is the user's call.
   If they ask you to follow up, draft the message for *them* to send; never send broker email
   yourself.

This is read-only. It never moves money or contacts anyone — it just tells the user where to look.
