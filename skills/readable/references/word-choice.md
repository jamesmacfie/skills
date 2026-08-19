# Word choice

Sources: https://developers.google.com/style/word-list, /jargon, /inclusive-documentation,
/translation, plus the unslop skill for the AI vocabulary and metaphor-noun sections. Fetch the
Google word list itself for anything not settled here.

## Never use these

| Don't use | Use instead |
| --- | --- |
| e.g. | for example |
| i.e. | that is |
| etc. | rewrite the list, or "and so on" |
| aka | also known as |
| N/A | not applicable, or not available |
| and/or | "and", "or", or "A, B, or both" |
| please | nothing, just give the instruction |
| simply, easy, quickly, just | nothing, cut it |
| click here, this document, this article (as link text) | the page title or a description |
| allows you to | lets you |
| in order to | to |
| leverage (meaning use) | use |
| utilize | use |
| comprise | consist of, contain, include |
| desire, desired | want, need |
| learnings | knowledge, what you learned |
| performant | the specific quality: fast, accurate, memory-efficient |
| actionable | that you can act on |
| functionality | features, capabilities |
| key (meaning important) | crucial, important |
| whitelist, blacklist | allowlist, denylist (or blocklist, safelist) |
| master (with slave) | primary, parent node, main |
| slave | replica, subordinate, follower |
| grandfathered | legacy, exempt |
| sanity check | final check, verification |
| crazy, insane, bonkers | complex, complicated, baffling, outliers |
| cripple | slows down, impairs |
| dumb down | simplify, remove jargon |
| lame, gimpy, ghetto | say what's actually wrong |
| blind to | unaware of, ignores |
| dummy variable | placeholder |
| man-hours, manpower | person-hours, staff |
| mankind | humanity |
| guys, you guys | everyone, folks |
| man-in-the-middle | on-path attacker |
| brown bag | learning session |
| ninja, rockstar | expert |
| abort, kill | stop, exit, cancel, end |
| hang | stop responding |
| uncheck, deselect (a checkbox) | clear |
| check (a checkbox) | select |
| pop-up, popup | dialog, menu |
| hamburger menu | Menu |
| omnibox | address bar |
| navigation bar | navigation menu |
| cell phone | mobile phone, mobile device |
| cellular data / network | mobile data / network |
| long press | touch & hold |
| access (verb) | see, edit, find, use, view |
| interface (verb) | interact, communicate |
| persist (transitive) | save, store |
| display (with no object) | appears, is displayed |
| Google (verb) | search with Google |
| foo, bar, baz | a meaningful name |
| k8s | Kubernetes |
| MIME type | media type |
| demilitarized zone, DMZ | perimeter network |
| pets vs. cattle | persistent vs. dynamic |
| NoOps | fully managed |
| first-class citizen | higher-order, or name the feature |
| tl;dr, ymmv, RTFM | write the sentence |
| ! (exclamation mark) | a period |
| & (as "and") | and |

## AI vocabulary

These words are rare in human writing and common in generated text. Seeing two or three in a
paragraph is enough to date the whole thing. Full context in [ai-tells.md](ai-tells.md).

| Don't use | Use instead |
| --- | --- |
| delve into | look at, dig into, read |
| crucial, pivotal, vital, essential | important, or say what breaks without it |
| additionally, moreover, furthermore | and, also, or start the sentence |
| underscore, highlight (meaning show) | show, prove, or name the fact |
| showcase | show, demonstrate |
| enhance | improve, or name the change |
| garner | get, collect, win |
| foster, fostering | build, encourage, cause |
| landscape (abstract) | the field, the market, the options |
| tapestry, mosaic, symphony (abstract) | cut the sentence |
| testament to | evidence of, or state the fact |
| interplay | how they interact |
| intricate | complex, detailed, fiddly |
| enduring | lasting, or say how long |
| seamless, frictionless | say what step is gone |
| robust | say what it survives |
| powerful, cutting-edge, groundbreaking | say what it does |
| vibrant, stunning, breathtaking, nestled | describe it plainly |
| serves as, stands as, represents (meaning is) | is |
| boasts, features (meaning has) | has |
| a rich set of, a wide range of | the number, or the list |
| navigate (meaning deal with) | handle, work through |
| unlock, empower, elevate, supercharge | say what becomes possible |
| in the realm of, in the world of | in |
| it is important to note that | delete it |
| when it comes to | for, about, with |
| not just X, but Y | state the point once |

## Abstract metaphor nouns

Each of these reads as technical but has a plainer, concrete word:

| Don't use | Use instead |
| --- | --- |
| substrate | base, foundation |
| wedge (verb) | add, insert |
| vector (meaning route) | way, method, path |
| locus, nexus | centre, the point where |
| vantage | view, position |
| primitive (noun) | building block, or name the thing |
| harness (metaphor) | setup, rig, test runner |
| surface (as in "API surface") | the API, the set of endpoints |
| bedrock | foundation |
| scaffolding (metaphor) | the starter code, the structure |
| modality, paradigm | approach, mode, style |
| gold-plating | more than the job needs |
| ratchet (metaphor) | name the mechanism, or "a limit that only tightens" |
| evacuate (of code) | move out |
| endgame | the last phase |
| north star, flywheel | the goal, or what compounds |

## Ableist and othering language

Describe the person first, or the condition plainly:

| Don't use | Use instead |
| --- | --- |
| the disabled, the elderly, seniors | people with disabilities, older adults |
| a quadriplegic | a quadriplegic person |
| wheelchair-bound | uses a wheelchair |
| victim of, suffering from | experiencing, living with |
| physically challenged | name the disability |
| abnormal, deficient, deformed (of people) | fine for systems and objects, not people |
| native / non-native speaker | describe the actual language proficiency |
| preferred pronouns | pronouns |

Research what a community calls itself before writing about it.

## Word pairs that get confused

- **can**: ability, permission, or an option. **may**: official permission only.
  **might**: possibility. Don't write "could" where "can" works.
- **must**: a requirement. **should**: a recognized best practice, nothing weaker.
- **because**, not **as**, for causation. **since** is about time.
- **whether**, not **if**, when presenting alternatives.
- **after**, not **once**.
- **that** for a restrictive clause, no comma. **which** for a nonrestrictive clause, with a comma.
- **between** two distinct things; **among** a group.
- **each** for individual items; **all** for the group.
- **earlier** / **later** for versions, not lower / higher, not old / new.
- **directory** in a command line; **folder** in a graphical interface.
- **type** for entering text with a keyboard; **enter** for supplying a value by any means.

## Spelling and one-word-or-two

One word: backend, frontend, codebase, codelab, checkbox, datastore, dataflow (stream processing),
data type, endpoint, lifecycle, livestream, namespace, webpage, hostname, workaround, email, emoji,
prebuilt, prerecorded, precapture, preemptible, timestamp.

Two words: data center, data source, style sheet, plain text (except "plaintext" in cryptography),
name server, health check.

Hyphenated: on-premises, pre-existing, pre-shared key, multi-region, self-managing, cross-region,
big-endian, little-endian, error-prone, parent-child, blue-green, cloud-based, user-friendly.

Case and form: I/O, NoSQL, OAuth 2.0, macOS, PostgreSQL, lint, gcloud.

Noun / adjective / verb splits: login (noun), plug-in (adjective), log in and plug in (verbs).
"Sign in" beats "log in".

Other rulings: "data is" (singular). "app", not "application", for end-user software.
"administrator", not "admin", unless it's a UI label. "configuration", not "config".
"disadvantages", not "cons". "US", not "America". "username", not "account name".
"unavailable", not "grayed out". "retrospective" or "blameless postmortem", not "postmortem" alone.
"listen on" a port, not "listen to". Don't shorten "Google Cloud" to "Cloud".

## Jargon

Before using a term of art, ask: can you write around it? Is there a more specific word? If you use
it once, define it in parentheses or link a definition. If you use it throughout, define it on first
reference. Keep it only when readers actually search for that term.

Common offenders and their plain versions: blast radius (affected area), ingest (import, load),
off-the-shelf (ready-made), shifting left (moving earlier in the process), cold standby (an identical
backup system), back-of-the-envelope (rough, informal), post-mortem (a review of what worked).

If the jargon is a literal keyword in code, keep it in code font and say what it refers to.

## Product and trademark names

- Use the full official name, capitalized as the owner capitalizes it. Match UI labels exactly.
- Don't put "the" before a product name; do use it before a tool or API name ("the Transcriber API").
- Never use a product or feature name as a verb, and never pluralize or possessive a trademark.
  "Google Search performance", not "Google Search's performance".
- Lowercase feature names unless they're officially capitalized.
