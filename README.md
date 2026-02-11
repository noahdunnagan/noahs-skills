# noahs-skills

Slash commands and skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Commands

| Command | Description |
|---------|-------------|
| `/push` | Generate a conventional commit message from your diffs, stage, and commit. |
| `/session` | Summarize what you worked on into a `SESSION.md` log. |

## Skills

| Skill | Description |
|-------|-------------|
| `blueprint` | Structured planning workflow — discovery, requirements, solution design, self-critique, and sync before any code gets written. |

## Install

### Commands

Copy into `~/.claude/commands/` (global) or `.claude/commands/` (per-project).

```bash
cp commands/*.md ~/.claude/commands/
```

### Skills

Copy into `~/.claude/skills/` (global) or `.claude/skills/` (per-project).

```bash
cp -r skills/blueprint ~/.claude/skills/blueprint
```

### Or clone and symlink everything

```bash
git clone https://github.com/noahdunnagan/noahs-skills.git
ln -s "$(pwd)/noahs-skills/commands/push.md" ~/.claude/commands/push.md
ln -s "$(pwd)/noahs-skills/commands/session.md" ~/.claude/commands/session.md
ln -s "$(pwd)/noahs-skills/skills/blueprint" ~/.claude/skills/blueprint
```

## License

MIT
