# Freigent plugin for Claude

Freigent negotiates truckload freight by email, for carriers, dispatchers and freight brokers. This plugin connects
Claude to your Freigent account and adds three skills that teach Claude how to work load offers and your approval
queue with you.

## What it does

- **See which brokers replied.** Claude lists the load offers brokers emailed to the inbox you connected to Freigent,
  with the lane, equipment, rate and rate per mile.
- **Get the counter from your own numbers.** For one offer, Freigent works out your counter and walk-away number from
  the minimum rate you set (and, for brokers, keeps your ceiling private). Paste any offer to get the same math without
  a connected inbox. Freigent never makes up a market rate.
- **Send the reply you approve.** Claude writes the reply, Freigent saves it as a draft and shows it to you, and only
  after you say to send it does Freigent email it to the broker in the same thread.
- **Work your approval queue.** Carriers who run their back office on Freigent can review what is waiting for their
  approval and approve or reject it, one item at a time, with their own words. Anything that moves money, sends a rate
  confirmation or sends an invoice is approved in the Freigent app, not from chat.
- **Follow up and record bookings.** Set a reminder when a broker goes quiet, and mark a load booked when it closes.

## What it sends, and where

Everything goes between Claude and one server: `https://app.freigent.ai/api/mcp`, run by Freigent. The plugin
contains no other code, scripts or hooks, and no credentials.

- **Sign-in:** you sign in to your Freigent account when you connect (OAuth). Claude never sees your password. You
  can disconnect at any time from Freigent's settings.
- **What Claude reads:** your load offers and their email threads, your rates on file and your pending Freigent tasks,
  only for the organization you signed in to.
- **What gets sent by email:** a reply to a broker, from your Freigent dispatch address (or, on a personal account, the
  mailbox you connected to Freigent), in the broker's existing thread. A reply is sent only from a draft you were shown
  and told Claude to send, with the same text. No separate email connector is required. On a free plan Freigent adds
  one small "Powered by Freigent" line below the reply.
- **What changes in Freigent:** drafts you review, follow-up reminders, booked loads you record, and the tasks you
  approve or reject. Approving or rejecting needs your own words; a phrase like "approve all" is refused.

Nothing is sent and nothing is approved until you say so.

## Install

Install it from the Claude directory, or in Claude Code:

```
/plugin marketplace add freigent/freigent-plugin
/plugin install freigent@freigent
```

Then sign in to Freigent when Claude asks. You need a Freigent account: https://freigent.ai

## Skills

- `get-started`: what Freigent can do and how to connect your inbox.
- `negotiate-load`: reading an offer, the counter, and drafting and sending the reply.
- `carrier-clear-my-queue`: working through tasks waiting for your approval.

## Privacy, terms and support

- Privacy policy: https://freigent.ai/privacy
- Terms: https://freigent.ai/terms
- Support: https://freigent.ai/contact or support@freigent.ai
- Security reports: see [SECURITY.md](SECURITY.md)
