# Build

The page is one `.html` file with its CSS and JavaScript inline. It opens from disk with no build step and no network.

## The design plan

Write it in the notes before any page code. Each later colour and type choice traces back to it.

- **Colour:** each hex value with a name and a job. First 4 to 6 base values: background, text, a neutral that leans a little toward the accent, and the accent. Then the status values (good, warning, critical). Then one hue for each mechanism kind and each thread.
- **Type:** the pair from [fonts/README.md](fonts/README.md) and the mono, with the role of each face and one type scale.
- **Layout:** the organizing idea, in a sentence or two.

Where the look comes from, first match wins: what the user said, then the design system of the project the page is about (its `DESIGN.md`, tokens, or components), then the subject. A choice from the subject uses its materials, its tools, and its words. Test the plan: swap in a neighbouring subject. A plan that fits the neighbour as well is stock, so rework it. Type always comes from the bundled faces: where a project's design system names a face, take the bundled face nearest to it, and say so in the plan.

The register is a field manual: flat colour and plain marks, with no gradients or shadows.

## Page code

- **Themes.** The page has a light and a dark theme. Declare the palette as custom properties on `:root`. Components read only those tokens. Reassign the tokens inside `@media (prefers-color-scheme: dark)`. The reader's system setting alone picks the theme, so the page has no theme control. Choose the dark values by eye for legibility and a working accent.
- **Rail.** A page with five or more sections gets a rail of section links, in groups under a short heading each, such as one group per reader or per part of the argument. Where the window has room for the rail beside the text, the rail is a sticky column. In a narrower window it folds into one closed `<details>` line above the title, so the title and the takeaway stay on the first screen. A review tool shows the page in a pane narrower than the window, so the fold is the state such a reader gets.
- **Type.** Embed each face as the fonts README says. Text lines run to about 65 characters. Headings take `text-wrap: balance`. Columns of numbers take `font-variant-numeric: tabular-nums`.
- **Depth.** Optional depth, such as raw data or a long reference table, folds behind a `<details>` block. What the reader must read stays open.
- **Wide content.** A table or a code block wider than the column scrolls inside its own container with `overflow-x: auto`, so the page body never scrolls sideways.
- **Structure marks.** An eyebrow, a number, or a divider states something true about the content. Numbers mark a real order.
- **State.** A state the reader scans for, such as held, open, or settled, shows as a pill or a chip in a status colour, with its word.
- **Controls.** Each page control, such as the rail's fold, works from the keyboard and shows its focus. Motion stops under `prefers-reduced-motion`. A figure's controls follow the `diagrams` skill.
- **Agent entry.** The page points its reader's agent to the agent context twice: in a visually hidden, `aria-hidden` block at the top, and in a collapsed "For agents" section at the foot. A fetch tool drops HTML comments and `<script>` bodies, so the entry stays in page text. Each entry links the context by its relative file name, `<page>.context.md`, so the link works from disk and on a host that holds both files in one folder.

## Looking at it

Serve the page's folder over loopback, since `playwright-cli` refuses `file://` URLs: `python3 -m http.server --bind 127.0.0.1 <port>`, then open `http://127.0.0.1:<port>/<file>`.

Look at each viewport and theme that step 4's Done when names. Switch the theme with `playwright-cli set-color-scheme dark`. Through `playwright-cli eval`, read `[...document.fonts].filter(f => f.status === 'loaded').map(f => f.family)`: each family in the design plan is in that list. Use every control and read the console. Fix clipped or overlapping text, a typeface that fell back, a broken state, and sideways scroll.

Adapted from the html and design-artifact skills of plannotator/effective-html (MIT, plannotator).
