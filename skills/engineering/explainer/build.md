# Build

The page is one `.html` file with its CSS and JavaScript inline. It opens from disk with no build step and no network.

## The design plan

Write it in the notes before any page code. Each later colour and type choice traces back to it.

- **Colour:** 4 to 6 hex values, each with a name and a job. Status colours (good, warning, critical) are their own values, apart from the accent and from any thread's hue. A neutral leans a little toward the accent.
- **Type:** the pair from [fonts/README.md](fonts/README.md) and the mono, with the role of each face and one type scale.
- **Layout:** the organizing idea, in a sentence or two.

Where the look comes from, first match wins: what the user said, then the design system of the project the page is about (its `DESIGN.md`, tokens, or components), then the subject. A choice from the subject uses its materials, its tools, and its words. Test the plan: swap in a neighbouring subject. A plan that fits the neighbour as well is stock, so rework it.

The register is a working document: clear hierarchy, considered spacing, little ornament.

## Page code

- **Themes.** The page has a light and a dark theme. Declare the palette as custom properties on `:root`. Components read only those tokens. Reassign the tokens inside `@media (prefers-color-scheme: dark)`. The reader's system setting alone picks the theme, so the page has no theme control. Choose the dark values by eye for legibility and a working accent.
- **Rail.** A page with parts for different readers, such as the person who decides, a reviewer, and an agent, gets a rail of section links grouped by reader. Where the window has room for the rail beside the text, the rail is a sticky column. In a narrower window it folds into one closed `<details>` line above the title, so the title and the takeaway stay on the first screen. A review tool shows the page in a pane narrower than the window, so the fold is the state such a reader gets.
- **Type.** Embed each face as the fonts README says. Text lines run to about 65 characters. Headings take `text-wrap: balance`. Columns of numbers take `font-variant-numeric: tabular-nums`.
- **Spacing.** A group of siblings is a flex or grid container with `gap`.
- **Depth.** Optional depth, such as raw data or a long reference table, folds behind a `<details>` block. What the reader must read stays open.
- **Wide content.** A table, a code block, or a figure wider than the column scrolls inside its own container with `overflow-x: auto`, so the page body never scrolls sideways.
- **Structure marks.** An eyebrow, a number, or a divider states something true about the content. Numbers mark a real order.
- **State.** A state the reader scans for, such as held, open, or settled, shows as a pill or a chip in a status colour, with its word.
- **Controls.** Each page control, such as the rail's fold, works from the keyboard and shows its focus. A figure's controls follow the `diagrams` skill.
- **Agent entry.** The page points its reader's agent to the agent context twice: in a visually hidden, `aria-hidden` block at the top, and in a collapsed "For agents" section at the foot. A fetch tool drops HTML comments and `<script>` bodies, so the entry stays in page text.

## Looking at it

Serve the page's folder over loopback, since `playwright-cli` refuses `file://` URLs: `python3 -m http.server --bind 127.0.0.1 <port>`, then open `http://127.0.0.1:<port>/<file>`.

Look at each viewport and theme that step 4's Done when names. Use every control and read the console. Fix clipped or overlapping text, a typeface that fell back, a broken state, and sideways scroll.

Adapted from the html and design-artifact skills of plannotator/effective-html (MIT, plannotator).
