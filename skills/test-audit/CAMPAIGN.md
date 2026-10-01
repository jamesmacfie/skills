# Test-pruning campaign

A campaign prunes one area's whole test surface in a single change. The area might be one plugin,
one package, or one core module. The value bar, retention bar, candidate evidence, and validation
in [SKILL.md](SKILL.md) apply throughout. This file adds the order of work and lessons from a full
campaign.

Each step ends on its completion criterion. Don't start the next step early.

Steps 3, 4, and 6 hand work to separate read-only agents. Asking for a campaign counts as asking
for those agents. If the harness can't run agents, do each lane yourself, one at a time.

## 1. Record a baseline

Pin a commit on the main branch. At that commit, record the area's test and test-support line
counts and whether each test file passes or fails. Keep the failures in their own list. In one
campaign, all three baseline failures turned out to be real product bugs, not stale tests.

Done when every test file in scope has a recorded result.

## 2. Split into lanes

Split the test surface into _lanes_ along the production code's own boundaries, not by file name.
A messaging integration might split into accounts, commands, inbound, outbound, persistence,
transport, shared helpers, test harness, and end-to-end scenarios. Include the area's cases in
shared core tests, and its end-to-end and manual test harnesses.

Done when every test file and scenario the area owns belongs to exactly one lane.

## 3. Write a ledger for each lane

Give each lane to its own read-only agent. The agent reads every test in the lane in full,
including parameter tables. It also reads the owners, their entry points, callers, history, and
how CI runs them.

Each test goes into a written _ledger_ with one mark. A table-driven test, such as `it.each` or
`@pytest.mark.parametrize`, counts as one test unless its rows need different marks. Then mark each
row.

- `R`: retain. Name the contract and the bug it catches. A test that only moves to a better file
  stays `R`, with the move noted.
- `F`: retain the contract but fix the assertion. An example is a negative test that passes when
  only one of several items is missing.
- `C`: consolidate. Name what absorbs the assertion: a row in a sibling table, a stronger suite at
  the owner, or a shared test in another package.
- `D`: delete. Name the test that still covers the behavior, or explain why no contract exists.

Judge a test by its assertions, not its name. One test named for clearing a progress indicator
asserted that the indicator was _not_ cleared.

Done when every test in the lane has a mark and a line of evidence.

## 4. Plan each lane by layer

Treat the ledger as input, not as the edit list. A second read-only pass starts from the ledger and
looks for a redundant _layer_. In one campaign, several suites replayed the same shared helper
through a single mock, alongside stronger suites that used real streams and recorded HTTP fixtures.

Name the _keeper_ suite for each contract. Prefer the real transport with a fake network over a
mocked collaborator. Correct any ledger mistakes this pass finds.

Done when each lane's plan names the files it retires, the keeper for each contract, the
assertions to carry into keepers, and the seams it lets you remove.

## 5. Cut over

Edit one lane at a time. Route all changes to shared harnesses and support files through one
person or agent, one after another. With each lane, remove the seams it unlocks: injection
parameters, getters, reset exports, and layers of indirection.

If the repo routes tests to CI jobs by path, keeps a test inventory, or tracks a coverage or size
baseline, update it. Put lasting test-ownership rules in the area's `AGENTS.md` or `CLAUDE.md`.
Write only rules drawn from mistakes this campaign actually found.

Done when every lane's plan is applied and each lane's keepers pass.

## 6. Review what was preserved

Before you claim completion, have independent reviewers compare the deleted coverage against the
keepers, one reviewer per group of related owners. They look for contracts that lost their only
test. They also look for new assertions that can't fail, such as a rejection case that production
code never reaches. In one campaign, this review found nine real gaps and one unreachable
assertion.

For each restored contract, make one deliberate _mutation_ to the owner and confirm the keeper
fails. Then restore the source exactly.

Done when every reported gap is restored or rejected with evidence from the source, and every
restored contract has a mutation that its keeper caught.

## 7. Fix product defects

A baseline failure that survives into a keeper is a bug. Fix it at the owner in its own commit,
and prove the fix through the real user flow. Run a _control_ that reverts the fix and shows the
old behavior. Record unrelated product problems you find as follow-ups. Don't fix them in the
campaign.

Done when each fixed defect has a failing control and a passing run on the same harness.

## 8. Reconcile and hand off

A campaign outlives many commits to the main branch. We recommend merging the main branch into
the campaign instead of rebasing a long series of commits. When the main branch changed a file the
campaign deleted, keep the deletion. Port the new contract into the keeper, and confirm every new
regression test from the main branch still has a home. Rerun the area's full test suite and repeat
any end-to-end proof on the merged result.

Review tools often show a truncated file list on a diff this large. Review the file list yourself.

Hand off with the report from [SKILL.md](SKILL.md), plus:

- Baseline and final test and test-support line counts, with production counted separately.
- The lanes, the retired layers, and the keepers.
- The preservation gaps found, and the mutations that proved each fix.
- Product defects, with the control and the passing run.
