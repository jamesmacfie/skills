---
name: open-pr
description: "Clean up the code you just wrote, then commit, push, and open a pull request a reviewer can actually use. Runs a cleanup pass over the diff, rewrites the comments so they say why and sound like a person, writes a description pitched at someone who can read code but wasn't in the room, and opens the PR. Use when the work is done and it's time to ship it."
disable-model-invocation: true
argument-hint: "[what the reviewer already knows]"
---

# Open PR

A pull request is two deliverables. The code, and the explanation of it. Most of the effort goes
into the first and the second gets written in thirty seconds, which is backwards, because the
reviewer's time costs more than yours.

Two sources. The cleanup angles in step 2 come from Claude Code's `simplify`

Anything you pass as an argument is futher detail about this PR that you need to take into account. Like. `/open-pr Sam wrote this
module` means skip the background on that module, or `/open-pr Make sure you explain the rational
behind this API change` means making sure that that particular API change is descibed clearly and
in understandable terms. 

## Before you start

Read the diff. `git diff` against the base branch for what's committed, and `git diff HEAD` for what
isn't. Everything below works from that diff.

Stop and say so if `gh auth status` fails, or if the branch already has an open PR. Being on `main`
isn't a stop; you branch in step 6.

If the branch does two unrelated things, say so in one line and carry on. Splitting it is the user's
call, not yours.

## 1. Clean the code

Four angles. Work through all four, then fix what you found.

**Reuse.** New code that reimplements something the repo already has. Grep the shared and utility
modules, and the files next to the change. Name the existing helper to call instead.

**Simplification.** Complexity the diff adds: redundant or derivable state, copy-paste with slight
variation, deep nesting, dead code left behind. Name the simpler form that does the same job.

**Efficiency.** Wasted work the diff introduces: repeated I/O, independent operations run one after
the other, work added to startup or a hot path.

**Altitude.** Does the change fix the cause at the right depth, or patch a symptom? Special cases
layered onto shared plumbing are the tell that it's too shallow. Prefer the more general change to
the underlying mechanism.

Apply the clear wins. Skip anything that would change intended behaviour, needs changes well outside
the diff, or that you judge a false positive. Name what you skipped rather than arguing with it.

This is not a bug hunt.

## 2. Fix the comments

Load `readable`, then go through every comment the diff adds or touches:

- Delete it if it restates the line below it.
- Keep it if it says why, and cut it to one or two lines.
- Rewrite anything that reads as machine or AI slop written.

A comment earns its place by holding something the code can't: the reason, the constraint, the context
behind the change.

## 3. Show your work

Show the user the diff of what steps 1 and 2 changed, with one line per change saying why. Then keep
going. Don't wait for an answer.

## 4. Commit

Match the format of the last twenty commits in this repo. Load `readable` for the message. Add
whatever attribution lines the harness asks for.

## 5. Write the description

**Assume the reviewer can read code.** They know the language, the framework, and this codebase.
Don't explain what the function you touched does, don't define the framework's own terms, and don't
walk them through a diff they're about to read.

**Don't assume they know why.** They weren't in the conversation. They haven't read the ticket. They
can't see what you tried first, what you ruled out, or which of the three plausible fixes this is.

Put together: cut every sentence a reviewer could learn by reading the diff. Spend the words on the
reasoning they can't get anywhere else. What's left is the description.

Structure, unless `.github/PULL_REQUEST_TEMPLATE.md` exists, in which case use that:

- What changed and why, in the first two sentences.
- One short entry per fix: what was wrong, what it does now.
- Anything you decided against that a reviewer would otherwise ask about.

Title under 70 characters, specific. "Fix bugs" is usless and informs nothing.

Don't write: a bullet per file touched, a test plan with checkboxes nobody will tick, "comprehensive",
"robust", "seamless", or any claim you can't point at a line to back.

## 6. Push and open it

Branch first if you're on `main`. Push with `-u`. Create the PR with `gh pr create`, passing the body
inline through a heredoc so the formatting survives. Return the URL.

## 7. Inline comments, only if needed

Some things help this reviewer and shouldn't live in the code forever: why you went this way instead
of the obvious way, a line that looks wrong but isn't, a trade-off you made deliberately. Those go on
the diff, not in the source.

Post them with `gh api repos/{owner}/{repo}/pulls/{number}/comments`. Same style as everything else:
short, plain, one point each. Human readable and helpful into the future, not just now.

Keep it to a handful. If most of the diff needs a comment to be understood, go back to step 1.
