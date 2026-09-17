# Pi + OpenRouter + Superpowers

Install pi, connect it to OpenRouter, add Superpowers. That's it.

---

## 1. Install pi

Pick whichever you prefer — they all give you the same `pi` command.

**curl installer** (Linux/macOS, no Node required):
```bash
curl -fsSL https://pi.dev/install.sh | sh
```

**npm** (all platforms, including Windows):
```bash
npm install -g --ignore-scripts @earendil-works/pi-coding-agent
```

**pnpm:**
```bash
pnpm add -g @earendil-works/pi-coding-agent
```

**Yarn:**
```bash
yarn global add @earendil-works/pi-coding-agent
```

**Bun:**
```bash
bun add -g @earendil-works/pi-coding-agent
```

Verify:
```bash
pi --version
```

---

## 2. Get an OpenRouter API key

1. Go to **[openrouter.ai](https://openrouter.ai)** and sign up (email or GitHub — no card needed).
2. Once logged in, go to **[openrouter.ai/keys](https://openrouter.ai/keys)**.
3. Click **Create Key**, give it a name, and copy the key it shows you (starts with `sk-or-v1-`). You only see it once.

You don't actually need to do this manually — step 3 below does it for you automatically. It's useful to know this page exists in case you ever want to view, rename, or revoke the key later.

---

## 3. Connect pi to OpenRouter

Start pi inside a project folder:
```bash
cd my-project
pi
```

Inside pi, run:
```
/login openrouter
```

Select **Sign in with OpenRouter**. This opens your browser, you log in (or you're already logged in from step 2), and pi automatically gets an API key from your account — no copying or pasting.

> **On a remote/SSH machine:** the browser can't reach pi directly. Complete the sign-in on a device that does have a browser, then paste the redirect URL back into the pi prompt when asked.

**Prefer to paste the key yourself instead?** That works too:
```bash
export OPENROUTER_API_KEY=sk-or-v1-...
pi
```

---

## 4. Pick a model

```
/model
```

Choose any model from the list, then press `Ctrl+S` to save it as your default so you don't have to pick again next time.

---

## 5. Smoke test

Type a simple request:
```
Summarize this repository and tell me how to run its checks.
```

If pi reads files and runs commands, you're connected and working.

---

## 6. Install Superpowers

```
pi install git:github.com/obra/superpowers
```

Restart pi. Verify it loaded:
```
/skill:brainstorming
```

If that command exists, Superpowers is active. You don't invoke skills by hand — just describe what you want to build, and the right skill triggers itself.

---

## What Superpowers gives you

A full development workflow that runs on its own:

**brainstorming** → **writing-plans** → **test-driven-development** → **code review** → **finishing-a-development-branch**

Plus: `systematic-debugging`, `using-git-worktrees`, `subagent-driven-development`, and a few others — about 15 skills total, all triggered automatically from context.

---

## Quick troubleshooting

| Problem | Fix |
|---|---|
| `pi: command not found` | Open a new terminal, or check `npm bin -g` is on your `PATH` |
| `/login openrouter` browser doesn't open (SSH) | Paste the redirect URL into the prompt manually |
| No models show up | Re-run `/login openrouter`, or check `OPENROUTER_API_KEY` is set |
| `/skill:brainstorming` doesn't exist | Restart pi — the install needs a fresh session to load |
