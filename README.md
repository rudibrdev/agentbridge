# AgentBridge — Human approval for AI agents

AgentBridge is a small browser extension that adds a human approval step between AI agents and your browser. It lets an agent read the active tab, read and write the clipboard, and inject text into a page — but **every action pauses until you approve it**. Nothing happens without your explicit OK, and everything the agent did is logged.

- Website: https://rudibrdev.github.io/agentbridge/
- Chrome Web Store: https://chromewebstore.google.com/
- Privacy policy: https://rudibrdev.github.io/agentbridge/privacy.html
- Built by: [YardWork](https://yardwork.dev)

## Why it exists

AI agents are useful, but letting one operate your browser unattended is a bad idea. Agents can click things, paste text, fill forms, or copy sensitive data — often faster than you can react. AgentBridge is a simple check in the loop: the agent requests an action, you see exactly what it wants to do, and you decide. Approve it, or stop it.

## What it does

- **Approval prompts** — a clear dialog appears before every agent action, showing exactly what the agent wants to do.
- **Activity log** — a full history of every action the agent requested and what you decided.
- **Clipboard control** — the agent can read and write the clipboard, but only with your permission each time.
- **Page interaction** — the agent can inject text into a page (form filling, autocomplete) only after you approve.

## How it works

1. An AI agent (any agent that speaks WebSocket) connects to the bridge on your machine.
2. The agent requests an action — e.g. "read the current tab", "copy this to clipboard", "type this into the form".
3. AgentBridge shows you an approval prompt with the details of the request.
4. You approve or deny. Only approved actions execute.
5. Every request and decision is written to the activity log.

## Local only

The bridge listens on `127.0.0.1` — your machine only. No cloud, no accounts, no telemetry. There is nothing to sign up for and nothing leaves your computer.

## Permissions

AgentBridge is a small extension with focused permissions:

- **Read the active tab** — so the agent can see the page you are looking at.
- **Clipboard read & write** — for copy/paste workflows.
- **Scripting** — to inject text into pages you approve.

No broad "read all websites" permission, no data collection, no third-party servers.

## Getting started

1. Install AgentBridge from the [Chrome Web Store](https://chromewebstore.google.com/).
2. Start the bridge (a small local process) on your machine.
3. Point your agent at `ws://127.0.0.1:<port>`.
4. Approve the first prompt and you're running.

## FAQ

**Does AgentBridge work with any agent?**
Yes. Any agent that can speak WebSocket can use it. There is no vendor lock-in and no proprietary protocol.

**Does my data leave my machine?**
No. The bridge runs locally on `127.0.0.1`. There is no cloud component and no telemetry. See the [privacy policy](privacy.html).

**Is it really free?**
Yes — free, with no accounts and no paid tiers.

**Can I deny an action the agent already asked for?**
Yes. Every request waits for your decision. Deny it and the action never runs.

## About

AgentBridge is a free, open project by the people at [YardWork](https://yardwork.dev) — practical tools for working with AI agents.

## Privacy

See the [privacy policy](https://rudibrdev.github.io/agentbridge/privacy.html).
