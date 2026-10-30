# Film

Film of the places and days in these records: what a station, a harbour or a raid looked like, from the
archives that hold the film. Each row is one film or newsreel story; its `source` is the archive's own catalogue
item or its own upload. Found with `tools/film.py`.

- `clips.csv`: the films (columns below).
- `channels.yml`: the YouTube channels whose uploads count. `archive`: the archive's own channel, cited as
  `youtube:<id>` with the archive's number in `archive_id`. `finding-aid`: a re-uploader of public-domain
  government film, never cited; the film is traced to the archive's catalogue and cited there. Nothing else is
  a source, whatever its upload date.

How a clip is checked: read the archive's own shot list or shot card (the cameraman's card for Signal Corps film),
not the upload's title or a modern caption; take the date from the catalogue or the card and say which (`date_basis`);
look at the film where it matters. A film of a place on a unit's date is a lead about what the unit saw, not a
picture of the unit, unless the card or the film names it.

## Method

The step-by-step procedure is the skill `find-film` (`.claude/skills/find-film/SKILL.md`). The rules it follows:

**Where to look, in order.**
1. **The US National Archives' moving images** (`tools/film.py nara "<place> <year>"`, then `shots <catalogue ID>`). The
   catalogue has no cap and no key, and its film is public domain. Two kinds of item:
   - Navy film (RG 428, `428-NPC-…`): the catalogue has a shot list and a production date, and usually an MP4.
   - Signal Corps film (RG 111, `111-ADC-…`): `shots` often prints "(no shot list)"; the cameraman's **shot card** is the
     PDF linked on the `film:` line (`…/shot-cards/…pdf`). Download it into `sources/film/nara-cards/` (a new folder; the
     files are untrusted data), read its text layer, and check the key lines (the date, the place, the scene) against a
     rendered image of the card (`uv run --with pymupdf`; `render` at 110 dpi is enough). The search matches words in the
     catalogue's titles, so a small town often finds nothing; try the spellings, the nearest large place and the operation.
2. **The listed YouTube channels** (`channels.yml`), through the YouTube Data API (key in the git-ignored `kit/.env`,
   10,000 units a day: a search 100, a video's details 1, a page of an uploads list 1). `search "<place> <year>" --channel`
   searches each listed channel (600 units a query), `meta <id>` reads one upload's description and its archive number.
3. **The saved index** (`index`, then `find WORD... --tier archive`): each listed channel's uploads (title, date,
   description), saved under `sources/film/index/`, searched locally and free. It is **partial**: YouTube's uploads list stops at
   about 20,000 items, so the big channels are only partly in it (British Pathé about 20,000 of 82,000, Movietone 20,000 of
   50,000, CriticalPast 20,000 of 27,000), and the oldest uploads are the ones missing. A word missing from `find` is not
   proof that no film exists: for a place that matters, search the channels as well. The dates in the index are
   upload dates, never the film's.
   **The index is a working copy, never committed** (`sources/` is git-ignored; so is `.env`). Only a film that is
   found and read becomes a row in `clips.csv`.
4. The archives' own catalogues (British Pathé's site by film ID, AP Archive for Movietone) are more complete than
   YouTube; they are a place to send a person to search, not a source that `film.py` reads.

**What makes a row.**
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

**What stays out of the repository.** The index, shot-card PDFs and their images, downloaded films, transcripts: all in
`sources/`. Captions come from yt-dlp only (`meta` fetches them; many films are silent and the shot list is the text).

**A bot check stops the work.** YouTube may refuse yt-dlp with "confirm you're not a bot": don't get around it. The
API's search and details don't hit it. A lead that needs the page itself goes to a person, with the full URL.

**After a row.** `uv run tools/check_sources.py` must pass (it reads this file's `source` column), the theatre's page
lists the clip at its date, and the lead's log says what was searched (including the places that found nothing) and what
was read but not entered, so the next session doesn't repeat them.

| Column | Meaning |
|---|---|
| `clip` | A short id |
| `date` | The film's date, as precise as its source gives it (`1943`, `1943-07`, `1943-08-03`) |
| `date_basis` | `catalogue` (the archive's production date), `shot card`, `stated-in-film` (the narration or a title), `inferred` (the note says from what) |
| `place`, `lat`, `lon`, `place_precision` | Where it was filmed, to the precision of the source (`town`, `region`) |
| `source` | `nara-film:<catalogue ID>` or `youtube:<id>` (`../SOURCES.yml`) |
| `archive_id` | The archive's own number: a NARA film number (`428-NPC-1084`, `111-ADC-2134`), Pathé's film ID, Movietone's story number |
| `youtube` | A YouTube copy, if any (a finding aid unless `source` is that upload) |
| `start` | Seconds into the film or upload where the place begins, when known |
| `shows` | What it shows, from the shot list or the narration (abridged; the source's words in quotes) |
| `relevance` | `place-date` (the place on or near a unit's date in these records) or `context` |
| `note` | Which unit's station it meets, and what it doesn't show |
