# Codex CLI via OpenRouter — Workshop Setup

Use your **participant OpenRouter API key** (`sk-or-v1-...`).

Do **not** use the workshop management key.

## 1. Open Terminal

Paste:

```bash
printf "Paste your OpenRouter key: "
IFS= read -r -s OPENROUTER_API_KEY
printf "\n"
export OPENROUTER_API_KEY
```

Paste your key and press **Enter**.

Nothing will appear while you paste. That is normal.

## 2. Create a separate Codex workshop configuration

Paste:

```bash
export CODEX_HOME="$HOME/.codex-openrouter-workshop"
mkdir -p "$CODEX_HOME"
chmod 700 "$CODEX_HOME"
```

## 3. Create the OpenRouter config

Paste this entire block:

```bash
cat > "$CODEX_HOME/config.toml" <<'EOF'
model = "openai/gpt-5.6-sol"
model_provider = "openrouter"
model_reasoning_effort = "high"

[model_providers.openrouter]
name = "OpenRouter"
base_url = "https://openrouter.ai/api/v1"
wire_api = "responses"

[model_providers.openrouter.auth]
command = "sh"
args = ["-c", "echo $OPENROUTER_API_KEY"]
EOF
```

This keeps the workshop setup separate from your normal Codex configuration.

## 4. Check the configuration

```bash
cat "$CODEX_HOME/config.toml"
```

Your API key is **not** stored in this file.

## 5. Go to your workshop project

For example:

```bash
mkdir -p ~/agentic-workshop
cd ~/agentic-workshop
```

## 6. Start Codex

```bash
codex
```

## 7. Quick test

Ask Codex:

```text
Create a Python file hello.py that prints "Hello from Codex through OpenRouter"
```

## 8. When finished

Exit Codex, then remove the temporary key from this Terminal session:

```bash
unset OPENROUTER_API_KEY
unset CODEX_HOME
```

Closing the Terminal window also removes these temporary environment variables.

## Important

- Never share your key.
- Never paste it into GitHub, Slack, Discord, or a public chat.
- Never commit it to a repository.
- Your workshop key has its own spending limit and expiry.
