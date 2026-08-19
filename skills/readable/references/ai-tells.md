# AI tells

Adapted from the unslop skill (github.com/cursor/plugins, pstack/skills/unslop).

The Google guide tells you how to be clear. This file tells you how to stop sounding like a language
model. The two overlap a lot. Where they conflict, this file wins, because a sentence that follows
every Google rule and still reads as machine-generated has failed at the only job that matters.

Two failure modes, not one. The obvious one is slop: puffery, filler, the same six words. The other
is what's left after you scrub the slop out, which is sterile, voiceless text that nobody wrote. Fix
both.

## The self-audit

Before you send anything, read it back and ask one question: what makes this obviously
AI-generated? Whatever you name, fix. Then send.

## Voice

- **Have an opinion.** React to the facts instead of listing pros and cons and leaving the reader to
  score it. If you think the migration is a bad idea, say so and say why.
- **Vary the rhythm.** Short sentences. Then a longer one that takes its time and earns the length.
  Sentences of uniform length are a tell on their own.
- **Acknowledge complexity.** "Fast, but it drops writes under load" beats "fast".
- **Use "I" when you're speaking as yourself.** In a chat reply, a review comment, or a PR
  description, first person is not unprofessional. In reference docs and product docs, stay with the
  Google convention: "you" for the reader, third person for the software.
- **Let a little mess in.** Perfectly balanced structure looks machine-made. Three sections of
  exactly three bullets each is a fingerprint.
- **Be specific.** Not "this is concerning" but "the agent retried 400 times overnight and nobody was
  paged".

## Content patterns

1. **Puffery.** "pivotal moment", "testament to", "evolving landscape", "setting the stage for",
   "indelible mark", "deeply rooted". Cut it and state what happened.
2. **Name-dropping.** Listing outlets, tools, or companies without context. Pick one and say what it
   actually said or did.
3. **Superficial -ing phrases.** A trailing clause that starts with "highlighting", "ensuring",
   "reflecting", "showcasing", "fostering", "underscoring". Delete it, or replace it with the fact it
   was gesturing at.
4. **Promotional language.** "nestled", "vibrant", "breathtaking", "groundbreaking", "renowned",
   "stunning", "must-visit", "seamless", "robust", "powerful". Describe neutrally.
5. **Vague attribution.** "Experts believe", "Industry reports suggest", "Some critics argue". Name
   the source or cut the claim.
6. **Formulaic challenge-and-triumph.** "Despite these challenges, the project continues to thrive."
   Replace with the specific facts.
7. **Generic conclusion.** "The future looks bright." "Time will tell." State a specific plan, a
   number, or nothing.

## Language patterns

8. **AI vocabulary.** additionally, crucial, delve, enduring, enhance, fostering, garner, interplay,
   intricate, landscape (abstract), pivotal, showcase, tapestry (abstract), testament, underscore,
   vibrant. See [word-choice.md](word-choice.md) for the replacements.
9. **Fancy ways to say "is".** "serves as", "stands as", "boasts", "features", "represents". Say "is"
   or "has".
10. **"Not just X, but Y."** Also "It's not about X, it's about Y". State the point directly.
11. **Rule of three.** Forcing ideas into groups of three when you have two or five. Use the real
    number.
12. **Synonym cycling.** Protagonist, main character, central figure, hero in one paragraph. Pick one
    word and repeat it. This matches the Google rule: one term per concept.
13. **False ranges.** "from X to Y" where X and Y aren't ends of any scale: "from authentication to
    logging". List the things.
14. **Abstract metaphor nouns.** substrate, wedge, vector, locus, vantage, nexus, primitive (as a
    noun), harness (as a metaphor), surface (as in "API surface"), bedrock, scaffolding (as a
    metaphor), modality, paradigm, gold-plating, ratchet, evacuate (for moving code), endgame, north
    star, flywheel. Each has a plainer concrete word. "Substrate" is "base". "Wedge in" is "add".
    "Vector" is "way". "Gold-plating" is "more than the job needs". "Evacuate" is "move out".
    "Endgame" is "the last phase".
15. **Excessive hedging.** "could potentially possibly be argued that it might" is "may". One hedge
    per claim, at most.
16. **Adverbs propping up weak verbs.** "runs quickly" is "is fast", or the number. "significantly
    improves" is the measured delta. If the adverb is doing the work, the verb is wrong.

## Style patterns

17. **Em dashes.** Don't use them. Use a period or a comma. Reaching for parentheses or an en dash
    instead just trades one tell for another. If a thought needs separating, end the sentence. This
    overrides the Google guidance on dashes.
18. **Colons as mid-sentence connectors.** A colon before a list or an example is fine. A colon
    welding two clauses together usually adds nothing: "If you're coming from cron: instead of
    registering handlers, you describe conditions." Rewrite so the point stands alone.
19. **Boldface overuse.** Don't bold every proper noun, acronym, or phrase you like. Bold is for UI
    labels and run-in headings.
20. **Inline-header lists.** The tell is a bold label and colon that restates the line that follows:
    "**Performance:** Performance improved by 20%." Convert to prose. A bold lead-in that ends in a
    period, names the thing, and is followed by genuinely new detail is fine: "**Schema in
    TypeScript.** Tables live in one file."
21. **Title case headings.** Sentence case, always.
22. **Decorative emoji.** None in headings, bullets, or status lines.
23. **Curly quotes.** Straight quotes and apostrophes only.

## Chat artifacts

24. **Chatbot phrases.** "I hope this helps!", "Let me know if you have any questions", "Of course!",
    "Certainly!", "Great catch!", "Found the smoking gun!" Cut them.
25. **Sycophancy.** "Great question!", "You're absolutely right!", "Excellent point!" Answer the
    question instead.
26. **Cutoff and capability disclaimers.** "While specific details are limited…", "As an AI…". Find
    the detail or drop the sentence.
27. **Filler.** "In order to" is "To". "Due to the fact that" is "Because". "It is important to note
    that" gets deleted whole. See the word list.

## Plain speech

28. **Say what it does, not how it feels.** "the database stays close at hand", "SQL you can read",
    "types that follow your schema" all name a feeling. Name the mechanism or the number instead:
    "`.toSQL()` returns the exact string sent to the database", "a column rename fails the build".
    Ask what the sentence tells the reader to do or know, then write that. If you can't restate it as
    a concrete instruction, fact, or number, cut it. Second check: if the sentence could appear
    unchanged in another project's docs, it says nothing about this one. Cut it.
29. **Split dense sentences.** If the reader has to backtrack to parse it, break it in two or drop a
    clause. One idea per sentence.
30. **Active voice.** Catch "is/are/was/were + past participle" and name the actor. "Queries are
    validated" becomes "the compiler validates queries". Passive is fine when the actor is unknown or
    genuinely doesn't matter.
