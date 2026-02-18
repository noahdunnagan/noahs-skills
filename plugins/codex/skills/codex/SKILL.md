---
name: codex
description: Delegate research to Codex CLI. Use when user says "/codex", "ask codex", "delegate to codex", "have codex look into", or wants fast parallel research using OpenAI's Codex agent.
allowed-tools:
  - Bash
---

# Codex

Delegate read-only research tasks to OpenAI's Codex CLI using the fast codex-spark model.

## Behavior

```
input: research prompt (and optional model override)
output: Codex agent's findings, presented inline
```

- **research**: user prompt -> run `codex exec` in read-only sandbox -> return findings
- **parallel research**: multiple prompts -> launch concurrent `codex exec` calls -> aggregate results

## Execution

Run Codex in non-interactive mode with read-only sandbox:

```
codex exec \
  -m gpt-5.3-codex-spark \
  -c model_reasoning_effort=\"low\" \
  --ephemeral \
  -s read-only \
  -o /tmp/codex-<hash>.md \
  -C <working-dir> \
  "<prompt>"
```

Flags:
- `-m gpt-5.3-codex-spark` — default model. Override with `-m <model>` in user prompt.
- `-c model_reasoning_effort="low"` — minimal thinking for max speed
- `--ephemeral` — no session persistence
- `-s read-only` — no file mutations
- `-o <file>` — capture final response for clean extraction
- `-C` — set working directory (defaults to current project root)

Parse the user's input:
- Everything after `/codex` is the prompt
- If the prompt contains `-m <model>`, extract it and pass to `-m` flag
- If the prompt is empty, ask what to research

After execution, read the output file and present the findings directly. Delete the temp file.

## Examples

### Single research task

User: `/codex how does the router package handle TLS termination?`

Execution:
```bash
codex exec -m gpt-5.3-codex-spark -c model_reasoning_effort="low" \
  --ephemeral -s read-only -o /tmp/codex-abc123.md \
  "how does the router package handle TLS termination?"
```

Present the contents of the output file as the response.

### Model override

User: `/codex -m gpt-5.3-codex how does deployment rollback work?`

Extract `-m gpt-5.3-codex` from the prompt. Run with that model instead of spark.

### Parallel research

When the user provides multiple distinct questions, or when the research naturally decomposes into independent sub-questions, run multiple `codex exec` calls concurrently using parallel Bash tool calls.

## Error Handling

```
case:
  empty prompt          -> ask user what to research
  codex not installed   -> tell user to install: npm i -g @openai/codex
  auth failure          -> tell user to run: codex login
  timeout (>120s)       -> kill process, report partial output if any
  model not available   -> fall back to default codex model, inform user
```
