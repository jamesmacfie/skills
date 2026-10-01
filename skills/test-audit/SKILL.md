---
name: test-audit
description: "Check new tests against a value bar before they land, or audit existing tests for ones that restate the source, duplicate stronger proof, test implementation instead of behavior, or keep test-only production code alive. Three modes: gate the tests in the current change, audit a path, or run a campaign that prunes one whole area's test surface. Use when you want to know which tests earn their keep."
disable-model-invocation: true
---

# Test audit

Three modes share one value bar:

- **Gate.** Check every new or changed test in the current change before it lands.
- **Audit.** Sweep a path for tests that re-assert the source, duplicate stronger proof, couple
  behavior to implementation, or keep test-only production code alive.
- **Campaign.** Prune one area's whole test surface in a single change. Read
  [CAMPAIGN.md](CAMPAIGN.md) before you start one.

Pick the mode from the arguments. No arguments means gate mode on the tests in the working tree
and the current branch's diff. A path means audit mode on that path. `campaign` followed by an
area means campaign mode. If the arguments don't make the mode clear, ask.

Optimize for confidence, not deletion count. A broad audit lands as a series of small, coherent
changes, not one large one.

Two terms used throughout:

- The _owner_ is the production code responsible for a behavior, reached through its real entry
  point. Each behavior has one primary test at its owner.
- A _seam_ is an export, flag, wrapper, global, or injection hook that exists only so a test can
  reach inside. No production caller needs it.

## Gate

Answer four questions before you add a test. If you can't answer one, don't add the test yet.

1. What observable behavior, invariant, or independent contract does it protect?
2. What realistic regression makes it fail?
3. Why doesn't existing coverage already catch that failure? A second test at another layer needs
   its own distinct risk, such as a transport or lifecycle failure the owner's test can't reach.
   Prefer adding a row to a table-driven test or reusing a shared fixture over writing a
   near-duplicate. Consolidate duplicated setup in the same change.
4. Does it need a seam? If it does, move the test to the owner instead.

Then check the test against every pattern in [Junk patterns](#junk-patterns). A match fails the
gate unless the [retention bar](#retention-bar) names a contract the test guards on its own.

If a test would break under a refactor that keeps behavior the same, it tests implementation.
Rewrite it at the owner before it lands.

A bug regression test must fail on the code before the fix, for the reason you expect, and pass
after the fix at the owner. A regression test that never failed proves the mock works, not the
fix. One regression test at the owner covers the bug. Don't replay the same scenario at every layer
it passes through.

## Junk patterns

The gate rejects a new test that matches one of these. Audits hunt for existing tests that do.

- Tests with no assertions that exist only to raise coverage.
- A value compared with itself, or a copy compared with its original.
- Copied fixtures, inventories, manifests, or export lists that restate the source.
- Tests that search the source for an exact string, import, or identifier.
- Tests of a private helper or call shape that the owner's test already covers.
- The same contract exercised twice under different test names.
- Each caller re-testing a shared helper that has its own tests.
- Tests whose only job is keeping a seam alive.
- Dead production code that only tests call.
- Expected values computed by the function or renderer under test.
- Mocks that implement the behavior being asserted, or one mock standing in for several different
  APIs.
- Fixtures that hand the code a result it should produce itself, such as an acknowledgement, an
  ordering, or a callback. Persistence checked against a store the code never writes to.
- Tests that restate a declared flag or config value instead of exercising what the flag promises.
- Negative tests that pass for the wrong reason, such as a rejection from a different check, or a
  branch that production never reaches.
- Names or fixtures that promise more than the test checks. A test named "clears the session on
  logout" that only checks logout returned is one.

## Value bar

A test earns its maintenance cost when it protects behavior, a realistic regression, or a contract
that matters on its own. In an audit, an existing test that must change when the source is
reorganized without changing behavior is suspect. It isn't automatically deletable. The gate still
rejects new ones.

Before you judge a candidate, read all of the following:

- The project's `AGENTS.md` and `CLAUDE.md` files, at the root and in the test's directory.
- The complete test, and every test that overlaps it.
- The owner, its entry point, callers, callees, and sibling implementations.
- How CI selects and runs the test.
- The history of the test and the code it covers, from `git log` and `git blame`.

When the test claims behavior that comes from a dependency, read the dependency's source or types
directly.

## Discovery

Keep discovery read-only, and report evidence before you edit anything. For a broad scope, split
the work along the repo's own top-level areas, such as core packages, plugins, UI, and tooling.
Finish with one sweep across all of them for the junk patterns.

Outside campaign mode, prefer a few high-confidence candidates over a long speculative list.

## Retention bar

Keep a test when it guards one of these contracts on its own: a public API, a protocol or wire
format, config, a migration, a storage format, security, platform-specific behavior, a default,
exact output that another system depends on, packaging, a release, or an architecture rule. Also
keep:

- A test of call order, when the order is observable behavior.
- A regression test for a realistic failure.
- A source inspection test, when it's the cheapest independent guard. It must fail when the
  contract changes, such as a user-facing key, byte, or path, and survive a rename of internal
  identifiers.

If a test you're keeping fails before you've changed anything, treat it as a possible product bug.
Reproduce it and fix the owner instead of deleting the test.

Being static or slow isn't a reason to delete a test. A test that looks like it restates the
implementation might still be the only guard on a contract. Prove otherwise before you remove it.

## Candidate evidence

Record every item below before you edit. A candidate with a missing item isn't ready for deletion.

- The exact test name and location.
- What failure it can actually detect.
- The non-test callers of the code or seam it covers.
- The stronger test at the owner that remains, or why no test is needed.
- The relevant history, and why the test or seam exists.
- What production code or test support the deletion lets you remove.
- The risk, and the command that validates the change.

## Edit shape

Work on one owner at a time. Delete seams and dead production paths outright. Don't leave aliases
behind. Move regression tests you keep to the owner's test file. Collapse repeated package or
dependency assertions into one general test.

Aim for fewer lines of production code. Don't add a replacement test that restates the same
implementation. Don't turn an uncertain candidate into a deletion to raise the count.

## Validation

Don't edit source or tests while a test runner in watch mode is running in the same checkout.

1. Find the project's test, lint, format, and type-check commands. Look in `AGENTS.md`,
   `CLAUDE.md`, the package manifest's scripts, the `Makefile`, and the CI config.
2. Run the smallest set of tests that covers the owner and its siblings.
3. If you removed a test that searched source or asserted a plan, run the script or dry run that
   owns the real contract.
4. Format the changed files, then run `git diff --check`.
5. Run whatever checks CI runs on changed files.
6. Run `git diff --numstat`. Report production and tooling lines separately from test and test
   support lines.
7. Review the final diff. If a review skill such as `/code-review` is available, run it.

## Landing

Commit, push, or open a pull request only when the user asks. If the `open-pr` skill is
installed, use it. Land one coherent change at a time. After it merges, update from the main
branch and rerun read-only discovery for the next batch.

## Report

When you finish, report:

- The root cause, and the categories of low-value tests you removed.
- Simplifications to production code.
- Candidates you kept, and why they still matter.
- The validation you actually ran, and its result.
- Production lines and test lines changed, counted separately.
- Pull request and merge state.
- Named follow-ups.

## Credit

Adapted from the
[OpenClaw `test-audit` skill](https://github.com/openclaw/openclaw/tree/main/.agents/skills/test-audit).
Copyright (c) 2026 OpenClaw Foundation. Used under the MIT License.
