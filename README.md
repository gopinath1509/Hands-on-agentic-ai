 # Hands-on Agentic AI

This repository contains the setup guides for the **Hands-on Agentic AI** workshop.

The goal is simple: get one agentic coding environment working on your laptop before the hands-on exercises begin.

## Choose your setup

There are **three main setup options** for the workshop:

### Option 1 — Claude Code

If you already have access to Claude Code, follow:

[claude-code-superpowers-setup.md](./claude-code-superpowers-setup.md)

Use this guide to install/configure Claude Code and the workshop "superpowers" setup.

---

### Option 2 — Codex CLI

If you already have access to Codex CLI, follow:

[codex-cli-superpowers-setup.md](./codex-cli-superpowers-setup.md)

Use this guide to install/configure Codex CLI and the workshop "superpowers" setup.

---

### Option 3 — Pi + OpenRouter

If you want to use the lightweight Pi/OpenRouter route, follow:

[pi-openrouter-superpowers-simple.md](./pi-openrouter-superpowers-simple.md)

This is the third supported setup option for the workshop.

---

# No paid Claude or Codex API access?

That is fine.

If you **do not have paid API access for Claude or Codex**, we can provide you with a temporary **OpenRouter API key** for the workshop.

You can then use that OpenRouter key with either **Claude Code** or **Codex CLI**.

> Ask the workshop organizers for your personal OpenRouter key.  
> Each participant gets their own key. Do not share it with anyone else.

## Use Claude Code with an OpenRouter key

Follow:

[openrouter-claude-code-workshop.md](./openrouter-claude-code-workshop.md)

This guide shows you how to run Claude Code through OpenRouter using the workshop-provided API key.

## Use Codex CLI with an OpenRouter key

Follow:

[openrouter-codex-workshop.md](./openrouter-codex-workshop.md)

This guide shows you how to run Codex CLI through OpenRouter using the workshop-provided API key.

---

# Which guide should I use?

| Your situation | Guide |
|---|---|
| I already use Claude Code | [Claude Code setup](./claude-code-superpowers-setup.md) |
| I already use Codex CLI | [Codex CLI setup](./codex-cli-superpowers-setup.md) |
| I want to use Pi + OpenRouter | [Pi + OpenRouter setup](./pi-openrouter-superpowers-simple.md) |
| I want Claude Code but do not have paid API access | [Claude Code via OpenRouter](./openrouter-claude-code-workshop.md) |
| I want Codex but do not have paid API access | [Codex CLI via OpenRouter](./openrouter-codex-workshop.md) |

## Recommended order

1. Pick **one** of the three main setup options.
2. Complete the corresponding setup guide.
3. If your Claude/Codex setup requires API access you do not have, ask us for an OpenRouter key.
4. Follow the matching OpenRouter guide.
5. Verify that your coding agent can successfully answer a simple prompt before the workshop exercises begin.

---

# OpenRouter workshop keys

If you receive an OpenRouter key from us:

- use **only your own key**;
- do not post it in Slack, Discord, GitHub, screenshots, or public chats;
- do not commit it to a repository;
- do not add it to example code or documentation;
- use it only for the workshop;
- the key may have a spending limit and an automatic expiration time.

The OpenRouter guides in this repository show how to load the key temporarily in your Terminal without saving it permanently.

---

# Repository files


Hands-on-agentic-ai/
├── README.md
├── claude-code-superpowers-setup.md
├── codex-cli-superpowers-setup.md
├── pi-openrouter-superpowers-simple.md
├── openrouter-claude-code-workshop.md
└── openrouter-codex-workshop.md
