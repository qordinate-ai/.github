# Qordinate

Qordinate builds infrastructure for agent software.

Our current focus is **Watchline**, an event layer for agents. Watchline allows agents to register future watches, receive only relevant events, and act with context instead of polling everything on a schedule.

## Watchline

Most agents today are still reactive. They respond when a user asks or wake up on a schedule and scan too much context.

That works for demos, but it falls short when agents need to monitor multiple tools, users, and changing workflows.

Watchline gives agents a simpler solution:

> "Tell me when this specific thing happens, then wake the right agent with the right event."

Examples include:

- A customer replies to a thread that requires follow-up.
- A meeting changes, prompting a related task to update.
- A GitHub issue matches a saved condition.
- A claim, ticket, invoice, or approval changes status.
- A high-priority event appears across email, calendar, Slack, CRM, support tools, or internal systems.

Instead of having each agent create its own polling loop, deduplication logic, trigger filters, and wakeup protocols, Watchline offers a shared event and filter layer.

## Why This Matters

Agents are evolving into workflow owners, not just chat interfaces.

This shift means they need to know the right time to act.

Basic approaches can get messy:

- Poll everything repeatedly.
- Push every webhook into the agent and let it sort through the noise.
- Hard-code one-off cron jobs.
- Build fragile per-integration trigger logic in every product.
- Wake costly downstream agents for irrelevant events.

Watchline is built around a more focused idea:

> Agents should only wake when a user-defined future event actually occurs.

This design makes agent systems more affordable, quieter, easier to audit, and more trustworthy.

## Projects

### Watchline

Website: https://watch.qordinate.ai/

Watchline serves as the event layer for agents.

It supports future watches, filtered event delivery, and agent wakeups.

### OpenClaw Plugin

NPM: https://www.npmjs.com/package/@watchline/openclaw-plugin  
GitHub: https://github.com/qordinate-ai/watchline-openclaw-plugin

The OpenClaw plugin allows OpenClaw agents to create and manage watches.

Core tools include:

- `start_watch`
- `continue_watch`
- `list_watches`
- `pause_watch`
- `resume_watch`
- `delete_watch`

The plugin polls a Watchline channel and injects matched events back into OpenClaw sessions.

### WatchBench

GitHub: https://github.com/qordinate-ai/watchbench  
Dataset: https://huggingface.co/datasets/watchline/watchbench-email-v0

WatchBench is a benchmark for event routing in agent systems.

The first dataset, `watchbench-email-v0`, tests whether an agent/event layer can correctly decide which email events should trigger user-defined watches.

Current dataset details:

- 500 synthetic email events
- 20 resolved watch intents
- 10,000 binary watch-event labels
- 412 positive pairs

The initial report compares Watchline-style event routing with polling-style downstream agent evaluation.

## What We Are Exploring

We are particularly interested in agent products where customers connect various tools and expect the agent to respond when external conditions change.

Key areas include:

- AI assistants for business workflows
- Customer support and revenue operations agents
- Healthcare administration and care coordination agents
- Finance and accounting workflow agents
- Recruiting and HR agents
- Legal and compliance workflow agents
- Security and IT operations agents
- Agents integrated into email, calendar, CRM, ticketing, or internal tools

The common theme is not "this product has webhooks."

The stronger theme is:

> Customers use an agent-based product, connect their own tools, and need the agent to activate at the right time across multiple external event sources.

## Design Principles

### Watches, Not Ambient Surveillance

A watch should have a defined scope, a clear owner, and a specific reason for waking an agent.

### Events Before Agents

The event layer should filter and route before expensive operations occur downstream.

### Human-Reviewable Automation

Agent actions should maintain provenance, wake reason, source context, and audit trails.

### Integrations Without One-Off Trigger Sprawl

Agent products should not have to recreate the same cross-application watch, filter, and wakeup systems repeatedly.

### Quiet by Default

The system should prefer missing noise rather than waking agents for trivial events. Precision is essential.

## Background

Qordinate began as a personal assistant across WhatsApp, Telegram, iMessage, Slack, and mobile apps.

Users often wanted scheduled tasks, reminders, delegation, and proactive follow-up. This revealed a recurring product issue: effective agents need timing and event awareness, not just chat capabilities.

Watchline is the infrastructure version of that lesson.

## Repositories

Some active public repositories include:

- `watchline-openclaw-plugin` — OpenClaw plugin for Watchline watches
- `watchbench` — benchmark and dataset tools for agent event routing

More public infrastructure and examples are coming.

## Contact

Website: https://watch.qordinate.ai/
Email: founders@qordinate.ai

If you are building an agentic product where users connect tools and expect the agent to act when things change, we would like to talk.
