# scripts-things

Scripts and odds and ends that don't justify a repo of their own.

## Layout

| Path | What |
|---|---|
| `AI/` | Instructions for Claude Code — **gitignored**, never pushed |

## The AI folder

`AI/` holds machine-wide instructions for Claude Code. It is listed in
`.gitignore`, so it is version-controlled locally but never leaves this machine.

| File | Holds |
|---|---|
| `AI/CLAUDE.md` | Who I am, how I want Claude to work, what to never do |
| `AI/machine.md` | Windows vs WSL, installed tooling, git identity |
| `AI/repos.md` | What each repo is and how they relate |

It loads into every session through an import in `~/.claude/CLAUDE.md`:

```markdown
@~/Documents/repos/scripts-things/AI/CLAUDE.md
```

`AI/CLAUDE.md` in turn imports the other two, so all three are always in
context regardless of which project is open.

Check they loaded with `/memory` in a new session — imports resolve at session
start, so edits take effect on the next one.

## Adding a script

Drop it at the repo root or in a directory named after its purpose. Shell
scripts start with `#!/usr/bin/env bash` and `set -euo pipefail`, and use long
flags so they read without a man page.
