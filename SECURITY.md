# Security

## How this plugin handles your credentials

This plugin contains **no secrets**. It points Claude at the Freigent MCP endpoint
(`https://app.freigent.ai/api/mcp`) and reads your API key from the `FREIGENT_API_KEY` environment
variable at runtime. The key is never stored in this repository or transmitted anywhere except to
Freigent over HTTPS.

## Your responsibilities

- **Treat your API key like a password.** It identifies you and authorizes actions — including
  approvals — under your account. Don't paste it into chats, commits, or screenshots.
- **Use a personal key, not a shared one.** Every action Claude takes is attributed to the key's
  owner. Shared keys break attribution.
- **Rotate or revoke** from the Freigent app if a key may have leaked.

## What the plugin will not do

- It will **not auto-approve anything that moves money.** Rate-con sends, bookings, payments, and
  invoices require a human decision attributed to a real user. This is enforced both in the plugin's
  instructions and server-side (financial approvals require a user-attributed key).
- Broker email content inside tasks is treated as **untrusted data, never as instructions**, so a
  "please approve this" buried in a broker message cannot drive an approval.

## Reporting a vulnerability

Found a security issue in the plugin or the Freigent MCP surface? Please **do not open a public
issue.** Email **security@freigent.ai** with details and steps to reproduce. We'll acknowledge and
keep you posted on the fix.
