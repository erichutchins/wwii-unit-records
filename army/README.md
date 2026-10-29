# Army units: stations, actions and crossings, 1942–1945

Where twenty Army units were, day by day, from their own records: an anti-aircraft battery's
and a medical detachment's war from Oran to Bavaria, the 62nd CA (AA)'s batteries and headquarters
around it in North Africa, an infantry company in Normandy, a gun
battalion's headquarters battery with Third Army, and the 9th Armored Division's positions.
Every station row cites its page (`page`), in the forms listed in `../SOURCES.yml`.

| Unit | Records | Years |
|---|---|---|
| `62ca-c` Battery C, 62nd Coast Artillery (AA) / 62nd AAA Gun Bn | Morning reports (roll 783) | 1942–1944 |
| `62ca-a`, `62ca-b`, `62ca-g`; `62ca-d`, `62ca-e` Batteries A, B and G, 62nd CA (AA); Batteries D and E (July 1943 only) | Morning reports (rolls 782 and 783) | 1942–1943 |
| `62ca-hq1`, `62ca-hq2`, `62ca-hq3` the headquarters batteries of the 62nd CA (AA)'s 1st, 2nd and 3rd Bns; `62ca-med` its Medical Detachment | Morning reports (rolls 782 and 783) | 1942–1943 |
| `106aaa-d` Battery D, 106th AAA AW Bn (SP) | Morning reports; for 1945 the battalion's own histories and journal (45th Infantry Division Museum) | 1944–1945 |
| `67ca-med` Medical Detachment, 67th CA (AA) / 894th AAA AW Bn | Morning reports (rolls 792–794); for 1945 the battalion's printed history | 1942–1945 |
| `113inf-med`, `113inf-g` Medical Detachment and Company G, 113th Infantry | Morning reports (rolls 1689–1690, handwritten, filmed sideways; later rolls for 1943–44) | 1940–1944 |
| `313inf-b` Company B, 313th Infantry (79th Division) | Morning reports | 1944 |
| `128aaa-hq` HQ Battery, 128th AAA Gun Bn (Mbl) | Morning reports; for 1945 Third Army's after action report | 1943–1945 |
| `9ad` 9th Armored Division | Division-level sources: its G.I. Stories booklet, Third Army's report | 1944–1945 |

## Sources

- **Morning reports** (NARA RG 64, series [85713825](https://catalog.archives.gov/id/85713825)): one
  form per battery or detachment per day, giving the date, the STATION, the soldiers whose status
  changed, and a record of events. Online for January 1940 – December 1944; 1945–46 are on
  microfilm only, in St. Louis. The rolls are listed by catalog ID in `../citations.json`.
- **The 106th AAA AW Bn's own records, July 1944 – May 1945**: its monthly "History and Historical
  Records of Organization" and its journal, in the 45th Infantry Division Museum's collection at the
  Metropolitan Library System of Oklahoma County ([ContentDM, collection ok45th](https://cdm17494.contentdm.oclc.org/digital/collection/ok45th/search/searchterm/106th%20Anti-Aircraft)).
  *Courtesy of 45th Infantry Division Museum and the Metropolitan Library System of Oklahoma County.*
  They give the battalion headquarters' moves (rows `bn`, drawn as assumed) except in May, when
  they give Battery D's.
- **After May 1945, a lead**: the museum's run ends on 31 May 1945 (1–10 May is missing), and the
  morning reports for 1945–46 aren't online. The War Department filed the battalion's monthly
  histories, with their S-2 summaries and action reports, as **CABN-106-0.x** in NARA's RG 407
  (WWII Operations Reports) at College Park, not online. A scan of the December 1943 file copy
  ([ww2aircraft.net forum attachment](https://ww2aircraft.net/forum/attachments/106th-aa-aw-bn-henry-arnold-cmding-dec-43-pdf.576104/)) gives
  the file number: `CABN-106-0.3` in the margin of its first page and on the folder cover
  (`cabn106-1943-12/p1`, `/p11`). That file series is where June 1945 onward should be.
- **Third Army's *After Action Report, 1 August 1944 – 9 May 1945, Vol. II*** ([Google Books ee9mAAAAMAAJ](https://books.google.com/books?id=ee9mAAAAMAAJ), full view):
  the Antiaircraft Section's month-end situation maps and the Provost Marshal's troop movements.
  Rows cite it as `aar3/pNNN`, the page of the downloaded PDF.
- **The 894th AAA AW Bn's history** (1945, mimeographed; a 2012 retyped copy): the battalion's
  moves in 1945.
- The 9th Armored Division's G.I. Stories booklet (Lone Sentry) and Wikipedia, for division positions.
- The *Order of Battle of the United States Army, World War II: European Theater of Operations: Divisions*
  (Office of the Theater Historian, Paris, December 1945; `etoob` in `../SOURCES.yml`): each division's
  assignments and attachments to corps and armies, and its command posts, by date. Rows cite the printed page
  (`etoob-9AD/p502`).

Download and rendering instructions for each are in the kit's [guides](https://github.com/erichutchins/wwii-research-kit/tree/main/guides) and the tools' own help.

## Files

Hand-edited (the source of truth):

- `units.csv`: the units, with lineage notes (`unit`, `name`, `short` (the map's label), `note`)
- `stations.csv`: each unit's station whenever it changed, as typed, with its page
- `places.csv`: coordinates for the places the stations name
- `actions.csv`: Battery D, 106th AAA's engagements and casualties, from the battalion's monthly
  histories (Aug 1944 – Apr 1945); the 62nd CA (AA) batteries' firings (A, B, C and G), from their morning reports
  (Oran and Algiers, 1942–43)
- `ships.csv`: the ships of the sea crossings
- `relations.csv`: dated relationships between units (part of, attached to, under command of, took part in), each with its page
- `routes.csv`: waypoints for legs the reports don't trace (Atlantic voyages, train rides).
  Columns: `unit`, `from_date`, `to_date` (the two stations it joins), `seq`, `lat`, `lon`,
  `note` (on the first row: why the route is drawn that way). Always drawn dashed as assumed.

Generated, never edited: `army.json`, each unit's stations placed on the map (town, offset or
grid reference), with its routes, ships and actions, for the kit's `site/army.html`.

```
python3 tools/geocode_places.py   # fill in coordinates for new places.csv rows
python3 tools/build_army.py       # check every row and write army.json; must report 0 problems
```

## stations.csv columns

| Column | Meaning |
|---|---|
| `unit` | Key into `units.csv` |
| `date` | The report's date ("ending 2400" on that day), written ISO; the form has it in words |
| `station` | The STATION line **exactly as typed**, including spelling ("Pozzouli", "Veiron"). `?` marks an illegible letter or digit |
| `place` | Key into `places.csv`; empty when the report gives no position ("At Sea", "En route"). Those rows are in the log but not on the map, and the leg across them is drawn dashed as assumed |
| `offset` | Distance and bearing from `place` as the report gives it, normalised: `10 mi SE`, `2 km NNE`, `1500 yd E` |
| `grid` | The map grid reference as typed: a 100 km square letter and an easting-northing (some have no letter, or give a map sheet instead) |
| `grid_on` | Which grid `grid` is on: `italy-s` / `italy-n` (South / North Italy Zone), `lambert3` / `lambert2` / `lambert1` (French Lambert Zones III, II and I; Zone I is Normandy, 1944), `nwa` (British North West Africa Grid, Tunisia 1943: Lambert, Clarke 1880, origin 34 N 0 E, scale 0.9994, false origin 1000 km E 500 km N; the 100 km letters repeat in every 500 km block, fixed by the worked example on AMS's 1942 Alger sheet, `princeton-amsalger`; see `tools/grid_ref.py`), `ndg` (Nord de Guerre), `ndg-w` (its western 500 km block, lettered V). Found by decoding each reference on every grid and checking it against the named town (`site/grids.html` shows every check); `tools/grid_ref.py` converts. The station is mapped at the grid point when the reference is to 1 km or better and falls within 8 km of the town plus offset; otherwise at the town |
| `page` | `rg64-<roll NAID>/pNNNN`: the page in the catalog viewer (`?objectPage=NNNN`); the cache's `nara/rg64-…/pNNNN.jpg` when downloaded. `ok45th-<item>/pNN`: page NN of a 45th Infantry Division Museum PDF; the cache's `45th-museum/ok45th-…/pNN.jpg` when rendered. `hist894/pNN`: page NN of the retyped copy of the 894th's history (not the booklet's printed page number, which is 8–9 lower). Every form is in `../SOURCES.yml` |
| `source` | `mr` = morning report. `btry` = Battery D's own position in the battalion's records (the May table of battery CPs, or an action report naming the battery). `bn` = the battalion command post from its journal or history; the battery is assumed nearby, and the map draws it hollow with dashed legs. `regt` = the Regimental Headquarters Battery's morning report, used for the 67th CA (AA)'s medical detachment in March–April 1943 when its own reports are missing; drawn the same way. `hist` = the 894th battalion's position in its printed history (1945), the detachment assumed with battalion headquarters; drawn the same way. `aar` = the 128th AAA's battalion symbol on a Third Army antiaircraft situation map, or its move in that report's text (1945); drawn the same way. `div` = the 9th Armored Division's (or one combat command's) position; drawn the same way. `cp` = a division headquarters' command post, from the ETO order of battle (`etoob`): the headquarters' own position, drawn solid. `uaar` = a unit's own after action report, as transcribed (the 60th Armored Infantry Bn's, `eucmh60aib/<yyyy-mm>`, the month's report): the battalion's own position, drawn solid |
| `note` | Readings, identifications, forward detachments, editorial context |
| `when` | Optional: what the record supports about the date, when that is less than `date` (which stays an ISO day, for sorting and the map). `..1945-01-31`: there by then (a situation map of that day); `1945-02`: some day that month (a move given only by month). Empty: the row starts on its date. A row lasts until the next row starts, so these give each stay a certain part and a possible part (the evidence engine's date forms) |
| `precision` | Optional: how the position was given, when the `source` doesn't say it (one of `grid-100m`, `grid-1km`, `town`, `area`, `division`; each stands for a working tolerance, a provisional assumption of the tools that compare positions, not a measured error). A division's symbol on a situation map is `area`: the map symbol's tolerance, though the position is still the division's (`source` `div`), which says nothing about where its units were |

Only **changes** of station are recorded, plus anything worth noting; a unit
stays where its last row puts it. The rows were found with
`tools/morning_reports.py locate` (OCR, to find the unit's pages each month)
and `changes` (OCR, to find pages where the station text changes), then every
row was read from the scan itself (`crop_pages.py heads`). The OCR is never
the source of a value.

For the 1945 journal entries `station` is the place phrase as typed ("Gersfeld
at N-550079"); the note gives the times and context.

## relations.csv columns

Dated relationships between units, so a unit's place in the chain of command is data, not a note. One row per
relationship and period; a change of attachment is a new row.

| Column | Meaning |
|---|---|
| `unit` | Key into `units.csv` (or a formation named in an earlier row's `other`) |
| `relation` | `part_of` (permanent: a battery of its battalion), `attached_to` (temporary), `under_command` (in a corps' or an army's order of battle), `took_part` (in an operation or battle) |
| `other`, `other_name` | The other end: an id, and its name as the records give it |
| `from`, `to` | When it held, as far as the cited page says, in the same forms as `when` above: `..1945-01-20` (by then), `1945-05-04..` (still then), `1945-02` (some day that month). An empty `to` means no end is recorded |
| `basis` | `reported` (the page says so) or `inferred` (reasoned; the note says from what). Relationships computed from positions (near, same path, inside an operation's area) are never stored |
| `page` | The citation, in a form in `../SOURCES.yml` |
| `note` | The record's words and what they don't say. A division's `took_part` is the division's: it is context for its units and men, not their participation |

## Leads

Statements found in research notes or secondary sources that no record cited here supports yet. They are kept
here, not in the data, until a page says so.

| Lead | Said by | Searched | Still to search |
|---|---|---|---|
| The 9th Armored Division's attachment to Third Army began 9 Jan 1945 (the order of battle) or 11 Jan (Third Army's Quartermaster and Antiaircraft sections): which date is right | `etoob-9AD/p502` (9 Jan); `aar3/p626` (11 Jan: "attached ... for supply and administration on 11 January, but remained assigned to the Fifteenth U. S. Army") and `aar3/p097` (the division's return to the Third Army area on 11 Jan) | Third Army's after action report, Quartermaster and Antiaircraft chapters for January (both read on the scan); the 9th Armored's own after action report and the 60th Armored Infantry Battalion's (transcribed by EUCMH, archived): no army named | The 9th Armored's G-3 and G-4 reports and journals for January 1945 (NARA RG 407, the division's 609 files); Fifteenth Army's history; Third Army's letters of instruction, January 1945 |

## actions.csv columns

Each history logs the battalion's engagements day by day: aircraft engaged,
ground fire missions, casualties. A row is kept when the entry names Battery D
(alone, with other batteries, or "all batteries") — entries that say only
"this battalion engaged" are left out, since D may not have fired.

Battery C, 62nd CA (AA)'s rows come from the record of events on its own morning reports, which
give only "Fired on hostile targets" and the times: no aircraft type, no result (`unknown`). A
newspaper or communiqué that reports the same raid is cited in the note (`gallica:`), and its claims
are the whole defense's, not the battery's.

| Column | Meaning |
|---|---|
| `unit` | Key into `units.csv` |
| `date`, `time` | As in the history; time is the typed 24-hour figure without its zone letter (A = GMT+1; B = GMT+2, used in summer: the reports switch from B to A in mid-September 1944 and back in April 1945) |
| `who` | Which batteries, as the entry names them: `D`, `D, 2nd Plt`, `B, C, D`, `all batteries`, `battalion` |
| `kind` | `air` (engaged aircraft), `ground` (ground fire), `casualty`, `event` |
| `result` | The entry's outcome: `destroyed`, `probable`, `hits`, `none`, `unknown`, `friendly` (the plane turned out to be American), `captured`, `neutralized`, `wounded`, `killed`, `injured` |
| `text` | The entry's words, abridged with `...`. Other soldiers' names and serial numbers are left out; the note says when the record names someone |
| `placed` | How the map point is made: `grid` (the entry's Nord de Guerre reference, via `tools/ndg_grid.py`), `place` (a `places.csv` row), or `station` (no usable position: the battery's station that day) |
| `place`, `grid`, `grid_on` | As used by `placed`; `grid_on` as in stations.csv |
| `page` | `ok45th-<item>/pNN` |
| `note` | Context, and which position a grid marks (often the target or the crash, not the battery) |

## ships.csv columns

The ships of the sea crossings (so far the Mediterranean ones: Ferryville to
Gela, Bizerte to Naples, Sicily to Italy, and Naples to southern France), shown
on the station rows.

| Column | Meaning |
|---|---|
| `unit`, `date` | The station row the ship is typed on (for a crossing the reports don't record, the arrival row) |
| `landed` | The date of the station where the crossing ended; the map's tooltip there names the ship |
| `as_typed` | The ship as the report gives it ("Ship # 416", "Aboard LST 313, 318") |
| `ship` | The ship as identified, or the typed name marked "(as typed)" when it can't be |
| `status` | `confirmed` (identified), `candidate` (a possible identification), `unknown` (the typed name or number doesn't identify a ship: both US Navy LSTs numbered 313 and 318 had been sunk in 1943), `none` (no ship recorded) |
| `voyage` | What the unit's own records say about the crossing, with pages |
| `about` | The ship's history, from the source in `links` |
| `links` | Space-separated sources (the Navy's DANFS ship histories) |

## places.csv columns

`place`, `query` (what was looked up), `lat`, `lon`, `source` (`OSM Nominatim`,
`hand-placed`, or `grid`), `note` (the OSM name it matched, or why it was placed
by hand). A town named in a station is placed at the town; the `offset` then
moves it. `grid` places come from the typed reference through
`tools/ndg_grid.py`, for stations that name no town or name the battery's
own CP.

## The grids

The references are on six grids: the South and North Italy Zones (Sicily
1943, Italy 1944), the French Lambert Zones III and II (southern France and
the Saône valley, Aug–Nov 1944), Lambert Zone I (Normandy, Brittany and
Maine, Jun–Aug 1944: Company B, 313th Infantry, and HQ Battery, 128th AAA), and the Lambert
"Nord de Guerre" grid (the 128th AAA from Étampes to Nancy, Aug–Sep 1944, in
its western block; the Vosges to Bavaria, Sep 1944 – May 1945). `grid_on`
records which; `tools/grid_ref.py` converts all six (`tools/ndg_grid.py` is the Nord de
Guerre one alone). `site/grids.html` explains them and checks every reference
against its named town: on the right grid most fall within 3 km.

Where a typed reference misses its named town by 10–50 km (Eisenberg,
Osthofen, Ober-Sailauf, Weißenburg in 1945; Battipaglia in July 1944) the row
is placed at the town. The 1945 notes say which digit probably slipped;
Battipaglia's miss (13 km) is unexplained. Twice the
typist kept the old square letter after crossing into the next square
(Gersfeld and Ostheim in April, Battery D's 15–23 May CP); the note says so.
Company B, 313th Infantry's clerk did the same in Normandy (VO for VT, 5–11 Jul 1944), and so
did the 128th AAA's HQ Battery the next month (Y-977547 "near Rennes", in square X).
