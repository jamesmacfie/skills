# skills

My [Claude Code](https://claude.com/claude-code) skills. Each folder under `skills/` is one skill with a `SKILL.md` and any supporting files.

| Skill | What it does |
| --- | --- |
| [readable](./skills/readable) | Writes anything a human reads (replies, PR descriptions, commit messages, docs, error strings) to the [Google developer documentation style guide](https://developers.google.com/style), and strips the patterns that make text read as AI-generated. |
| [planner](./skills/planner) | Turns a known goal into a concrete implementation plan for an existing codebase. Reads the code first, then asks in rounds until nothing is assumed, and makes every decision cite the pattern it follows. Invoke it with `/planner`, inside plan mode. |

## Install as a plugin

In Claude Code:

```
/plugin marketplace add jamesmacfie/skills
/plugin install jamesmacfie-skills@jamesmacfie
```

## Install by hand

Clone the repo and symlink the skills you want:

```sh
git clone git@github.com:jamesmacfie/skills.git
cd skills
for skill in skills/*/; do
  ln -s "$PWD/$skill" ~/.claude/skills/"$(basename "$skill")"
done
```

Or symlink one by hand:

```sh
ln -s "$PWD/skills/readable" ~/.claude/skills/readable
```

Restart Claude Code to pick them up.

## Licence

MIT. See [LICENSE](./LICENSE).
