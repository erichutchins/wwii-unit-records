# USS Haynsworth (DD-700), 6 April 1945

The kamikaze hit on USS Haynsworth, on picket station 12 miles from Task Group 58.3's carriers off Okinawa, on the
first day of Japan's mass kamikaze offensive. Her own reports beside the other ships of the group and
the Japanese records of the planes sent against them. Hand-edited; every row cites its page in `ref`.

- `timeline.csv`: every timed entry, US and Japanese. `date`, `time` (as recorded; `placed` says when a time was placed
  by sequence, not recorded), `side` (`us`, `jp`), `actor`, `kind`, `text` (the record's words in quotes, abridged with
  `...`), `source` (in words), `ref` (the page), `pos` (a `positions.csv` id), `step` (the part of the story it belongs to).
- `positions.csv`: fixes, and positions given as bearing and distance from another (`from`, `brg`, `nm`), which a page
  resolves. `basis` says `fix`, `reported`, `derived`, `assumed` or `approx`; `hand-placed` rows are reference points
  placed on a modern map.
- `claims.csv`: the evidence board. Each disputed question (when was she hit, what hit her, who flew it), each answer,
  and what kind of evidence it is (`weight`: `record`, `photo`, `recollection`, `inference`).

The ship's track for April 1945 is in [`ships/dd-700-haynsworth/`](../../ships/dd-700-haynsworth/README.md). The crew
lists stay out of these records (see the kit's rules on people); the casualty count and the Report of Casualties page
are cited instead.
