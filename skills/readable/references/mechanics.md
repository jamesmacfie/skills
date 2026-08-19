# Mechanics: punctuation, grammar, numbers

Source pages under https://developers.google.com/style: /commas, /dashes, /hyphens, /colons,
/semicolons, /periods, /quotation-marks, /parentheses, /slashes, /ellipses, /abbreviations,
/capitalization, /contractions, /possessives, /pluralization, /articles, /prepositions, /numbers,
/dates-times, /units-of-measure, /mathematical-notation, /phone-numbers.

## Commas

- Serial comma before the final "and" or "or": "zones, regions, and multi-regions".
- After an introductory word or phrase: "Finally, only groups can…".
- Before a coordinating conjunction joining two independent clauses. Skip it if both are very short.
- Around a nonrestrictive "which" clause. No comma before a restrictive "that" clause.
- After a conjunctive adverb, with a semicolon, period, or dash before it: "…; otherwise, the
  server returns an error".
- Generally no comma before "because".

## Dashes and hyphens

- No em dashes. They're a strong AI tell. Use a period or a comma. Don't substitute parentheses,
  an en dash, or a spaced hyphen, which just trades one tell for another.
- No en dashes. Use a hyphen or the word "to".
- Never separate a term from its description with a dash. Use a colon: "Example: this is an example".
- Prefixes usually close up: metadata, preprocessing, infrastructure. Hyphenate after "self" and
  "cross", before a capitalized word or a number (non-Google, post-2000), when it prevents a
  misreading (re-mark, de-energize), and when the base is already hyphenated (un-Google-like).
- Hyphenate a compound modifier before a noun: "well-designed app", "Android-specific techniques".
  Not after the verb: "the app is well designed". Not with an -ly adverb: "publicly available".
- Hyphenate a spelled-out unit with a number: "64-bit system", "five-minute wait". Don't hyphenate an
  abbreviated unit: "200 GB disk", "50 Mbps connection".
- Hyphen for ranges, no spaces: "8-20 files", "2012-2016". Don't mix with "from".
- Suspended hyphens take a space after: "one- or two-hour intervals".

## Colons and semicolons

- Whatever precedes a colon must stand alone as a sentence. "The fields are defined as follows:",
  not "The fields are:".
- Lowercase the first word after a colon, unless it's a proper noun, a heading, a quotation, or a
  label like "Note".
- Avoid semicolons. They're acceptable to join two closely related independent clauses, before a
  conjunctive adverb, and to separate list items that already contain commas.

## Periods and end punctuation

- End every complete sentence with a period, except questions, headings, and some list items.
- One space between sentences.
- Periods and commas go inside quotation marks, unless the quoted thing is a literal in code font:
  "If you enter `escape`, the program crashes."
- A period goes inside parentheses only when the whole sentence is inside them.
- Never end a heading with a period.
- Don't put a URL at the end of a sentence where a period could be mistaken for part of it.
- Avoid exclamation marks entirely in concept and reference material.

## Quotation marks, parentheses, slashes, ellipses

- Straight quotes and apostrophes only. Never curly.
- Quotation marks for the titles of short works and for sections of a larger document, when unlinked.
  Italics for full-length works. Single quotes only inside a nested quotation or in code.
- Avoid parentheses. Readers skip them. Use a comma or a separate sentence. Never write
  "file(s)".
- Avoid slashes outside code, paths, and URLs. Write "developed or hosted", not "developed/hosted".
  Never "3/15/2024", "c/o", or "w/".
- Avoid ellipses. In quoted text, use three separate periods with a space either side, never the
  single ellipsis character. Drop the trailing ellipsis when naming a UI command: the "Save…" button
  is just **Save**.

## Abbreviations and acronyms

- Spell out on first use with the abbreviation in parentheses, both italicized:
  _Border Gateway Protocol_ (_BGP_). Use the abbreviation alone after that.
- Only capitalize the spelled-out form if it's a proper noun: "data manipulation language (DML)".
- No periods in acronyms or initialisms (API, HTML, CIA) or in country and state abbreviations
  (US, CA, UK). Periods after shortened words (Dr., min.).
- Words that became words need no expansion or periods: app, sync, demo.
- Pluralize with a plain s: APIs, PDFs, SKUs. Add es after s, sh, ch, or x: OSes.
  Never use an apostrophe to pluralize.
- Don't use an abbreviation as a verb: "Use SSH to connect", not "ssh into the server".
- "a" or "an" follows pronunciation, not spelling: "a SQL query", "an SAP system".
- These rarely need spelling out: AI, API, DVD, HTML, PC, PDF, RAM, REST, URL, USB, XML.

## Capitalization

- Standard American English. Don't capitalize for emphasis or importance.
- Sentence case for headings, titles, table headers, captions, callouts, and list items.
- Sentence case when referring to another document's title, even if that title uses title case.
  Keep a third-party title's own capitalization.
- No all-caps and no camel case except in official names and code.
- Don't let capitalization alone carry meaning ("Pod" vs "pod").
- Lowercase glossary terms unless they're proper nouns.
- In a hyphenated compound, capitalize only the first element: "High-definition video".
- Don't name a casing convention ("camel case"). Describe it and show an example.

## Contractions, articles, prepositions

- Use everyday contractions: you're, don't, there's. Especially the negative ones, because a reader
  scanning can miss a standalone "not".
- No nonstandard or three-word contractions.
- Keep articles, including in headings: "Create a VM instance".
- A preposition at the end of a sentence is fine if it reads better that way. Cut prepositions that
  add nothing, and don't chain them.

## Possessives and plurals

- Singular noun: add 's, even if it ends in s. Plural ending in s: apostrophe only.
  Plural not ending in s: 's.
- Rewrite an awkward possessive rather than writing it.
- Never form a possessive from a code element: "the `wordCount` method's return value", not
  "`wordCount`'s".
- Don't make a product or trademark possessive or plural.
- Don't pluralize a class name; add a noun: "`Intent` objects".
- Don't pluralize an abbreviated unit: "64 GB".
- "one or more tests fail" (plural verb); "more than one instance is" (singular).
- Never "(s)". Pick one form, or write "one or more".

## Numbers

- Spell out zero through nine. Numerals for 10 and up.
- Numerals regardless of size for versions, measurements, technical quantities, percentages, prices,
  page numbers, and maths: "version 3", "6 queries per second", "128 bits", "40%".
- Spell out ordinals: first, fifth. Spell out any number that starts a sentence.
- If numbers in the same sentence sit either side of ten, use numerals for both.
- Decimals rather than fractions. Keep the leading zero: "0.75 inches".
- Comma every three digits left of the decimal point: "1,532,784 bytes".
- Dimensions use a lowercase x with no spaces: "192x192".

## Dates and times

- "January 19, 2017". With a weekday: "Tuesday, April 27, 2021". Month and year take no comma:
  "January 2017". Mid-sentence, close the date with a comma: "the January 19, 2017, release".
- Use ISO 8601 (2017-04-15) only when a numeric date is genuinely needed. Never slashes.
- Abbreviate only when space forces it, and then use three letters throughout: "Mon, Sep 3, 2018".
- 12-hour clock, capitalized AM/PM, one space: "3 PM", "3:45 PM". Drop ":00".
- Ranges take a hyphen with no spaces: "5-10 minutes".
- Avoid time zones. If you need one, spell out the full region name with its offset: "US and Canadian
  Pacific Standard Time (UTC-8)". Better still: "10 AM your local time".
- Date before time: "2017-04-15 at 3 PM".
- Never reference a season. Name the month or quarter.

## Units of measurement

- Nonbreaking space between the number and the unit: `64&nbsp;GB`. No space for currency ($10),
  percentages (65%), or degrees of angle (180°). Temperature: `50&nbsp;°C`. Kelvin: `300&nbsp;K`.
- Repeat the unit across a range, and use "to": "-40 °C to 85 °C".
- Hyphenate multiplied units: "5 vCPU-hours", "40 person-hours".
- "requests per day" rather than a slash. Abbreviated rates are fine where established: Gbps, MBps.
- Match the byte system the technology uses: decimal kB/MB/GB, or binary KiB/MiB/GiB.
- Name the currency when it could be ambiguous: US$10.
- Lowercase k for thousands, no space: "55k operations".

## Maths and phone numbers

- HTML entities for operators (`&minus;`, `&times;`, `&ne;`), with nonbreaking spaces around them.
  Never italicize an operator. Never use `*` for multiplication or `^` for an exponent. Use `<sup>`.
- Italicize variables. Keep short expressions inline; put long equations on their own line.
- Use notation when it's clearer than words: "_a_ > _b_".
- Phone numbers: only 800-555-0100 through 800-555-0199. Nonbreaking hyphens (`&#8209;`) between
  the parts. Country code after a plus sign with no space: +1‑415‑555‑0132. Spell out "extension".
