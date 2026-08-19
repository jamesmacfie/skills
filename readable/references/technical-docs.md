# Technical documentation

Source pages under https://developers.google.com/style: /procedures, /ui-elements, /code-in-text,
/code-samples, /code-syntax, /placeholders, /filenames, /examples, /api-reference-comments,
/prescriptive-documentation, /other-sources, /trademarks.

## Procedures

- Number the steps. Lowercase letters for substeps, Roman numerals below that. A single-step
  procedure is a bullet, not a "1".
- Start each step with an imperative verb: "Clone the repository", not "You need to clone".
- State the location before the action: "In Google Docs, click…".
- State the goal before the action: "To start a new document, click…".
- One decision per step. Complete sentences, parallel structure.
- Say what the reader needs — hardware, software, permissions — before the first step.
- Say what happens as a result of a step when it isn't obvious.
- Chain a menu path with `>`: "Click **File > New > Document**".
- Optional steps open with "Optional: ". Not "(optional)".
- Don't repeat a procedure you've already written; link to it.
- When there are several ways to do something, document the simplest and most accessible one.
- Never "please", never a direction like "above" or "below", and don't lean on keyboard shortcuts.
- Don't write "run the following command" — say what the command does.
- Give the intro sentence real content beyond restating the heading, and end it with a colon.

## Prescriptive language

Required: "must", or a plain imperative. Recommended: "We recommend" — "should" only for a widely
recognized best practice. Optional: "can". Certain outcome: state it plainly. Possible outcome:
"might" or "can". Never "should be" to describe a state that just is; say "The server sets the value
to `true`". In sample commands, give the arguments for the common case and link the full reference.

## UI elements

- Bold every UI label. Follow the label's own capitalization, except that all-caps or inconsistent
  labels become sentence case. Code font only if the string also qualifies as code.
- Describe the goal, not the widget, where you can: "Refresh the page" beats "Click **Refresh**".
- Terms: *window* for a desktop app window, *page* for a web page or console subpage, *dialog* for a
  small detached window, *pane* or *panel* for a region inside a window, *section* for a labelled
  group of controls, *command* for a menu entry, *field* or *text box* for text input, *list* for a
  list box.
- Checkboxes are **selected** and **cleared** — never checked, unchecked, or deselected.
- Prepositions: **in** a dialog, field, list, menu, pane, or window; **on** a page, tab, or toolbar.
- Verbs to use: click, choose, drag, enable, enter, type, go to, hold the pointer over, press,
  select, tap, turn on, turn off.
- Don't turn a UI label into a verb ("**Name** the account"). Don't use slang for a control
  ("hamburger icon"). Don't use directional language.
- Keys: spell modifiers out and capitalize the letter — "Control+S", not "Ctrl+s". Give the macOS
  equivalent in parentheses. Use `<kbd>` or monospace.
- Name an icon alongside its glyph. If an icon has no tooltip, that's an accessibility bug worth
  filing.

## Code in text

Code font goes on: attribute names and values, class names, command names and their output, data
types, database column names, DNS record types, element names (`script`, without angle brackets),
environment variables, filenames and paths, HTTP headers, status codes and verbs, IAM roles, IP
addresses, language keywords, method names with `()`, namespaces, package names, port numbers, and
query parameters. Also a UI value the reader typed earlier (bold and code font together).

No code font for: domain names, product and service names, a URL a reader visits in a browser, or a
conceptual reference ("an activity", "a view").

Conditional: `true` and `false` in code font as literal values, not as evaluations. The command
(`gcc`) in code font, the project name in regular font. An email address in code font only when
it's literal input or output.

Grammar with code:

- Don't inflect a code element. "The `ADDRESS` constant's value", not "`ADDRESS`'s value".
- Don't use a code element as a verb. "Send a `POST` request", not "`POST` the data".
- Don't wrap code in quotation marks unless the quotes are part of the code.
- Qualify it with a noun: "the `example.yaml` file", not just "`example.yaml`".

## Code samples

- Spaces, not tabs. Follow the language's own style guide; two spaces is the usual default.
- Wrap at 80 characters.
- Introduce every sample with a sentence — colon if the sample follows immediately, period if
  something intervenes.
- Mark an omission with a language-appropriate comment (`# Several lines are omitted here.`), never
  an ellipsis. Don't offer click-to-copy on a block with omissions.

## Command-line syntax

- Code block. Break past 80 characters, indent continuations four spaces, and end each continued
  line with `\` (or `^` on Windows).
- `[OPTIONAL]` in square brackets. `{THIS|OR|THAT}` in braces with pipes. `[FLAG...]` for a repeating
  argument, ellipsis with no space.
- Strip all of that syntax out of a click-to-copy example: give the common case with only the
  arguments it needs, and link the full command reference.
- Prefix input lines with `$`. Be consistent within a document. Add an environment hint (`shell@`)
  when the reader switches context. Don't include the directory path in the prompt.
- Show output only when it earns its place. Introduce it with "The output is similar to the
  following:" and put it in its own code block. Mark omitted output lines with `...` on its own line.
- gcloud terminology: "flag" for an option, "command" for an action, "argument" for a value.

## Placeholders

- Uppercase with underscores: `API_NAME`, `METHOD_NAME`. Not `api_name`, `apiName`, or `API-name`.
- No possessives — never `MY_API_NAME` or `YOUR_API_NAME`.
- Descriptive names; no strings of x's unless that's the convention (HTTP status codes).
- HTML: `<code><var>PLACEHOLDER</var></code>` inside code, `<var>PLACEHOLDER</var>` in prose.
  Markdown: `` *`PLACEHOLDER`* ``. Inside a fenced block, plain text.
- Keep brackets and braces outside the `<var>` tag.
- One placeholder: "Replace `PLACEHOLDER` with …". Several: "Replace the following:" and then a list,
  each entry `` `PLACEHOLDER`: `` followed by a lowercase description.

## Filenames

Lowercase, hyphen-separated, ASCII alphanumeric: `query-data.html`, `build-script.sh`. No generic
names like `document1.html`. Match an existing directory's convention if changing everything isn't
practical.

In prose: code font, with the word "file" after it — "the `build.sh` file". Preserve the exact
spelling. Name the format, not the extension: "a PNG file", not "a .png file"; "a Markdown file", not
"a .md file".

## Example names, domains, and addresses

- Domains: `example.com`, `example.org`, `example.net`. Google-owned alternatives include
  `altostrat.com`, `examplepetstore.com`, `cymbalgroup.com`.
- Email: an approved name at an approved domain — `dana@example.com`.
- Person names, gender-neutral by preference: Alex, Amal, Ariel, Bola, Charlie, Cruz, Dana, Dani,
  Hao, Ira, Izumi, Jie, Kai, Kalani, Kim, Kiran, Lee, Lucian, Luka, Mahan, Noam, Nur, Quinn, Raha,
  Rosario, Sasha, Tal, Taylor, Tristan, Yuri. Add a surname initial when you need one: "Quinn N.".
  Use they/them. Vary names, ages, and locations, and don't lean on stereotypes.
- Companies: "Example Organization", and variants like "Startup Example Organization".
- Phone numbers: 800-555-0100 through 800-555-0199 only.
- IPv4: 192.0.2.0/24, 198.51.100.0/24, 203.0.113.0/24. IPv6: 2001:db8::/32.
- Project names: descriptive and meaningful. Never foo, bar, or baz. Number them when you need
  several: production-1, production-2.
- Never a real person, phone number, address, or IP address.

## API reference comments

Document every class, interface, struct, constant, field, enum, typedef, and method, plus every
parameter, return value, and exception.

- Class description: open with what it's for, without repeating the class name. Never "This class
  will…".
- Method description: third person present tense. "Gets the…", "Sets the…", "Checks whether…",
  "Deletes the…", "Registers…", "Called by…", "Creates a…". Not the imperative.
- Parameters: capitalized, ending in a period. Non-boolean starts with "The" or "A". A boolean that
  triggers an action: "If true, …. If false, ….". A boolean state: "True if …; false otherwise."
  Defaults as "Default: value".
- Return values: brief. "The …" or "True if …; false otherwise."
- Exceptions: "If condition…" when the tool inserts "Throws", otherwise "Thrown when condition…".
- Deprecations: name the replacement in the first sentence, give the version, say why, and point at
  the migration path.
- Write "for example", never "e.g." — truncation can cut it off mid-phrase.

## Third-party content

Paraphrase and link; don't reproduce. That covers documentation, websites, books, blogs, videos,
images, podcasts, code, logos, and speech, and it includes dictionaries and Wikipedia. Open source
and GitHub content is not automatically reusable — check the license, and attribute where it requires
it.

Trademarks: follow the owner's guidelines, use the mark as a modifier rather than a standalone noun,
never as a verb, and never pluralized, possessive, or otherwise altered.
