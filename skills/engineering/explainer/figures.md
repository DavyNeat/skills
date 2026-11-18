# Figures

A figure is anything the reader looks at: a diagram, a screenshot, a real record, a table, or a code view. It sits in the page as a `<figure>` whose `<figcaption>` states the one claim it shows, such as "The webhook writes before the sync reads, so the sync sees the new status."

## Which figures

SKILL.md's step 3 lists the frames. This file says what each frame is made of. For each diagram, the `diagrams` skill decides its question, its type, and how much it holds.

- **The whole in one picture.** The first frame shows the whole subject at the level a newcomer needs, with groups folded into black boxes as the `diagrams` skill says. A later frame that opens a box draws the parts outside it faint. On a hub, the first frame is the map of the pages in reading order. On a decision brief, it is the calls and which call each depends on.
- **A table is a frame** when the reader compares things: options against what each means for each person, today against the proposal, or cases against outcomes.

- **Screenshots.** Where the subject has screens the reader has not seen, take real screenshots and caption each with what to look at. Replace or blur any personal data before the shot.
- **Code beside it.** When the reader also judges code shape, put a code view beside the drawing: pseudocode, a call tree, a file tree, or a `diff` of one of these.
- **The difference, when comparing.** Draw both designs on one layout with the same worked case, and mark the one edge each adds or removes. In a table of today against the proposal, mark each cell that changes.

## Coding across the page

These hold across every diagram on a page, so the reader learns the marks once:

- Each kind of part has its own shape: a person, a store, a queue, a service, a boundary. A person is drawn as a person.
- Each kind of mechanism has its own colour, line style, and arrowhead: such as a read, a write, an event, a direct call, a timer, a webhook, a person acting.
- One key per page states the marks, in the order a reader traces a chain: what triggers, then what reacts. It replaces each diagram's own key.
- A part keeps one colour on every figure.
- A thread the page follows side by side with others, such as a lane or a track, keeps one hue on every figure, card, table, and rail link.
- After the first walk of a case, later walks draw the known path faint and the new wiring strong.
- A diagram the user approved keeps its shape on a rebuild.

## Drawing

Draw each diagram as the `diagrams` skill says for a page, with the design plan's palette and typefaces.

- Prefix every SVG id with the figure's name, such as `step2-write`: all figures on a page share one id space.
- At 390 px wide, every label renders at 12 px or larger. A diagram too wide for that is redrawn top to bottom.
- A figure takes interaction, such as stepping through stages, picking a case, or a switch between designs, where the `diagrams` skill says it helps. Its still frame shows the caption's claim, because a reader of the caption walk, a print, or a Notion copy sees only that frame. The text of every other state goes into the agent context.
- A figure that runs the reader's own input, such as a simulation, is plain script in the page. It opens at the moment the problem shows, is labelled illustrative, and shows its parameters.
