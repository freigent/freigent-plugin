---
description: Show the Freigent AI work queue — a triaged sit-rep of what needs your review
---

Pull the pending Freigent work queue with `list_pending_tasks` and give me a **triaged sit-rep**,
not a row dump:

1. One-line headline: total pending, broken down by type (rate negotiations, bookings, status
   updates, invoices, compliance).
2. **Lead with what needs a human decision** — anything that moves money, anything flagged
   high-gap/low-confidence, anything with a near deadline. Name the dollar figure or gap % per item.
3. List the routine/low-risk items briefly at the end — don't expand them.
4. End with: "What do you want to look at?" — do **not** fetch task details or approve anything yet.

Money items are never auto-approved. If I later say "approve everything," separate the money items
and make me approve those individually.
