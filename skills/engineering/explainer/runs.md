# Helper runs

A helper run does one job in its own context and writes a result file. Each run starts as the `scratch-agents` skill says, at the role named here, in the build folder. A run is done when you have read its result file and checked it against its brief.

- **Evidence run:** reading that step 2 sends out, such as tracing a flow through a repo. The `explainer evidence` role, briefed to use the `how` skill for what code does or the `why` skill for why. The brief names the repo's path, the question, the evidence that would settle it, and the result file.
- **Diagram run:** draws one diagram into a file its brief names. The `explainer diagram` role. The brief carries the figure's question and caption, its row and its level from the `diagrams` skill's table, its parts from the source, the page's key of marks, its SVG id prefix, the design plan's palette and typefaces, and the paths of [figures.md](figures.md) and the `diagrams` skill's `drawing.md`.
- **Cold read:** as [cold-read.md](cold-read.md) says.
