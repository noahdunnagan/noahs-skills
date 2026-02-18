# noahs-skills

Skills and commands for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## What's included

| Plugin | Type | Description |
|--------|------|-------------|
| `blueprint` | Skill + Command | Three-mode planning — always-active disposition, `/blueprint` for generating requirements docs, and blueprint execution. |
| `workflow` | Commands | `/push` for conventional commits, `/session` for session logging. |
| `rust-guide` | Skill | Opinionated Rust style guide — makes AI-written Rust code look like a human wrote it. |
| `codex` | Skill | Delegate read-only research to OpenAI's Codex CLI using the fast codex-spark model. |

## Install

Add the marketplace and install what you want:

```
/plugin marketplace add noahdunnagan/noahs-skills
/plugin install blueprint@noahs-skills
/plugin install workflow@noahs-skills
/plugin install rust-guide@noahs-skills
/plugin install codex@noahs-skills
```

## License

MIT
