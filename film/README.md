# Film

Film of the places and days in these records: what a station, a harbour or a raid looked like, from the
archives that hold the film. Each row is one film or newsreel story; its `source` is the archive's own catalogue
item or its own upload. Found with the kit's `tools/film.py`. 23 films so far.

- `clips.csv`: the films (columns below).
- `channels.yml`: the YouTube channels whose uploads count. `archive`: the archive's own channel, cited as
  `youtube:<id>` with the archive's number in `archive_id`. `finding-aid`: a re-uploader of public-domain
  government film, never cited; the film is traced to the archive's catalogue and cited there. Nothing else is
  a source, whatever its upload date.

How a clip is checked: read the archive's own shot list or shot card (the cameraman's card for Signal Corps film),
not the upload's title or a modern caption; take the date from the catalogue or the card and say which (`date_basis`);
look at the film where it matters. A film of a place on a unit's date is a lead about what the unit saw, not a
picture of the unit, unless the card or the film names it.

The step-by-step search (which archive first, the tools' commands, what to do at a bot check) is the kit's skill
`find-film` (`.claude/skills/find-film/SKILL.md`). This file keeps the rules a row must meet and the columns.

## What makes a row

- The film's own words: its shot list or shot card, or (for an archive's upload) the story's shot list in the
  description. Never the upload's title, a "Today in history" caption or an automatic caption, and never a re-uploader's
  title (a finding aid is traced to the archive's catalogue and cited there).
- A date with its basis. The card's or the catalogue's date is a date; an upload's date is not. If the card's date
  disagrees with its scenes (111-ADC-254 is dated 10 Aug 1943 but shows the aftermath of Salerno), enter nothing until the
  film itself settles it, and log it. An undated card (111-ADC-481) is not entered; log it with what would date it.
- A place with its precision, and `relevance`:
  - `place-date`: a unit's records put it at that place (or its immediate area) within the film's date or month. Say in
    `note` which unit's station and which dates.
  - `context`: the place at another time, or the operation the unit took part in. Say how far off, and that it is not the unit.
  - A compilation that mixes stock (a "Movietone Moment", a "Cut story" with London, Malta and the landings in one reel, a
    later programme such as Pathé's "Time To Remember" that re-cuts wartime film) is read shot by shot, and only the
    shots that name the place are used; if none do, it isn't a row.
- Nothing about a relative: a clip names units and places, as the rest of the records do.
- A row passes the kit's `tools/check_sources.py`, which reads this file's `source` column.

## clips.csv columns

| Column | Meaning |
|---|---|
| `clip` | A short id |
| `date` | The film's date, as precise as its source gives it (`1943`, `1943-07`, `1943-08-03`) |
| `date_basis` | `catalogue` (the archive's production date), `shot card`, `stated-in-film` (the narration or a title), `inferred` (the note says from what) |
| `place`, `lat`, `lon`, `place_precision` | Where it was filmed, to the precision of the source (`town`, `harbour`, `region`) |
| `source` | `nara-film:<catalogue ID>` or `youtube:<id>` (`../SOURCES.yml`) |
| `archive_id` | The archive's own number: a NARA film number (`428-NPC-1084`, `111-ADC-2134`), Pathé's film ID, Movietone's story number |
| `youtube` | A YouTube copy, if any (a finding aid unless `source` is that upload) |
| `start` | Seconds into the film or upload where the place begins, when known |
| `shows` | What it shows, from the shot list or the narration (abridged; the source's words in quotes) |
| `relevance` | `place-date` (the place on or near a unit's date in these records) or `context` |
| `note` | Which unit's station it meets, and what it doesn't show |
| `video` | The archive's own copy of the film (an MP4 URL), checked to answer as `video/mp4`, for a page to play; blank if it isn't online |
