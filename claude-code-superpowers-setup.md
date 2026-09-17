# Claude Code + Superpowers

Install Claude Code, then add the Superpowers methodology on top.

**Time:** 5 minutes.

---

## 1. Install Claude Code

**Native installer (recommended)** — no Node.js required, updates itself
automatically.

macOS / Linux / WSL:
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Windows (PowerShell):
```powershell
irm https://claude.ai/install.ps1 | iex
```

**npm, instead**, if you prefer it or already manage tools through Node:
```bash
npm install -g @anthropic-ai/claude-code
```
Requires Node.js 22+ (older Node prints a warning but the install still
completes — the binary doesn't use Node at runtime). Do **not** run this
with `sudo`.

### Verify

```bash
claude --version
claude doctor
```

---

## 2. Start it and sign in

```bash
cd your-project
claude
```

First run opens your browser to sign in. Follow the prompt.

---

## 3. Install Superpowers

Two marketplaces carry the same plugin. Pick one.

**Option A — official marketplace**
```
/plugin install superpowers@claude-plugins-official
```

**Option B — Superpowers' own marketplace**
```
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```

### Verify

```
/plugin list
```

`superpowers` should appear as installed and active.

That's it. Skills trigger automatically from what you ask Claude to do — you
don't invoke them by name.

---

## 4. What you just installed

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

## 5. Updating

```
/plugin install superpowers@superpowers-marketplace
```

Re-running the install command updates it. Claude Code itself updates
automatically if you used the native installer.

---

## 6. Troubleshooting

| Symptom | Fix |
|---|---|
| `claude: command not found` | Open a new terminal window; check `PATH` for the install location |
| `EACCES` during npm install | Don't use `sudo` — fix your npm prefix instead |
| Plugin install fails with a schema error | Update Claude Code and retry, or try the other marketplace |
| Skills never seem to trigger | Run `/plugin list` to confirm `superpowers` is active |
| Browser login loop | Re-run `claude`, or paste the printed URL manually |
