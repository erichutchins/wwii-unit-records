# WWII unit records

[![Licence: CC BY 4.0](https://img.shields.io/badge/licence-CC%20BY%204.0-lightgrey)](LICENSE)
[![Made with Claude](https://img.shields.io/badge/made%20with-Claude-D97757)](https://claude.com/claude-code)
[![The pages](https://img.shields.io/badge/see%20it-on%20the%20site-2b6cb0)](https://erichutchins.github.io/wwii-research-kit/)

Where ships and units were in the Second World War, day by day, and what they did, transcribed from the records
they kept at the time: <!--n:boats-->25<!--/n--> US submarines, <!--n:ships-->23<!--/n--> surface ships, <!--n:army_units-->33<!--/n--> Army units and two Seabee battalions, with the
Japanese, German, British, French and Italian records of the same days beside them where those have been found.
Every row cites its source, to the page where there is one.

The pages drawn from this data are [*Charting WWII History*](https://erichutchins.github.io/wwii-research-kit/). This
is the data half of the [WWII research kit](https://github.com/erichutchins/wwii-research-kit), where it is the
`records/` submodule: the kit's tools fetch, check and build these files, and its pages draw them. The data stands on
its own: CSV and YAML, no code needed. Paths below that begin `tools/`, `site/` or `guides/` are the kit's.

## Coverage

A sample, not a survey: the ships and units are the ones one research project followed, and most are followed for
part of their war. [`inventory.yml`](inventory.yml) lists every report and record, found or not, and how far along
each is.

| Subjects | Dates | Record | How complete |
|---|---|---|---|
| <!--n:boats-->25<!--/n--> submarines, <!--n:patrols-->34<!--/n--> war patrols | Sep 1943 – Jun 1945 | War patrol reports | USS BANG's six patrols in full (positions, dives, density layers, attack sheets); <!--n:other_boats-->24<!--/n--> other boats for one or two patrols each, positions and attack sheets |
| <!--n:ships-->23<!--/n--> surface ships | Oct 1942 – Oct 1945 | War diaries | Four ships over months (a battleship, an escort carrier, a destroyer, a destroyer escort; South Dakota's 1943 is mostly untranscribed); nineteen ships of Task Force 58 for 5 to 7 April 1945 only |
| The Pacific submarine force | October 1944 | Its war diary | Where every boat was on 1, 15 and 31 October, and the daily log |
| <!--n:army_units-->33<!--/n--> Army units | 1940 – 1945 | Morning reports, unit histories and journals | Changes of station only; anti-aircraft batteries and a medical detachment from North Africa to Germany, an armored division and three of its battalions, and others for shorter spans ([`army/`](army/README.md)) |
| 2 Naval Construction Battalions | 1942 – 1945 | Muster rolls, history sheets, war diaries | Stations of each battalion and each part of it ([`seabees/`](seabees/README.md)) |
| <!--n:convoys-->11<!--/n--> Japanese convoys | 1944 | Movement tables, escort diaries | Each convoy a followed submarine met: route, ships, cargo |
| <!--n:engagements-->24<!--/n--> engagements | 1943 – 1945 | Both sides' records | <!--n:engagements_pacific-->18<!--/n--> Pacific, <!--n:engagements_mediterranean-->3<!--/n--> Mediterranean, <!--n:engagements_europe-->3<!--/n--> European. The other side's record is entered for some and still to find for others; each `engagement.md` says which |
| Twelfth Army Group's front | 6 Jun 1944 – 7 Jun 1945 | Daily situation maps | The front line on <!--n:front_days-->365<!--/n--> days; the unit symbols on <!--n:symbol_days-->98<!--/n--> ([`fronts/`](fronts/README.md)) |

## Sources and citations

Every transcribed row carries a citation (`page`, `ref`, `source` or `map`) in one of the short forms listed in
[`SOURCES.yml`](SOURCES.yml), which describes each source: what kind it is, whose, where it is held, its terms.

| Record | Held | Cited as |
|---|---|---|
| U.S. submarine war patrol reports | US National Archives (NARA), Record Group 38, series 305243 (microfiche M1752) | `rg38-74802746/p05`: catalog item 74802746, page 5 |
| War diaries of ships and commands | NARA, RG 38, series 4697018 | `rg38-<item>/p<page>` |
| Army morning reports | NARA, RG 64, series 85713825: the microfilm, online for January 1940 – December 1944 | `rg64-<roll>/p<page>` |
| Navy muster rolls | NARA, RG 24, series 594996 | `rg24-<item>/p<page>` |
| Missing Air Crew Reports | NARA, RG 92, series 305256 | `rg92-<item>/p<page>` |
| German army and navy records | NARA, RG 242, microfilm T-312, T-314, T-1022 | `t312-<roll>/f<frame>` |
| Imperial Japanese Navy records | Japan Center for Asian Historical Records (JACAR) | `jacar:C08030140600`, the reference code |
| Twelfth Army Group situation maps | Library of Congress, Geography and Map Division | `loc-12ag/ict21276`, the day's sheet |
| Unit histories, journals, newspapers, British squadron records | The 45th Infantry Division Museum, the Bibliothèque nationale de France, The National Archives (Kew) and others | Each its own form, in `SOURCES.yml` |

The prefix of a National Archives citation is the item's record group as the catalog gives it.
[`citations.json`](citations.json) holds each cited item's catalog title, series and record group, and the kit's
`tools/check_sources.py` fails on a citation that doesn't resolve, a row without one, or a prefix that disagrees with
the catalog.

## How the records were transcribed

- **From the scan, never from OCR.** Every value was read on the page image. OCR text is used only to find pages.
- **As typed.** Dates, times, zone letters, positions and place names are recorded exactly as the record has them,
  misspellings included; `?` stands for an illegible character.
- **Corrections beside, never over.** An evident typing error is corrected in a `*_fix` column, with the reason in
  `fix_note`; the typed value stays. A position that contradicts its neighbours and can't be resolved stays as typed,
  off the track (`on_track: no`).
- **Checked by computation.** A track is tested for legs the ship couldn't have steamed (`tools/check_track.py`), a
  torpedo's typed track angle against its course and gyro (`tools/check_attacks.py`). A typed value is never changed
  to agree.
- **Read by Claude, once.** Claude (Anthropic's AI model, working in Claude Code) read every scan and made every
  transcription here, under these rules, with one researcher directing and reviewing. Where it read in bulk, the
  folder's README says how each day or page was reviewed (`fronts/`). No row has had a second, independent reading:
  the inventory's status `verified` is used nowhere yet.
- **Translated by Claude.** A Japanese, German, French or Italian record is kept in the original with an English
  translation beside it. No translator has checked the translations; the original is there so that one can.
- **Computed by Claude's tools.** Conversions, placements and decoded positions come from the kit's tools, which
  Claude wrote; each such value is labelled (below) and carries the typed value it was computed from.

The typed values stand on their citations: each resolves to the archive's own image of the page. Everything else is
the project's work and is labelled as such.

## How each value is known

`basis` on a row says how its value is known; a source's `kind` in `SOURCES.yml` says what sort of witness it is.

| `basis` | Meaning |
|---|---|
| `reported` | The record says it |
| `derived` | Computed from what a record says: a grid reference turned into a position, a bearing and distance resolved |
| `inferred` | Reasoned from other records; the `note` gives the reasoning |
| `assumed` | Assumed, and labelled so: a zone letter the record doesn't type, a battery placed with its battalion |
| `secondary` | From a later history or site, where no record has been read |

A source's `kind` is one of `record` (written at the time by the subject or its command), `intelligence` (what one
side knew of the other at the time), `press` (published at the time), `assessment` (an official reckoning after the
fact), `recollection` (told later by someone who was there), `secondary` (a later history or site), and `reference`
or `derived` (not a witness: a chart, a manual, a dataset, or a method of ours).

Times are kept in the record's own zone, as typed (GCT in the Navy's tables); times this dataset computes are
labelled UTC.

## What is not here, and known limits

- **No people.** There are no rosters, crew lists or service records, and no one is followed by name; a unit's record
  is the unit's. Names the records themselves carry (a captain, a rescued aviator) stay as written.
- **Context is not participation.** A division's symbol on a situation map, or an operation's area and dates, says
  nothing about where one of its batteries was. Such rows are labelled as the larger unit's.
- **The front lines are a staff's picture** of each day at the map's hour, traced to a kilometre or two, and a sheet
  can lag a move by days.
- **Weather, seafloor and relief are modern datasets** (ERA5, ETOPO1, SRTM), not records: ERA5 rests on few
  observations in the 1940s western Pacific, and today's coastline shows harbour works built since. Harbour
  positions are standard coordinates, not the records', and say so.
- **Claims are kept as claims.** A sinking a submarine claimed and a loss the Japanese recorded are separate rows,
  paired in `claims.yml` with the strength of the match in words.

## Layout

Hand-edited, the source of truth:

| Folder | What |
|---|---|
| `boats/<hull>-<name>/` | A submarine: `ship.yml`, and one `patrol-N/` per war patrol (positions, attack sheets, the Japanese record of her attacks, claims; for BANG also depths, density layers and the FRUPAC radio-intelligence maps) |
| `ships/<hull>-<name>/` | A surface ship: `ship.yml`, `positions.csv` from her war diaries, a README |
| `commands/comsubpac/` | The submarine force's war diary for October 1944 |
| `convoys/<id>/` | A Japanese convoy: `convoy.md` |
| `engagements/<id>/` | Two sides meeting, each from its own records: `engagement.md`, and as needed `events.yml`, `claims.yml`, `positions.csv`, `routes.yml`, `reach.yml` |
| `operations/<theater>/` | The campaigns the stations sit inside, from the official histories: context, one Markdown file each |
| `army/`, `seabees/` | Units, stations, places, actions, crossings, relations |
| `fronts/` | The traced situation maps, a set of files per day |
| `roads/` | A wartime road map traced for one engagement's base map |
| `film/` | Archive film of the places and days in the records, one row per film |
| `silhouettes/` | Recognition silhouettes traced from the wartime plates |
| `relief/` | Shaded relief and land masks for four map views (generated from modern elevation data) |
| `SOURCES.yml`, `inventory.yml` | Every source; every report and how far along it is |

Generated by the kit's tools, never edited: every `.geojson` and `.json` (`track.geojson`, `ships.json`, `dives.json`,
`engagement.json`, `convoys.json`, `subjects.json`, `army.json`, `seabees.json`, `operations.json`, `silhouettes.json`,
`scans.json`, `citations.json`), `seafloor.csv`, `weather.csv`, `fronts/sitmaps.csv` and `relief/`.

Every file's fields are in [`SCHEMA.md`](SCHEMA.md) and the folder READMEs.

## Rebuilding and checking

From a clone of the kit (`git clone --recurse-submodules https://github.com/erichutchins/wwii-research-kit.git`),
`tools/check_builds.sh` rebuilds every generated file and `uv run tools/check_sources.py` checks every citation; the
kit's `tools/README.md` lists each tool.

## Licence, and how to cite

The transcriptions, corrections and notes are licensed [CC BY 4.0](LICENSE). The original records are not covered by
it: `SOURCES.yml` gives each one's own terms (the National Archives records are public domain, the 45th Infantry
Division Museum's need its credit line, the FRUPAC maps are linked and never copied). One exception among this
repository's own files: the P.108B silhouette is adapted from a CC BY-SA 3.0 drawing and carries that licence.

To cite the dataset, give its title, address and the version you used:

> Eric Hutchins, with Claude (Anthropic), *WWII unit records* (dataset), https://github.com/erichutchins/wwii-unit-records, commit `<hash>`
> or the date read. CC BY 4.0.

For any value you use, cite the original record as well: its row's citation resolves to the archive's own page.
