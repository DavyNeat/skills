# Cold read

A cold reader gets the page and the reader's profile (the reader from step 1's notes), and nothing else. It shows where the page leans on what only you know.

Copy the reader from the notes to `COLD-<n>-profile.md` beside the page; `n` counts cold reads in the effort, from 1.

Save the **reader's copy** of the page as `COLD-<n>-page.md`: the page's text in reading order, each figure replaced by its caption and its text alternative, with no fonts, styles, or scripts. Take one screenshot of each figure's still frame, as `COLD-<n>-<figure>.png`. The built file is mostly encoded fonts and markup, which a helper cannot read as a page.

Start one helper as the `scratch-agents` skill says, in its `explainer cold read` role, with this brief:

```text
You are the reader the profile describes. These files are everything that reader has: <COLD-n-page.md path>, the screenshots <COLD-n-*.png paths>, and <COLD-n-profile.md path>. Read those files and nothing else, no other file, note, repo, or search. Change no file except <COLD-n.md path>.
Write to <COLD-n.md path>, in your own words and nothing else:
1. In two or three sentences, what this page wants its reader to understand.
2. What the reader is asked to decide or do.
3. Every term, system, or premise the page used before it explained it, for this reader, each with the sentence where it first appears. Leave out a reference that names the section or page that explains it. Write "none" when there are none.
```

For several pages, give the reader's copy of the hub and of each page, in reading order.

Read `COLD-<n>.md` against your takeaway and asks. Each item in its list is a place to teach earlier, to add a clause, or to cut.
