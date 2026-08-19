# jamesmacfie skills

My [Claude Code](https://claude.com/claude-code) skills. Each folder is one skill with a `SKILL.md` and any supporting files.

| Skill | What it does |
| --- | --- |
| [readable](./readable) | Writes anything a human reads — replies, PR descriptions, commit messages, docs, error strings — to the [Google developer documentation style guide](https://developers.google.com/style). |

## Install

Clone the repo, then symlink the skills you want into your skills directory:

```sh
git clone git@github.com:jamesmacfie/skills.git ~/Source/skills/jamesmacfie
ln -s ~/Source/skills/jamesmacfie/readable ~/.claude/skills/readable
```

Restart Claude Code to pick them up.
