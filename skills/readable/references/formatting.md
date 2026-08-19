# Structure and formatting

Source pages under https://developers.google.com/style: /text-formatting, /headings,
/headings-targets, /lists, /tables, /notices, /images, /footnotes, /cross-references, /accessibility,
/paragraph-structure, /italics-terms, /format-examples.

## Text formatting

| Item | Format |
| --- | --- |
| UI element names, run-in headings, the opening word of a notice | Bold |
| A term you're introducing and defining, on first mention | Italics |
| A word, phrase, or letter discussed as itself | Italics |
| Semantic emphasis | Italics (`<em>`) |
| Book, film, and series titles | Italics |
| Mathematical and version variables | Italics |
| Code, filenames, paths, class and method names, HTTP status codes, console output | Code font |
| Placeholders | Code font, uppercase with underscores |
| Code blocks | Fenced block or `<pre>` |
| Article, episode, and section titles, when unlinked | Quotation marks |
| Headings, titles, navigation, captions, table headers, list items | Sentence case |

Don't underline anything but links. Don't override fonts. Don't use "&" as a conjunction. Don't use
bold or quotation marks where italics are called for.

## Headings and titles

- Sentence case. No trailing period. Keep punctuation simple. Complex punctuation means the heading
  isn't clear yet.
- Task headings take the bare imperative: "Create an instance". Not "Creating an instance".
- Concept headings are noun phrases: "Migration to Google Cloud". Avoid an -ing word first;
  established gerunds like "Billing" and "Pricing" are the exception.
- Optional sections: "Optional: Customize your alias". Not "(optional)".
- One h1 per page. Don't skip levels. Don't leave a heading with no content under it.
- Don't number sections, don't put a link in a heading, and don't use code alone as a heading. Add a
  descriptive noun.
- Make headings descriptive enough to distinguish them from each other; readers navigate by them.
- Introduce a group of subsections with "The following sections describe…". Don't write
  "this section".
- Define an abbreviation in the first paragraph below the heading, not in the heading itself.

### Headings as link targets

Lowercase, hyphen-separated anchor IDs: `introduction-to-everything`. In Markdown, append
`{: #anchor-id }`. Add a custom anchor to anything you link to often, so the link survives a heading
rewrite. When you rewrite a heading, keep the old anchor. Don't change an existing anchor unless the
wording is a problem, and if you do, update every inbound link.

## Lists

- Numbered when order matters. Bulleted when it doesn't. Description lists for term-and-definition
  pairs. Run-in headings (a bold term, then its description) when space is tight.
- Introduce with a complete sentence: a colon if the list follows immediately, a period if something
  comes between. Never let list items complete a sentence fragment.
- Keep every item in the same syntactic shape.
- Capitalize each item, unless case is significant, and end it with a period, unless it's a single
  word, has no verb, is entirely code, or is link text.
- In a description list, no period after the term; period after the description.
- Nested numbered lists use lowercase letters, then Roman numerals.
- Never write a one-item list.

## Tables

- Use a table when each item has three or more related pieces of data. Two paired values are a
  description list. A single value per item is a list.
- Never for layout, never for code, and never split a one-dimensional list into columns.
  No single-row or single-column tables. Avoid a table in the middle of a numbered procedure.
- Introduce it with a complete sentence: colon if the table follows immediately, otherwise a period.
- Sentence case headers, no ending punctuation. Mark only the first row or column as headers, with
  `<th>` and a `scope` attribute.
- Never merge cells with `colspan` or `rowspan`. No custom styling. Use CSS that adapts to the
  viewport. Multi-paragraph cells use `<p>`, not `<br>`.
- Sort rows logically or alphabetically. Split a table that's grown unwieldy.
- If a page has several tables, caption them "**Table 2.** Description." and refer to them by number
  rather than linking.

## Notes and notices

Four kinds, in ascending severity:

- **Note**. Useful but skippable. Never for a prerequisite, a cross-reference, or anything the
  reader actually needs.
- **Caution**. Proceed carefully; care now avoids a problem later.
- **Warning**. Don't do this. Reserve it for irreversible actions, data loss, security exposure, or
  financial harm.
- **Success**. Only in interactive content, never in static docs.

Write the sentence as body text first, then decide whether a notice earns its place. Use them
sparingly; a page of notices has no notices. Never stack two in a row. Reorganize instead. Don't
turn a procedural step or an expected result into a notice.

## Images and figures

- Only for a visual UI element or a diagram that words can't carry. Never a picture of code, text,
  or terminal output.
- SVG for diagrams, PNG if you must. MP4 for motion, not animated GIF. Consistent OS and visual
  style across screenshots. Crop to what matters. Cover any personal data with a solid 100% opaque
  block. Descriptive filenames. `srcset` for a 2x version.
- Alt text: 155 characters or fewer, a full sentence or noun phrase, punctuated so a screen reader
  pauses. No "Image of". Empty `alt=""` for purely decorative images. Don't introduce a diagram in
  its alt text.
- Never put new information in an image alone; the surrounding text must carry it too.
- Captions are optional: "**Figure 3.** A complete sentence." Refer to figures by number, lowercase
  except at the start of a sentence. Don't link to a figure on the same page.
- Text inside an image stays short, in sentence case. Use numbered callouts and explain them in the
  text.
- Don't center images, don't hand-position them, don't exceed the column width, and never put an
  `img` inside a `p`.

## Links and cross-references

- Every link is a chance for the reader to leave. Prefer explaining the thing on the page.
- Link text is the target's title, or a clear description of it, with the important words first.
  Never "click here", "this document", "read this", or a raw URL.
- Introduce with "For more information, see …". Say "see", not "on". Add an "about…" clause when the
  reason isn't obvious.
- Link once, in the most useful place, unless the page is long or has several entry points.
- Punctuation goes outside the link tag. Don't wrap link text in quotation marks.
- Don't force a new tab. If you do, say "(opens in a new tab)".
- Say when a link downloads a file, opens a mail client, jumps within the page, or leaves the site.
  Don't rely on an external-link icon to say it.
- Put a character between adjacent links so a screen reader doesn't run them together.

## Paragraphs

One idea per paragraph. Past 5 or 6 sentences, it's carrying too much, so split it. Short sentences
rather than long ones. Key information first. A one-sentence paragraph is fine. Left-align only, never centered or
justified. Never force a line break inside a sentence.

## Introducing examples

- At the end of a sentence, lead in with a comma: "Choose a strong encryption algorithm, such as
  AES-256".
- Mid-sentence and short: "Enter a six-digit hex number (for example, `228B22`), and then click OK".
- Mid-sentence and long: rewrite, or move the example to the end.
- Longer than that: give it its own sentence starting with "For example".
- Never "e.g."; never combine "for example" or "such as" with a semicolon.

## Accessibility

- Never rely on color, size, or position alone. Add a text cue.
- Refer to a control by its label, not its appearance: "Click **Save**", not "click the blue button".
- No directional language, such as above, below, or left-side. Use "the following" and "the preceding".
- Follow the heading hierarchy; style with CSS rather than picking a level for its looks.
- Semantic HTML: `<em>`, `<strong>`, `<button>`, `<label>`, `<cite>` for a standalone work's title.
  `<br>` only for a real content line break, never for spacing.
- Every input gets a `<label>`, placed outside the field. Error messages state the fix:
  "Name is a required field".
- 4.5:1 contrast minimum. Never `display:none` or `visibility:hidden` for content. Never a
  mouseover-only interaction. Add focus and blur. Keep CSS order matching DOM order.
- Everything reachable by keyboard. Caption all audio and video. No flickering or flashing.
- Avoid camel case and all-caps: some screen readers spell them out letter by letter.
- Test the page with color, sound, images, and punctuation removed. It should still make sense.

## Footnotes

Avoid them. They're bad for screen readers and for translation. Use a cross-reference, a note, or
parentheses instead. If you truly need one, `<sup>1</sup>` and put it at the bottom of the page.

## Markdown or HTML

Either is fine. Markdown reads better in source; HTML is more expressive when you need semantic
precision or a special character inside code. Follow whatever your team already uses. HTML details:
lowercase elements and attributes, two-space indentation, no tabs, no trailing spaces, 80-character
lines, and keep the optional elements rather than omitting them.
