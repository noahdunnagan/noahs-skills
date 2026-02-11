# noahs-skills

Slash commands for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Commands

| Command | Description |
|---------|-------------|
| `/push` | Generate a conventional commit message from your diffs, stage, and commit. |
| `/session` | Summarize what you worked on into a `SESSION.md` log. |

## Install

Copy the commands you want into your `~/.claude/commands/` directory (global) or your project's `.claude/commands/` directory (per-project).

```bash
# Global install (available in all projects)
cp commands/*.md ~/.claude/commands/

# Per-project install
cp commands/*.md .claude/commands/
```

Or clone and symlink:

```bash
git clone https://github.com/noahdunnagan/noahs-skills.git
ln -s "$(pwd)/noahs-skills/commands/push.md" ~/.claude/commands/push.md
ln -s "$(pwd)/noahs-skills/commands/session.md" ~/.claude/commands/session.md
```

## License

MIT
