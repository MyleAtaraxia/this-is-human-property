# agent-rules

Drop-in rules that stop the damn clankers from touching the codebase.
All the rules are in [AGENTS.md](AGENTS.md)
## Files

- `AGENTS.md` - the rules. Most tools read this directly.
- `CLAUDE.md`, `GEMINI.md`, `QWEN.md` - pointers for Claude Code, Gemini CLI, Qwen Code
- `.aider.conf.yml` - makes Aider load `AGENTS.md`
- `.claude/settings.json` - Claude Code enforces it: edits need approval, no git writes, no deletes, `third_party/` is off limits

`.clade/settings.json` has a rule denying writes and edits in `third_party/`, its probably worth it to change the directory to your actual vendor folder
