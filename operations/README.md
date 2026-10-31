# Operations

The campaigns and operations the units' stations sit inside, so a page can show where a unit was against what the war
was doing there, and what it meant. Context, not participation: a unit with stations inside an operation's area and
dates is a lead until its own records say it took part.

**Hand-edited Markdown, one file per operation**: `<theater>/<id>.md`, the theater itself `<theater>/index.md`.
`operations.json` is generated from them by `tools/build_operations.py`; never edit it.

## A file

```markdown
---
name: The Tunisian campaign          # as the official histories name it
short: Tunisia                       # short enough for a timeline bar or a map
kind: campaign                       # theater, operation, campaign or phase
parent: mediterranean                # the file it belongs under
from: 1942-11-12
to: 1943-05-13                       # empty for an open end; the note says why
area: [7.5, 32, 11.5, 37.6]          # west, south, east, north, in degrees
area_precision: region               # region: drawn by hand around the fighting
ref: [howe-nwa/35/p675, howe-nwa/34/p665]   # the pages the dates come from (forms in ../SOURCES.yml)
note: >-
  Which page gives which date, and what's ours (a grouping, a hand-drawn area).
---

## What it meant

By May 1943, "with the southern side of the Sicilian straits in Allied possession, ..." [[cite:howe-nwa/35/p676]]

> An aside: a qualification, set smaller on the page. [[cite:howe-nwa/35/p675]]
```

- Headings (`##`) are what the page shows: usually *What it was for*, *What it meant*, or *What happened*.
- A paragraph is one statement and ends with its citation, `[[cite:...]]`. Quotes are exact and typed as plain
  quotation marks; anything outside them is our summary of the same page.
- Links are written by name: `[[op:husky|the invasion of Sicily]]`, `[[ship:bang]]`, `[[unit:106aaa-d@1944-08-15]]`,
  `[[page:algiers]]`. People's names never appear here; a family links its people from its own files.

After editing: `uv run tools/build_operations.py`. It names any citation or link that doesn't resolve, a paragraph
without a citation, or a date out of order, and writes nothing until they're fixed. `check_sources.py` runs the same
checks.
