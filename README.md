# WWII unit records

Where US submarines, a destroyer and Army units were in the Second World War, and what they did,
transcribed from their own records: submarine war patrol reports, a destroyer's war diary, Army
morning reports and battalion histories, with the Imperial Japanese Navy's records of the same
convoys beside them. Every row cites the page it was read from.

This is the data half of the [WWII research kit](https://github.com/erichutchins/wwii-research-kit), where it is the `records/` submodule: the kit's tools fetch, check and build
these files, and its pages draw them. The data stands on its own: CSV and YAML, no code needed.

## The rule: cite every source

Every transcribed row carries a citation (`page`, `ref`, `source` or `map`) in one of the short
forms listed in [`SOURCES.yml`](SOURCES.yml): `rg367-74802746/p05` is page 5 of National Archives
catalog item 74802746; `jacar:C08030140600` a JACAR record; `ok45th-17552/p06` a museum PDF's page.
`tools/check_sources.py` fails if any citation doesn't resolve or any row has none, and writes
[`citations.json`](citations.json): every cited National Archives item's own catalog title and series.

Values are recorded **exactly as typed** in the original, `?` for an illegible character. A
correction never overwrites the original: it goes in a `*_fix` column with the reason in `fix_note`.

## What's here

[`inventory.yml`](inventory.yml) lists every report and record: found, transcribed, mapped, or
still to look for.

| Folder | What | Records |
|---|---|---|
| `boats/<hull>-<name>/` | US submarines: `ship.yml` (name, class, speed limit, map wording), one `patrol-N/` per war patrol | War patrol reports (NARA series 305243, microfilm M1752) |
| `boats/ss-385-bang/` | USS BANG, six patrols in full: positions, every dive and depth charge, density layers, the Japanese records of her attacks, the FRUPAC radio-intelligence maps ([README](boats/ss-385-bang/README.md)) | |
| `ships/<hull>-<name>/` | Surface ships: one `positions.csv` from a war diary ([USS Haynsworth](ships/dd-700-haynsworth/README.md)) | War diaries (NARA RG 38) |
| `engagements/<id>/` | One convoy battle each, from every boat's report and the Japanese side: `engagement.yml`, `notes.csv` | |
| `army/` | Eight Army units' stations, actions and sea crossings, 1940–1945 ([README](army/README.md)) | Morning reports (NARA RG 64), battalion histories |
| `silhouettes/` | Recognition silhouettes: aircraft traced from the 1943–45 plates, ships drawn to the ONI 54 heights, and the battle pages' generic shapes (`silhouettes.yml`; how they were made is in its header) | CINCPAC-CINCPOA Bulletin 105-45, FM 30-30, ONI 54 |
| `SOURCES.yml`, `citations.json` | Every source, and every cited archive item's title | |

Generated (don't edit by hand; the kit's tools rebuild them): `track.geojson`, `tracks.geojson`,
`ships.json`, `seafloor.csv` (NOAA ETOPO1), `weather.csv` (ERA5), `crossrefs.json`,
`pack_timeline.csv`, `dives.json`, `battles/`, `silhouettes/silhouettes.json`, `scans.json` (each cited page's
public scan URL), `citations.json`.

Not here: the people. There are no rosters, crew lists or service records, and no one is followed
by name; a unit's record is the unit's. Names the records themselves carry (a captain, a rescued
aviator) stay as written.

## Rebuilding

From a clone of the [kit](https://github.com/erichutchins/wwii-research-kit) (`git clone --recurse-submodules https://github.com/erichutchins/wwii-research-kit.git`):

```
uv run tools/check_track.py all --geojson   # speed-check every track; GeoJSON and ships.json
uv run tools/check_sources.py               # every citation resolves; inventory matches the folders
uv run tools/check_crossrefs.py             # attacks beside the Japanese records -> crossrefs.json
uv run tools/fetch_seafloor.py              # only if positions changed (ETOPO1, cached)
uv run tools/fetch_weather.py               # only if positions changed (ERA5, cached)
uv run tools/build_dives.py                 # dives.json
uv run tools/build_silhouettes.py           # silhouettes/silhouettes.json
uv run tools/build_battle.py                # battles/ (each carries the category silhouettes)
```

`check_track.py` must report 0 too-fast legs.

## Licence

The transcriptions, corrections and notes are licensed [CC BY 4.0](LICENSE): use them, and cite
this dataset and the original records (`SOURCES.yml` gives each one's own terms; the National
Archives records are public domain, the 45th Infantry Division Museum's need its credit line, the
FRUPAC maps are linked, never copied).

## Formats

### ship.yml

`name`, `hull`, `class`, `kind` (`submarine`, `destroyer`), `max_kts` (the speed check's limit),
`dives` (has a depth log for the dive-profile page), `silhouette` (the class profile in
`silhouettes/silhouettes.yml` that draws her: one silhouette serves every ship of a class, so the link runs
from the ship to the silhouette, never back; left out until her class has one), and `map`: the map page's wording. `periods`
lists each patrol (`n`, `name`, `dates`, `area`, `co` as the report gives the commanding officer);
`ports`, `places` and `home` place labels and the opening view. Anything left out takes the page's
defaults for that kind of vessel.

### engagement.yml

Fields are in the kit's `guides/BATTLES.md`.

### positions.csv columns

| Column | Meaning |
|---|---|
| `source` | Which part of the report: `bt` (bathythermograph / density-layer table, GCT), `air` (aircraft contacts — the boat's own position), `ship` (ship contacts — the **target's** position), `attack` (torpedo attack data sheet), `radar` (radar countermeasures log), `noon` (daily noon position in the narrative), `narrative` (ports, arrivals, departures) |
| `ref` | Contact or attack number as the report numbers it |
| `date`, `time`, `zone` | Exactly as typed. Zones: Z = GCT, K = −10, I = −9, M = −12, Y = +12, X = +11, W = +10, VW = +9½ (US Navy letters; "−10" means local = GCT + 10) |
| `lat_raw`, `lon_raw` | Exactly as typed, in deg-min (`19-26N`). `?` marks a digit that is illegible in the scan |
| `page` | The cited page, e.g. `rg367-74802746/p16`: catalog item 74802746, object page 16 (`nara/rg367-74802746/p16.jpg` in the kit's cache after `tools/nara.py fetch`) |
| `on_track` | `yes` = used for the track line. `no` = ship contacts, pre-departure readings, and fixes that contradict their neighbours |
| `lat_fix`, `lon_fix`, `date_fix`, `time_fix` | Corrections of evident typing errors in the 1944–45 originals. Raw values are never overwritten |
| `fix_note` | Why a correction was made, or why a fix is off the track |

Port positions (Pearl, Midway, Saipan, Guam) aren't in the reports; they are
standard harbor coordinates and say so in `note`. Arrival times not given in
the report are set to noon and marked "noon assumed".

### depths.csv columns

| Column | Meaning |
|---|---|
| `date`, `time`, `zone` | As typed in the narrative (same zone letters as positions.csv). Where the report gives no time, the `quote` says how it was estimated |
| `event` | `dive` (submerged; depth not given), `surface`, `periscope` (back to periscope depth), `radar_depth`, `depth` (a depth ordered or reached), `passing` (a depth noted on the way down, not an order), `bottom` (sat on the seabed), `charges` (depth charges heard with no depth change), `quake`, `routine` (a summary like "submerged during daylight" covering several days without itemized times; the span ends at the date in the quote) |
| `depth_ft` | Depth in feet as logged |
| `charges` | Depth charges (or, Patrol 6, bombs) counted in that entry, as the captain tallied them |
| `proximity` | How close the captain judged them ("very close", "distant", ...) |
| `quote` | The captain's words, abridged with `...`; editorial notes in parentheses |
| `page` | Scan file, as in positions.csv |

The dive-profile page assumes periscope depth (about 60 ft) wherever a dive
gives no depth, holds each logged depth until the next entry, and changes depth
at about 100 ft/min. Those assumptions are labelled on the page.

### layers.csv columns

One row per reading in the report's density-layer table (taken with the
bathythermograph on a dive, usually once a day around 2000-2100 GCT).

| Column | Meaning |
|---|---|
| `date`, `time_gct` | As typed (GCT). Summary notes with no time have `time_gct` blank |
| `iso_ft`, `iso_deg` | "Isothermal to feet / degrees": the warm surface layer is `iso_deg` °F down to `iso_ft` feet |
| `grad_ft`, `grad_deg` | "Negative gradient to feet / degrees": below that, temperature falls to `grad_deg` °F at `grad_ft` feet. This cold layer bends enemy sonar, which is why the captains hid under it |
| `date_fix` | Same corrections as positions.csv where the date was mistyped |
| `note` | Pencilled circles on the scans (someone at headquarters marking strong layers), second isothermal lines, faded values |

### The Japanese side (japanese.csv, crossrefs.csv)

The other side of a boat's attacks, from Japanese wartime records (JACAR,
`tools/jacar.py`) and, where no primary record has been found yet, from
combinedfleet.com. Transcribed the same way as the patrol reports: as
written, with the page, and with an English translation beside the original.

#### japanese.csv columns

| Column | Meaning |
|---|---|
| `id` | `J01`, `J02`, … within the patrol |
| `source` | `jacar:<reference code>` (primary; the image is at `https://www.jacar.archives.go.jp/das/image/<code>`) or `combinedfleet:<page>` (secondary, e.g. `Daiyoku_t` = combinedfleet.com/Daiyoku_t.htm) |
| `page` | Page of the JACAR PDF (`jacar/<code>/pNN.jpg` in the kit's cache after `tools/jacar.py fetch`) |
| `ship`, `convoy` | Romanized as in English-language references (convoy TAMA-17 = タマ一七, Takao→Manila) |
| `event` | `departed`, `joined`, `torpedoed`, `sank`, `rescue`, `attacked_no_damage`, `sub_sighted`, `status`, `weather`, `loss_list` (a monthly loss table) |
| `date`, `time`, `zone` | As written. Zone `I` (−9, Tokyo time), which the Imperial Navy and its convoys kept |
| `lat_raw`, `lon_raw` | Converted from 北緯一九度〇六分 to `19-06N` (the original is in `original`) |
| `original` | The Japanese text, abridged with `…` |
| `translation` | English translation of `original` |
| `note` | Context, and agreement or disagreement with other sources |

`crossrefs.csv` pairs an attack (`ref` in positions.csv) with a `japanese.csv` id.
An attack can be another boat's, written `<boat>/<patrol>:<ref>` (e.g.
`ss-384-parche/1:Attack 2`). `relation` is `hit` (the attack caused that
record), `miss` (same moment, no damage), `probable` (time and place point to
this attack, but another boat is credited or was attacking too), `possible`
(times fit, but more than one attack could explain the record), or `no_loss`
(a claimed sinking with no matching entry in the Japanese loss list).

### US radio intelligence (frupac.csv)

The National Museum of the Pacific War's Fleet Radio Unit Pacific map
collection (846 overlays, mid-1943 to 1945, on UNT's Portal to Texas History)
plots what US radio intelligence knew of Japanese shipping, day by day, in
pencil. `tools/frupac.py` finds the maps for a ship or a date. The zoom
viewer (`https://texashistory.unt.edu/ark:/67531/<map>/m1/1/zoom/`) serves
full-resolution tiles and the notes are legible there; the plain page images
are only ~1500 px wide. The collection is CC BY-NC-ND, so the maps are linked
and read in place, never copied.

#### frupac.csv columns

| Column | Meaning |
|---|---|
| `id` | `F01`, `F02`, … within the patrol |
| `map` | Portal ark id (`metapth1733069` → `https://texashistory.unt.edu/ark:/67531/metapth1733069/`) |
| `map_date` | The map's date in the catalog |
| `view` | Zoom-viewer query that frames the note: append to `…/<map>/m1/1/zoom/?` |
| `text` | The note as written, line breaks as ` / `, `?` for an unsure reading |
| `dtg` | The message date-time group written with the note (day + time, zone not given) |
| `date`, `time` | The event's day and time as written (`1515/29` → the 29th, 1515); the month is the map's |
| `lat_est`, `lon_est` | Decimal degrees, **estimated** from where the mark sits on the map: against a printed grid where there is one (±0.1–0.2°), otherwise against the overlay's `120`/`130` meridian labels assumed to sit on 20N (±0.3°). Blank when the note has no mark of its own |
| `ship` | As written (FRUPAC's romanization) |
| `event` | `torpedoed`, `sank`, `attacked`, `torpedo_attack`, `torpedo_track`, `sub_contact`, `sub_sighted`, `df_sub` (a direction-finding fix on a submarine), `claim` (a US boat's own report), `convoy`, `position`, `arrival`, … |
| `attack` | The boat's attack (`ref` in positions.csv) the note belongs to, if any |
| `relation` | `match` (the same event), `candidate` (time and place fit but something doesn't), `context` (nearby, probably not this boat) |
| `note` | Reasoning, and agreement or disagreement with the boat's report |

**Assumption:** FRUPAC notes carry no zone letter. They are taken to repeat
the Japanese time (zone I, −9), which the matches bear out (below).
`check_crossrefs.py` prints each note against its attack in GMT.
