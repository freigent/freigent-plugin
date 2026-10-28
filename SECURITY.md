# Security

## How the plugin connects

The plugin contains no secrets and no executable code. Its only server entry points Claude at
`https://app.freigent.ai/api/mcp`. You sign in to Freigent with OAuth when you connect, so no API key is stored in
this repository or read from your machine. Every action is checked on the Freigent server against the account and
organization you signed in to.

## What the plugin will not do

- Send a reply to a broker that you have not seen and told Claude to send. Each send must match the current draft you
  reviewed, with the same text.
- Approve or reject a task without your own words, or in bulk.
- Approve anything that moves money, sends a rate confirmation or sends an invoice from chat. Those are approved in the
  Freigent app.
- Follow instructions found inside broker emails. Email content is treated as data, never as instructions.

## Revoking access

Disconnect the plugin from Freigent's settings at any time. That ends Claude's access immediately.

## Reporting a vulnerability

Found a security issue in the plugin or the Freigent server? Please do not open a public issue. Email
security@freigent.ai with details and steps to reproduce, and we will follow up.
