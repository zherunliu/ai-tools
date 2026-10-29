# ricoxy

Launch Claude Code with DeepSeek Flash or Pro through DeepSeek's Anthropic-compatible API. No local proxy service is required.

## Usage

Install Claude Code and set `DEEPSEEK_API_KEY` in your environment:

```sh
export DEEPSEEK_API_KEY="your DeepSeek API key"
./ricoxy          # Flash (default)
./ricoxy pro      # Pro
```

Additional arguments are passed to Claude Code:

```sh
./ricoxy flash --continue
./ricoxy pro -p "Explain this project"
```

| In-session command | Actual model |
| --- | --- |
| `/model sonnet` or `/model haiku` | `deepseek-flash` |
| `/model opus` | `deepseek-v4-pro` |

The `/model` menu shows **DeepSeek Flash** (text and images) and **DeepSeek Pro** (text only), plus Claude Code's built-in **Default** entry. Pro does not accept images; use Flash for screenshots. When switching to Pro, start a text-only conversation if the existing history contains images.

The launcher passes session settings through `--settings` to override stale model mappings in user or project settings. The custom menu requires Claude Code 2.1.242 or later. Credentials stay in the environment and are not included in command-line arguments. The launcher does not modify global Claude settings. Claude Code itself may save a model selected with `/model`; the next launch through this script uses the model specified by the script.

## Model limits

Both Flash and Pro use the following settings, including after switching between them with `/model`:

| Setting | Value |
| --- | --- |
| Thinking effort | `max` |
| Context window | 1,048,576 tokens |
| Auto-compact window | 1,048,576 tokens, before output reservation and client buffers |
| Maximum output per request | 128,000 tokens |

DeepSeek supports up to 393,216 output tokens, but Claude Code caps unrecognized model IDs at 128,000. Setting a larger output value does not raise that client cap. Input and generated tokens share the context window; increasing the output budget reduces the space available for conversation history. These are limits, not guaranteed response lengths.

The launcher declares thinking and effort capabilities for both model IDs and sets `CLAUDE_CODE_EFFORT_LEVEL=max`. It uses `CLAUDE_CODE_DISABLE_THINKING=1` to omit Claude-specific `thinking` parameters, not to turn off DeepSeek reasoning: DeepSeek enables thinking by default and receives `output_config.effort=max`. DeepSeek ignores `thinking.budget_tokens`, so the launcher clears `MAX_THINKING_TOKENS`. Managed settings and additional command-line overrides may still affect Claude Code.

References: [DeepSeek model limits](https://api-docs.deepseek.com/api/list-models/), [DeepSeek thinking mode](https://api-docs.deepseek.com/guides/thinking_mode/), [DeepSeek Anthropic API](https://api-docs.deepseek.com/guides/anthropic_api/), [Claude Code model configuration](https://code.claude.com/docs/en/model-config), and [Claude Code environment variables](https://code.claude.com/docs/en/env-vars).
