# Word choice

Source: https://developers.google.com/style/word-list, /jargon, /inclusive-documentation,
/translation. Fetch the word list itself for anything not settled here.

## Never use these

| Don't use | Use instead |
| --- | --- |
| e.g. | for example |
| i.e. | that is |
| etc. | rewrite the list, or "and so on" |
| aka | also known as |
| N/A | not applicable, or not available |
| and/or | "and", "or", or "A, B, or both" |
| please | nothing — just give the instruction |
| simply, easy, quickly, just | nothing — cut it |
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

- **can** — ability, permission, or an option. **may** — official permission only.
  **might** — possibility. Don't write "could" where "can" works.
- **must** — a requirement. **should** — a recognized best practice, nothing weaker.
- **because**, not **as**, for causation. **since** is about time.
- **whether**, not **if**, when presenting alternatives.
- **after**, not **once**.
- **that** for a restrictive clause, no comma. **which** for a nonrestrictive clause, with a comma.
- **between** two distinct things; **among** a group.
- **each** for individual items; **all** for the group.
- **earlier** / **later** for versions — not lower / higher, not old / new.
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
