# Claude Code via OpenRouter — Workshop Setup

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

## 2. Configure Claude Code for OpenRouter

Paste:

```bash
export ANTHROPIC_BASE_URL="https://openrouter.ai/api"
export ANTHROPIC_AUTH_TOKEN="$OPENROUTER_API_KEY"
export ANTHROPIC_API_KEY=""

export ANTHROPIC_DEFAULT_SONNET_MODEL="~anthropic/claude-sonnet-latest"
export ANTHROPIC_DEFAULT_OPUS_MODEL="~anthropic/claude-opus-latest"
export ANTHROPIC_DEFAULT_HAIKU_MODEL="~anthropic/claude-haiku-latest"
```

## 3. Start Claude Code

```bash
claude
```

If this machine was previously logged into Claude Code with an Anthropic account, inside Claude Code run:

```text
/logout
```

Then exit and start again:

```bash
claude
```

## 4. Verify

Inside Claude Code:

```text
/status
```

You should see that Claude Code is using:

```text
ANTHROPIC_AUTH_TOKEN
https://openrouter.ai/api
```

## 5. Quick test

Ask Claude Code:

```text
Create a file called hello.py that prints "Hello from OpenRouter"
```

## 6. When finished

Exit Claude Code, then remove the temporary credentials from this Terminal session:

```bash
unset OPENROUTER_API_KEY
unset ANTHROPIC_AUTH_TOKEN
unset ANTHROPIC_API_KEY
unset ANTHROPIC_BASE_URL
```

Closing the Terminal window also removes these temporary environment variables.

## Important

- Never share your key.
- Never paste it into GitHub, Slack, Discord, or a public chat.
- Never commit it to a repository.
- Your workshop key has its own spending limit and expiry.
