---
name: planner
description: "Turn a known goal into a concrete implementation plan for an existing codebase, by reading the code first and then interrogating the user in rounds until nothing is left assumed. Use inside plan mode when the destination is clear but the architecture of the change, or the order of the work, is not. Produces a plan, optionally a context doc and tickets. Executes nothing."
disable-model-invocation: true
---

# Planner

The goal is known. What's missing is the shape of the change: where it belongs, what it touches,
what order the work goes in, and which of the small decisions inside it the user actually cares
about.

This skill exists because of one failure mode. An agent reads the task, takes it literally, guesses
at everything it wasn't told, reinvents a pattern the codebase already has, and returns a plan that
technically works and sits at the wrong layer. Every rule below is aimed at that.

If the goal isn't known, this is the wrong skill. Say so and stop. Charting a route to a destination
nobody has named is a different job.

## The rule that does the most work

**Every question you put to the user must have already survived a search.**

Finding facts is your job. Making decisions is the user's. A question the codebase already answers
is work you skipped, and it costs the user more than the answer is worth. Read first, ask second.
When a question occurs to you, try to answer it with a search before you type it.

## Process

Seven steps, in order.

### 1. Anchor the goal

Write one line: what changes, for whom, and how you'd know it worked. Get that wrong and every
question after it is wasted. If your line and the user's ask differ, say so now.

### 2. Read the code

Before the first question:

- Locate the code the task lands in. Read it, including the parts that look boring.
- Trace the data from where it enters to where it comes to rest. Name the transformations.
- Name the callers and the consumers. Something upstream depends on how this behaves already.
- Find the data model and the contracts. The explicit ones are types, schemas, and endpoints. The
  implicit ones are conventions, argument orders, and the things everyone knows.
- Find the tests. The way this area is tested tells you where its seams are.

Launch Explore agents in parallel when the surface is wide, one per area, and keep reading the
critical files yourself.

By the end of this you can name the blast radius. If you can't, keep reading.

### 3. Sweep four lenses

Each lens generates candidate questions. Skip a lens when it doesn't apply, in one line that says
why. Don't pad a round to fill all four.

**Architecture and data model.** Where does this belong, and at what layer? What's the blast radius?
Does the model support this change or is it being forced into a shape it resists? Which contracts
move, and who is still holding the old one? Is this the cause or the symptom?

**User experience.** What does a person see, click, and get told when it fails? What are the empty,
loading, and half-finished states? What happens on the second attempt?

**Workflow.** What sequence does this sit inside? Where can it be interrupted, retried, or abandoned
midway? Who is partway through the old flow when this ships?

**Developer experience and maintenance.** How does someone test this, debug it at 3 AM, and change
it in six months? What does it cost to delete? What will the next person assume that isn't true?

### 4. Ask in rounds

The _frontier_ is every question whose prerequisites are settled: the ones you can ask without
guessing at an answer you haven't heard. Ask the whole frontier in one round. Each question carries
your recommended answer, because a recommendation is faster to correct than a blank to fill.

A question whose answer depends on another open question belongs to a later round. Don't ask it.

Default format, any number of questions:

```
**Q1. <short title>**

<the question. Name the files and lines that make it a question. Give the options if there are
discrete ones.>

Recommend: <your answer, and the one-line reason>

---

**Q2. <short title>**
...
```

When a round is four or fewer questions and each one is a discrete choice, use `AskUserQuestion`
instead, with your recommended option first and labelled as the recommendation. Anything wider or
more open-ended goes in prose.

Then wait. The answers settle decisions, which push the frontier outward and unblock the questions
that depended on them. Recompute the frontier and ask the next round.

### 5. Cite precedent

Consistency with the codebase is the point. So every decision names the existing thing it follows,
with a path and a line. "Same shape as the retry in `src/api/client.ts:88`."

No precedent means one of two things, and you say which:

- You didn't look hard enough. Go look again.
- This is a new pattern. Then it needs a stated reason, and it takes the smallest form that works.

The one place consistency yields is a recommendation to change the architecture itself. When the
existing shape is the problem, the grain of the code is evidence, not law, and simplicity decides.
Say plainly that you're proposing to break the pattern, and why.

### 6. Run the simplicity gate

Before the plan is final, try to delete it.

- Can two steps merge into one?
- Is any step there for a need nobody stated?
- Would the boring version hold? What would it cost when it stops holding?
- Does any new abstraction have two callers? One caller is a hypothetical seam.
- What's the smallest change that makes the goal true, and what does the rest of the plan buy?

Say what this pass cut. A plan that survives it is the plan.

### 7. Land it

The questioning is done when the frontier is empty and the user has said they're happy. Not when
you run out of ideas, and not when the round count feels like enough. Ask them directly, then write.

## Delivery

### The plan

The default, and where plan mode ends. Sections:

- **Context.** The goal, and why this change is being made.
- **What it touches.** The blast radius, with paths. What must not change.
- **Decisions.** Each one with the precedent it follows, or the reason it's new.
- **Implementation order.** Steps someone can execute and check one at a time. What each step makes
  true.
- **Out of scope.** What was ruled out, and why. A scope boundary is recorded once, not revisited.
- **Verification.** How to run it and see the thing work end to end. No plan ships without this.

### Documented output

Only when asked for. Default location `docs/plans/<slug>/` unless the user names another. Tickets go
to whichever tracker is available: Linear, GitHub, or files on disk. Ask if it isn't obvious.

The structure is one _context doc_ plus thin tickets.

The context doc holds everything the conversation knew: the research, the data-flow trace, every
decision with its precedent, what's out of scope, and how to verify. It's the only place any of that
lives, so nothing is restated elsewhere.

Each ticket states one vertical slice, demoable on its own, sized for a single agent session, with
the tickets it's blocked by. It links to the context doc by path, in the body, near the top.

One rule matters more than the rest here. A subagent handed one ticket and nothing else must be able
to reach the full context from the ticket alone. Write every ticket as if that's how someone reads
it, because it is.

## Plan, don't do

This skill produces a plan. It writes no code, runs no migration, and touches nothing but the plan
file and, when asked, the docs. The pull to start building is the signal the plan is done and it's
time to hand off.
