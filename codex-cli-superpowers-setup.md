# Codex CLI + Superpowers

Install OpenAI's Codex CLI, then add the Superpowers methodology on top.

**Time:** 5 minutes.

---

## 1. Install Codex CLI

**Standalone installer (recommended)** — no Node.js required.

macOS / Linux:
```bash
curl -fsSL https://chatgpt.com/codex/install.sh | sh
```

Windows (PowerShell):
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://chatgpt.com/codex/install.ps1 | iex"
```

**npm, instead:**
```bash
npm install -g @openai/codex
```

**Homebrew (macOS), instead:**
```bash
brew install codex
```

### Verify

```bash
codex --version
```

---

## 2. Start it and sign in

```bash
cd your-project
codex
```

First run opens your browser. Choose **Sign in with ChatGPT** and follow
the prompt.

---

## 3. Try a first task

```
Summarize this repository and tell me how to run its tests.
```

Codex sandboxes execution by default and blocks network access unless you
allow it. Approval modes run from Read Only through Auto to Full Access —
start conservative until you trust the setup.

---

## 4. Install Superpowers

Superpowers ships via the official Codex plugin marketplace.

**In an interactive session:**
```
/plugins
```
Search:
```
superpowers
```
Select **Install Plugin**.

**In the Codex desktop app:** open **Plugins** in the sidebar, find
**Superpowers** under Coding, click **+**, follow the prompts.

### Verify

Restart your Codex session. Skills trigger automatically based on what you
ask for — you don't invoke them by hand.

---

## 5. What you just installed

About a dozen skills that fire themselves, in this order, as a project moves
forward:

1. **brainstorming** — refines a rough idea through questions before any code is written
2. **using-git-worktrees** — isolated workspace on a new branch, clean test baseline
3. **writing-plans** — breaks work into small tasks with exact file paths
4. **subagent-driven-development** / **executing-plans** — fresh subagent per task with review, or batch execution with checkpoints
5. **test-driven-development** — failing test first, then minimal code, then pass
6. **requesting-code-review** — issues reported by severity; critical ones block progress
7. **finishing-a-development-branch** — merge / PR / keep / discard, then cleanup

You never invoke these by name — describe what you want to build and the
right skill activates on its own.

---

## 6. Troubleshooting

| Symptom | Fix |
|---|---|
| `codex: command not found` after npm install | Global npm bin not on `PATH`; don't use `sudo npm install -g` |
| Browser auth loops, never completes | `codex logout`, or delete `~/.codex/auth.json`, then retry |
| `sandbox-exec ENOENT` (macOS) | Run `xcode-select --install` |
| Landlock/seccomp unsupported (WSL) | Update WSL2 to the latest version |
| Network denied inside a sandboxed command | Expected default — enable explicitly if needed |
| Skills never seem to trigger | Restart Codex; search `/plugins` to confirm it's installed |
