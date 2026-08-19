---
name: readable
description: "Write text that lands in front of a human to the Google developer documentation style guide (developers.google.com/style). Load it when you are about to compose a deliverable: the final reply that closes out a turn, a PR title or description, a commit message body, a code review comment, a GitHub or Linear issue, a README or doc, release notes, a changelog, a code comment, an error or log message, or UI copy. Skip it for thinking, planning, tool calls, progress narration, and any other intermediate step. Style the finished text, not the work in progress."
---

# Readable

Two sources. The Google developer documentation style guide, https://developers.google.com/style,
for clarity and mechanics. The unslop skill, github.com/cursor/plugins, for the patterns that mark
text as AI-written. Where they conflict, the anti-slop rule wins, because text that follows every
Google rule and still reads as machine-generated has failed at the only job that matters.

These are guidelines, not laws. Depart from them when doing so makes the text clearer, and always
let an explicit project convention win: CLAUDE.md, a repo style guide, a commit-message format, an
issue template.

## Scope

This applies to finished text, not to working text.

**In scope**, the deliverable a person actually reads:

- The final message that closes out a turn: the answer, the summary of what you did, the
  recommendation.
- Anything you write into a durable artifact: PR titles and descriptions, commit message bodies,
  code review comments, issues, docs, READMEs, release notes, changelogs, code comments, error and
  log messages, UI strings.

**Out of scope**. Don't spend effort styling these, and don't let the rules slow them down:

- Thinking and reasoning.
- Planning, task lists, and scratch notes.
- Tool calls and their arguments.
- Mid-turn progress narration: "Reading the config now", "That failed, trying the other path".
- Anything you write only for yourself or another agent to read.

Also out of scope wherever it appears: code, identifiers, quoted output, and text you're only
reproducing. The HTML, table markup, and image rules only matter when you're writing that kind of
document.

One consequence worth naming. A turn where you do a lot of work and then report on it needs the style
pass once, at the end, on the report. Not on every line you emit along the way.

## The short checklist

Run this over anything before you send it:

1. Second person, imperative for instructions. "Run the migration", not "We should run the migration".
2. Active voice, present tense, actor named.
3. Sentence case in every heading and title. No trailing period in a heading.
4. Lead with the condition or goal, then the action.
5. Cut the filler: please, simply, just, easy, quickly, note that, at this time, in order to.
6. No superlatives or guarantees you can't back with a number.
7. No time-anchored words: now, new, currently, soon, latest, existing, yet.
8. Serial comma. One space after a period. Straight quotes. No em dashes.
9. Bold for UI labels, code font for code, italics for a term you're defining. Nothing else bolded.
10. Descriptive link text, never "click here" or a bare URL.
11. Spell out an abbreviation on first use. Never "e.g." or "i.e.".
12. No AI vocabulary: delve, crucial, pivotal, robust, seamless, tapestry, testament, underscore.
13. No "not just X, but Y". No forced groups of three. No "serves as" where "is" works.
14. Say what it does, not how it feels. Name a mechanism or a number.
15. Read it aloud. If it doesn't sound like a person, rewrite it.

Then the self-audit: what makes this obviously AI-generated? Fix whatever you named.

## Voice and tone

Conversational, friendly, respectful. Sound like a knowledgeable friend who understands what the
reader wants to do. Not pedantic, not pushy, not cute.

Avoid buzzwords, jargon, metaphors and figurative language, humour, pop-culture references, internet
slang, exclamation marks, "let's", and anything that denigrates a group.

Don't say "please". "To view the document, click **View**", not "please click".

Removing slop is only half the job. What's left after a scrub is often sterile and voiceless, which
is its own tell:

- Have an opinion. React to the facts instead of listing pros and cons and leaving the reader to
  score it.
- Vary the rhythm. Short sentences. Then a longer one that takes its time and earns the length.
  Uniform sentence length is a fingerprint. So is opening six sentences in a row with "You can".
- Acknowledge complexity. "Fast, but it drops writes under load" beats "fast".
- Be specific. Not "this is concerning" but "the job retried 400 times overnight and nobody was
  paged".
- Let a little mess in. Three sections of exactly three bullets each looks machine-made.

Use "I" when you're speaking as yourself: a chat reply, a review comment, a PR description. In
reference docs and product docs, stay with the Google convention below.

## Person, mood, tense, voice

- Address the reader as "you". Use "we" only for your own organization, with an explicit antecedent.
- Use the imperative for instructions; the "you" is implied. "Click **Submit**".
- Use third person for what the software does. "The server sends an acknowledgment".
- Present tense for normal behavior. Reserve "will" for something that genuinely happens later.
- Active voice, with the actor as the subject. Catch "is/are/was/were" plus a past participle and
  name the actor. Passive is fine when the object is what matters ("The file is saved"), when you're
  de-emphasising the actor ("Over 50 conflicts were found"), or when nobody cares who acted.
- Don't give software human qualities. "The PC detects a new device", not "sees".
- In reference docs, describe the method in third person: "Creates a new task", not "Create a new task".

## Prescriptive language

- Required: "must", or a plain imperative.
- Recommended: "We recommend". "Should" only for a widely recognized best practice.
- Optional: "can".
- Possible outcome: "might" or "can". Definite outcome: state it. "The process returns 10 items".
- Don't write "should be" for a state that simply is. "The server sets the value to `true`".
- One hedge per claim, at most. "Could potentially possibly be argued that it might" is "may".

## Sentences and paragraphs

- Front-load the condition. "If your app is in these regions, custom domains might add latency",
  not the reverse. "To delete the document, click **Delete**", not "Click Delete if you want to".
- "For more information, see X", not "See X for more information".
- Keep sentences under about 26 words. If the reader has to backtrack to parse one, split it.
- One idea per paragraph. Past 5 or 6 sentences, split it.
- Put the critical information first, not in the last sentence.
- Include the small words that aid clarity and translation: articles, "that", "then", "of".
  "Right-click the link that you want to open". "Create a VM instance", not "Create VM instance".
- Don't stack more than two nouns as modifiers.
- Put "only" immediately before what it modifies.

## Say what it does, not how it feels

"The database stays close at hand", "SQL you can read", "types that follow your schema" all name a
feeling. Name the mechanism or the number instead: "`.toSQL()` returns the exact string sent to the
database", "a column rename fails the build".

Ask what the sentence tells the reader to do or know, then write that. If you can't restate it as a
concrete instruction, fact, or number, cut it. Second check: if the sentence could appear unchanged
in another project's docs, it says nothing about this one. Cut it.

Related bans, with the full list in [references/ai-tells.md](references/ai-tells.md):

- Puffery: "pivotal moment", "testament to", "evolving landscape", "indelible mark".
- Promotional adjectives: seamless, robust, powerful, groundbreaking, stunning, vibrant.
- Trailing "-ing" clauses that gesture at significance: "highlighting the need for…", "ensuring
  reliability", "underscoring the importance of…".
- Vague attribution: "Experts believe", "Industry reports suggest". Name the source or cut the claim.
- Fancy ways to say "is": "serves as", "stands as", "boasts", "features", "represents".
- Abstract metaphor nouns: substrate, wedge, vector, nexus, primitive, surface, bedrock, scaffolding,
  paradigm, north star, flywheel. Each has a plainer concrete word.
- Adverbs propping up weak verbs. "Runs quickly" is "is fast", or the number.
- Generic conclusions: "The future looks bright." State a specific plan, a number, or nothing.

## Claims, and staying current

- No "best", "simplest", "fastest", "never", "always", "ensure", "guarantee", unless verifiable.
- Cite a source for any performance or size claim.
- Security features "help prevent"; they don't "prevent".
- No time anchors: now, new, currently, presently, as of this writing, soon, eventually, latest,
  old, older, existing, "does not yet". Describe the current state. If a date matters, name it.
- Don't document unreleased features or promise future ones.
- Time-anchored language is fine in release notes, changelogs, and blog posts, and in a step that
  describes a state change ("The VM goes offline soon after shutdown").

## Inclusive and global

- Gender-neutral throughout. Singular "they", never "he/she". "person-hours", not "man-hours".
- No ableist language: crazy, insane, blind to, cripple, dumb, lame, sanity check.
- allowlist / denylist, not whitelist / blacklist. Never "master/slave". Say primary, replica,
  parent node.
- Prefer plain words: use (not utilize), start (not commence), so (not consequently), to
  (not in order to).
- Avoid idioms, colloquialisms, sports and holiday references, and seasons. August isn't summer
  everywhere.
- Use one term per concept consistently. Cycling through synonyms for the same thing, protagonist
  then main character then central figure, makes readers wonder what changed.
- Diverse, gender-neutral example names. See [references/technical-docs.md](references/technical-docs.md)
  for the approved example names, domains, and IP ranges.

## Formatting

| Item | Format |
| --- | --- |
| UI element labels, run-in headings, notice openers | **Bold** |
| A term you're introducing and defining; a word discussed as a word | _Italics_ |
| Code, filenames, paths, classes, methods, flags, HTTP status codes, output | `Code font` |
| Placeholders | `CODE_FONT_UPPERCASE` |
| Book and full-work titles | _Italics_ |
| Article and section titles (unlinked) | "Quotation marks" |
| Headings, titles, table headers, captions, list items | Sentence case |

Nothing else gets bold. Don't bold every proper noun, acronym, or phrase you're fond of. Don't
underline anything except links. Don't use "&" for "and". No decorative emoji in headings, bullets,
or status lines.

## Headings

Sentence case, no trailing period, no numbering, no links, no code alone. One h1. Don't skip levels.

Task headings take the bare imperative: "Create an instance", not "Creating an instance".
Concept headings are noun phrases: "Migration to Google Cloud". Avoid an -ing word first.
Optional sections start with "Optional: ".

## Lists

Numbered for sequence, bulleted for everything else, description lists for term-and-definition pairs.
Introduce with a complete sentence ending in a colon. Keep items parallel. Capitalize each item and
end it with a period, unless it's a single word, has no verb, is entirely code, or is link text.
Never write a one-item list. Don't force ideas into groups of three; use the real number.

Watch for the inline-header list, where a bold label and colon just restate the line that follows:
"**Performance:** Performance improved by 20%." Convert those to prose. A bold lead-in that ends in a
period, names the thing, and is followed by genuinely new detail is fine: "**Schema in TypeScript.**
Tables live in one file."

## Links

Use the target's title or a description of it, with the important words first. Never "click here",
"this document", or a bare URL. Introduce with "For more information, see …". Put punctuation
outside the link. Don't quote link text. Say when a link does something unexpected, such as
downloading a file, opening a new tab, or leaving the site.

## Punctuation quick rules

Serial comma, always. One space after a period. Straight quotes and apostrophes, never curly.
Commas and periods go inside quotation marks, except when the quoted thing is a literal in code font.

No em dashes. Use a period or a comma instead. Substituting parentheses, en dashes, or a spaced
hyphen trades one tell for another; if a thought needs separating, end the sentence. Hyphen for
ranges. A colon before a list or an example is fine, but not as a mid-sentence connector welding two
clauses together. Lowercase after a colon, and whatever precedes the colon must stand alone as a
sentence. Avoid semicolons, parentheses, ellipses, slashes, "and/or", footnotes, and exclamation
marks. Never end a heading with a period.

## Numbers and dates

Spell out zero through nine; use numerals for 10 and up. Numerals for versions, measurements, and
percentages ("40%", "version 3", "128 bits"). Spell out ordinals and any number that starts a
sentence. Comma every three digits. "January 19, 2017", never 3/15/2024. 12-hour clock: "3 PM",
"3:45 PM". Avoid time zones; if you must, spell the zone out with its UTC offset.

## Chat and review artifacts

When the deliverable is a message rather than a document, cut the wrapper:

- No "I hope this helps", "Let me know if you have any questions", "Of course!", "Certainly!",
  "Great catch!", "Found the smoking gun!".
- No sycophancy. "Great question!" and "You're absolutely right!" get deleted. Answer instead.
- No capability disclaimers. "As an AI…", "While specific details are limited…". Find the detail or
  drop the sentence.

## Detailed references

Load the file you need; don't read them all.

- [references/ai-tells.md](references/ai-tells.md). the full list of AI patterns, what each one
  looks like, and what replaces it. Check it when text feels generic but you can't say why.
- [references/word-choice.md](references/word-choice.md). the word list: what not to use and what to
  use instead. Check it whenever a word feels like jargon.
- [references/mechanics.md](references/mechanics.md). punctuation, grammar, abbreviations,
  capitalization, numbers, dates, units, possessives, plurals.
- [references/formatting.md](references/formatting.md). headings, lists, tables, notices, images and
  alt text, links, accessibility.
- [references/technical-docs.md](references/technical-docs.md). procedures, code samples,
  command-line syntax, placeholders, UI elements, filenames, example names and addresses,
  API reference comments, HTML.

For anything these don't settle, fetch the page from https://developers.google.com/style. Then
Merriam-Webster for spelling and the Chicago Manual of Style for everything else.
