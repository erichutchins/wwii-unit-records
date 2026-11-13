# Schema: the files and their fields

The field dictionary for [WWII unit records](README.md). Each section is one kind of file. The folder READMEs cover
what is particular to a folder: [`army/`](army/README.md), [`seabees/`](seabees/README.md),
[`fronts/`](fronts/README.md), [`film/`](film/README.md), [`roads/`](roads/README.md),
[`operations/`](operations/README.md), [`commands/comsubpac/`](commands/comsubpac/README.md), and each vessel's own.

Conventions that hold everywhere:

- **Tables are CSV** (RFC 4180, UTF-8, a header row). A cell of words (a `note`, a `quote`, a `station`) is quoted
  where it holds a comma or a quotation mark. **Records' words, lists and nested fields are YAML**, or Markdown with
  YAML front matter. **JSON and GeoJSON are generated**, never edited.
- **As typed.** A value transcribed from a record is exactly as the record has it; `?` stands for an illegible
  character. A correction goes in a `*_fix` field beside it, with its reason.
- **Citations** (`page`, `ref`, `source` or `map`) are in the forms listed in [`SOURCES.yml`](SOURCES.yml).
- **`basis`** says how a value is known; the README's table gives the common values, and each file below lists the
  ones it uses.
- Paths that begin `tools/`, `site/`, `guides/` or `reference/` are in the
  [kit](https://github.com/erichutchins/wwii-research-kit), not in this repository.

## ship.yml

One per vessel, in `boats/<hull>-<name>/` (submarines) or `ships/<hull>-<name>/` (surface ships).

| Field | Meaning |
|---|---|
| `name`, `hull`, `class` | As the Navy's lists give them |
| `kind` | `submarine`, `destroyer`, `destroyer escort`, `battleship`, `carrier`, `cruiser` |
| `plain` | What she was, in a line, in our words, for a reader who doesn't know the designation |
| `max_kts` | The speed check's limit (the kit's `tools/check_track.py`) |
| `dives` | Whether she has a depth log (`depths.csv`) |
| `silhouette` | The class profile in `silhouettes/silhouettes.yml` that draws her. One silhouette serves every ship of a class, so the link runs from the ship to the silhouette, never back; left out until her class has one |
| `map` | A block of wording and framing for the kit's map pages, all optional (anything left out takes the page's default for that kind of vessel). Inside it: `periods`, each patrol or month (`n`, `name`, `dates`, `area`, `co` as the report gives the commanding officer); `ports` and `places`, labels; `home`, the opening view; and the page's own words (`title`, `intro`, `listTitle`, `legend`, `labels`, and so on) |

A ship with no record transcribed yet has only a `ship.yml` (no `positions.csv`); the tools skip her.

## An engagement (engagements/<id>/)

The model, the reasons for it, and how the pages draw it are in the kit's `guides/ENGAGEMENTS.md`; `tools/build_engagement.py` checks every field below.

**`engagement.md`**: YAML front matter, then the story in Markdown (a paragraph per statement, `##` headings; links
written `[[kind:id|words]]`: `cite`, `op`, `ship`, `unit`, `page`, `convoy`, `engagement`). The first paragraph is the
page's lede.

| Field | Meaning |
|---|---|
| `title`, `short`, `eyebrow` | The title, a short name, and a line of context above the title |
| `theater` | `pacific`, `mediterranean`, `europe` |
| `clock` | The zone letter the entries' times are in when an entry gives none (Haynsworth's `I`; Neuburg's `B`). Left out when the records don't say: the page then shows their times as local, unconverted |
| `window` | `{from: YYYY-MM-DDTHH:MMZ, to: ...}` in UTC: the span the engagement covers. Left out, it's the span of the timed entries. Entries outside it stay in the log, off the clock |
| `against` | Whom the subjects faced, as the records name them (`[de, it]`): a list of nationalities, written only when more than two meet in one frame (Algiers, where the RAF's record book and the city's paper stand beside Battery C). Left out, it is every nationality that isn't the followed subjects' own |
| `participants` | Who took part, each with an `id` (used by events and pages), `name`, `of` (its nationality as the record gives it: `us`, `jp`, `de`, `it`, `uk`, `fr`, ...; never a bloc), `kind` (`submarine`, `destroyer`, `convoy`, `air group`, `aircraft`, `tanker`, ...), and as it applies: `track` (a boat's patrol, `ss-385-bang/1`, or a ship, `dd-700-haynsworth`: its own record, read where it is, never copied), `convoy` (a `convoys/<id>`), `hull`, `co`, `sil` (a silhouette id; a tracked ship's comes from her `ship.yml`), `unit` (an Army unit in `army/units.csv`, `kind: army`: the pages follow it from one engagement to the next), `basis` (`reported` if not given; `inferred` when no entry names the unit itself, with the reason in `note`), `note` |
| `places` | Map labels: `name`, `lon`, `lat`, `small` |
| `steps`, `views` | The story's steps, framed (below, "Steps") |
| `relief`, `roads` | The map's base where the records' places sit closer than a world coastline tells: a `relief/<name>/` (or a list of them, coarse first; today's elevation, made by the kit's `build_relief.py`) and a traced road map, `roads/<name>-primary.geojson` (`relief: [algiers, algiers-town]`, `roads: oss967`) |
| `fronts` | The traced situation maps, `fronts/<name>.geojson`, in date order (`fronts: [12ag-1945-03-07, 12ag-1945-03-09, ...]`): the army group's picture of each day, context under the records. A participant with a `unit` also brings its own placed stations from a week before the window to its end |

At most three participants may have a US track (the build's `MAX_BOATS`). The boats' attacks, ship contacts and
depth charges come from their own patrol folders, the Japanese records from each boat's `japanese.yml` inside the
window, and US radio intelligence from each boat's `frupac.yml` inside the window (below: each note becomes an entry
with `actor: FRUPAC`, `of: us`, `about` the ship it names, its `text` as `words`, the map as its source, zone I assumed
for its time and its position read off the map, both said to be ours; a note tied to an attack also joins that attack's
pairing as `intelligence`); `events.yml` holds only what belongs to this engagement.

**`events.yml`**: a list of entries, in the order of the account.

| Field | Meaning |
|---|---|
| `at` | `YYYY-MM-DD HHMM Z` as recorded, with its zone letter (or the engagement's `clock`); a date alone, or a month, when no time is recorded |
| `placed` | Why the time isn't the record's: `seq` (placed by the order of the account) or words ("Between 1245 and 1250; no time recorded") |
| `actor`, `of` | Who (a participant id, or a name as the record gives it); the actor's nationality (`us`, `jp`, `de`, `it`, `uk`, `fr`, ...), which may be left out when the actor is a participant id, whose `of` it takes. The press is told apart by its source's `kind` in `SOURCES.yml`, not by a side |
| `kind` | From the vocabulary in `tools/build_engagement.py` (`KINDS`): `contact_report`, `received`, `attack`, `hit`, `sank`, `rescue`, `log`, `station`, `report`, ... Add a word there rather than inventing one in a file |
| `to`, `from` | A message's recipients, or its sender (participant ids) |
| `title`, `words` | A heading; the record's words as typed (or ours, quoting it), when the record is in English |
| `original`, `lang`, `translation` | A record that isn't in English, instead of `words`: its words exactly as quoted, its language as a two-letter code (`de`, `it`, `fr`, `ja`), and our translation. Editorial notes go in square brackets in the translation, or in `note` |
| `source`, `ref` | The source in words; the citation (a `SOURCES.yml` form or a URL) |
| `pos`, `step` | A `positions.csv` id; the step of the story this entry belongs to (below, "Steps") |
| `basis`, `note` | `reported`, `derived`, `inferred`, `assumed`, `secondary`; what's assumed and why |

**Steps**: the story told in steps, each with a time and a frame. An entry's `step` names the step it belongs to (`s7`); the story's prose links to a step as `[[step:s7|at 1250
she was hit]]`, and the build fails on a link to a step no entry carries. A step's time is its earliest clocked
entry's; its framing comes from the front matter: `steps: {s7: {view: close, when: "6 April, 1245-1250"}}`, where
`view` names one of `views: {close: {name: Haynsworth's station, box: [[129.36, 26.62], [129.86, 27.04]]}}` (`box` is
`[[west, south], [east, north]]`) or is a box written inline, and `when` is the step's span in words. A step with no
`view` is framed on its own entries' positions. The build writes `steps` into `engagement.json` in time order.

**`claims.yml`**: the questions the records leave open. `question`, `answer`, `weight` (`record`, `photo`,
`recollection`, `inference`, `secondary`), `source` (words), `ref` (citation), `note`. Questions with competing
hypotheses go further in an evidence case.

**`positions.csv`**: `id,label,of,kind,date,time,lat,lon,from,brg,nm,lat2,lon2,basis,source,ref,note`. `of` is whose
position it is, as the record gives it (`us`, `jp`, `de`, ...), empty for a place (a town, a harbour, a landmark). A
position given as bearing and distance from another (`from`, `brg`, `nm`) is resolved by the build. `basis`: `fix`,
`reported`, `derived` (worked out from a grid reference or a reference point; the `source` says how), `decoded` (a
Japanese kana grid square whose key is established), `probable` (one whose key rests on an assumption, said in `note`),
`assumed`, `approx`. `hand-placed` (a reference point placed on a modern map) is defined and not yet used.

**Read from the participants' records** into `engagement.json` (never copied into the engagement's folder): each
boat's `tracks` (its fixes inside the window, one either side), `dives` (its `depths.csv` as states, `surfaced` or
`submerged` with the depth where logged and, where the row counts them, the `charges` and their `proximity`, from the
last state before the window) and `water` (the seafloor under its track from `seafloor.csv`, and its `layers.csv`
readings of the window's days and the day either side), its attack `sheets`, its depth charges as entries (a depth
order's row that counts charges is an entry too).

**Derived, never stored** (`tools/build_engagement.py` writes them into `engagement.json`; its docstring has the
reasons): on each participant `followed` (it has a track or a unit: a subject that is followed; a convoy is
the other side's record, read against the followed boats' sightings of it, and isn't) and `opposed`; on the engagement
`own` (the followed subjects' nationalities); on each entry and position `opposed` (its `of`, or its actor's, is among
`against`, or, when `against` isn't written, isn't among `own`); on each entry, claim and position `source_kind` and
`source_of`, its citation's `kind` and `of` in `SOURCES.yml` (a record, the press, a later account; whose).

## An engagement's routes (routes.yml)

Paths, mostly through the air: a bomber's course, a formation's line on a squadron's sketch, a sortie from its airfield.
A list; each entry is one path. Hand-edited; the build resolves the
points into `engagement.json` (`routes`).

| Field | Meaning |
|---|---|
| `id`, `label` | A short key; a label |
| `of` | Whose path (us, de, ...); required |
| `by` | What moved: `air`, `ground` or `sea`; required |
| `actor` | A participant id, optional: whose path it is (the bombers' group) |
| `basis` | `reported` (a course or track the record types), `sketched` (a sketch map's line, traced on its grid), `inferred` (a straight line between two places where no record gives the path) |
| `points` | A run of points, each `{lat, lon}` or a `positions.csv` id |
| `from`, `to` | Two `positions.csv` ids: a straight line between them (`inferred`) |
| `to`, `course`, `drawn_km` | A course as typed (degrees), drawn back from position `to` for `drawn_km`; the length is ours, not the record's |
| `arrow` | `false` where the direction isn't sure (a sketch whose arrowheads disagree) |
| `time`, `source`, `ref`, `note` | When, as typed; the source and its citation, as in `events.yml`; what's assumed and how it was drawn |

## An engagement's reach (reach.yml)

A weapon's range, drawn as a ring round where the battery was: what it could reach, not what it hit. A list; each entry is
one ring. Hand-edited; the build writes
`rings` into `engagement.json`.

| Field | Meaning |
|---|---|
| `id`, `label` | A short key; a label |
| `of` | Whose weapon (us, de, ...); required |
| `actor` | A participant id, optional: whose weapon |
| `at` | A `positions.csv` id, placed: the ring's centre |
| `weapon`, `range_yd` | The weapon as the record or the manual names it, and its range in yards as the manual prints it (horizontal, to the tracer's burn-out or the fuze), never a range worked out by us |
| `basis` | `reported` (the battery's place and weapon both in its own records), `inferred` (the weapon from another record, a sister battery's or the battalion's), `assumed` (the place assumed, near the unit it defended) |
| `source`, `ref`, `note` | The manual and its page, cited as in `events.yml`; what's assumed |

## positions.csv columns (boats/*/patrol-N/, ships/*/)

One file per war patrol, or per ship: the same columns for both.

| Column | Meaning |
|---|---|
| `source` | Which part of the record the row is from (the values are below) |
| `ref` | Contact or attack number as the report numbers it |
| `date`, `time`, `zone` | Exactly as typed. `zone` is the Navy's zone letter (below) |
| `lat_raw`, `lon_raw` | Exactly as typed, in degrees and minutes (`19-26N`; a ship's diary may type tenths or seconds). `?` marks a digit that is illegible in the scan. Blank for a logged event with a time and no position |
| `page` | The cited page, e.g. `rg38-74802746/p16`: National Archives catalog item 74802746, object page 16 (`nara/rg38-74802746/p16.jpg` in the kit's cache after `tools/nara.py fetch`) |
| `note` | What the row is, in a few words: the contact, the port, what is assumed (a standard harbour position, "noon assumed") |
| `on_track` | `yes` = used for the track line. `no` = ship contacts, pre-departure readings, and fixes that contradict their neighbours |
| `lat_fix`, `lon_fix`, `date_fix`, `time_fix` | Corrections of evident typing errors in the originals. Raw values are never overwritten |
| `fix_note` | Why a correction was made, or why a fix is off the track |

`source`, in a submarine's war patrol report: `bt` (the bathythermograph, or density-layer, table, in GCT), `air`
(aircraft contacts: the boat's own position), `ship` (ship contacts: the **target's** position, never on the track),
`attack` (the torpedo attack data sheet), `gun` (a gun attack), `radar` (the radar countermeasures log), `noon` (the
daily noon position in the narrative), `narrative` (ports, arrivals, departures).

`source`, in a surface ship's war diary: `diary` (an 0800, 1200 or 2000 position from the diary's daily table),
`narrative` (ports, berths, departures and arrivals, with the diary's times), `event` (a logged event with a time,
usually no position), `air` and `attack` (an air contact or an attack logged the same way), `ship` (a ship contact),
`action` (a position typed on an Aircraft Action Report). Each ship's README says which she uses.

**Zone letters.** The letter is as typed; the hours are the Navy's *zone description*, the number added to local time
to give Greenwich Civil Time, so zone K is "−10" and local time is GCT + 10. In use in these files: Z (0, GCT); east
of Greenwich A (−1), G (−7), H (−8), I (−9, Tokyo time), K (−10), L (−11), M (−12); west of it N (+1), O (+2), P (+3),
Q (+4), R (+5), S (+6), T (+7), U (+8), V (+9), W (+10), X (+11), Y (+12); and the half-hour zones written with two
letters: IK (−9½), KL (−10½), LM (−11½), TU (+7½), UV (+8½), VW (+9½, Hawaii war time), WX (+10½), XY (+11½). Where a
record types a number and no letter, the letter is written from the number and the ship's README says so.

**GCT, GMT, UTC.** A record's own time standard is kept as typed (GCT in the Navy's tables). Times this dataset
computes (the `utc` in generated files, an engagement's `window`) are labelled UTC; at these records' precision of a
minute the three are the same clock.

Port positions (Pearl Harbor, Midway, Saipan, Guam, Ulithi) aren't in the reports; they are standard harbour
coordinates and say so in `note`. Arrival times not given in the report are set to noon and marked "noon assumed".

## depths.csv columns

| Column | Meaning |
|---|---|
| `date`, `time`, `zone` | As typed in the narrative (zone letters as in positions.csv). Where the report gives no time, the `quote` says how it was estimated |
| `event` | `dive` (submerged; depth not given), `surface`, `periscope` (back to periscope depth), `radar_depth`, `depth` (a depth ordered or reached), `passing` (a depth noted on the way down, not an order), `bottom` (sat on the seabed), `charges` (depth charges heard with no depth change), `quake`, `routine` (a summary like "submerged during daylight" covering several days without itemized times; the span ends at the date in the quote) |
| `depth_ft` | Depth in feet as logged |
| `charges` | Depth charges (or, Patrol 6, bombs) counted in that entry, as the captain tallied them |
| `proximity` | How close the captain judged them ("very close", "distant", ...) |
| `quote` | The captain's words, abridged with `...`; editorial notes in parentheses |
| `page` | Scan file, as in positions.csv |

Where a dive gives no depth, none is written. The kit's dive profile fills those gaps with labelled assumptions
(periscope depth, about 60 ft; each logged depth held until the next entry).

## layers.csv columns

One row per reading in the report's density-layer table (taken with the
bathythermograph on a dive, usually once a day around 2000-2100 GCT).

| Column | Meaning |
|---|---|
| `date`, `time_gct` | As typed (GCT). Summary notes with no time have `time_gct` blank |
| `iso_ft`, `iso_deg` | "Isothermal to feet / degrees": the warm surface layer is `iso_deg` °F down to `iso_ft` feet |
| `grad_ft`, `grad_deg` | "Negative gradient to feet / degrees": below that, temperature falls to `grad_deg` °F at `grad_ft` feet. |
| `page` | The table's page, as in positions.csv |
| `date_fix` | Same corrections as positions.csv where the date was mistyped |
| `note` | Pencilled circles on the scans (someone at headquarters marking strong layers), second isothermal lines, faded values |

## attacks.csv columns and attack_sheets.yml

The torpedo attack data sheets (the report's "Torpedo Attack Report Form", usually two pages an attack): the numbers
in `attacks.csv`, one row per torpedo fired, and the sheet's words in `attack_sheets.yml`, one entry per attack. A gun
attack has no rows.

| Column | Meaning |
|---|---|
| `attack` | The attack's `ref` in positions.csv (`Attack 3`) |
| `date`, `time`, `zone` | As typed on the sheet; repeated on each torpedo's row, like every per-attack value. A time typed with seconds stays so, `1616-32` (positions.csv has the minute, 1616); `zone` is blank where the sheet types none (positions.csv has it) |
| `tube` | The tube fired, as typed |
| `own_course`, `own_speed`, `own_depth` | The boat's, as typed (degrees true, knots, feet, or `Surface`). A course swinging while firing is the typed range, `050-069` |
| `target_course`, `target_speed`, `target_range`, `target_draft` | The target's, as typed (degrees true, knots, yards, feet). A range typed for two targets keeps the one aimed at; the words are in the YAML. A draft in feet and inches (`8'3"`) is blank here and typed in `target_line` |
| `track` | Track angle with its side joined, `62S` / `86P`; a track typed without a side (`0`) or as a mark (`*`) stays so |
| `gyro` | Gyro angle as typed: three figures (`162`), or right or left of the bow (`10R`); ½ is written `.5`. A footnote mark is dropped here and quoted in the YAML |
| `depth_set`, `power`, `torpedo` | As typed (`6'`; `High`, or `---` for "- - -"; the mark, `14-3A`, `18`) |
| `hit`, `erratic` | As typed in the table, even where the remarks disagree (the `note` says so). Blank where the sheet types the hits once for the salvo ("2 Hits"); that is the YAML's `hits` |
| `interval`, `since_first` | The sheet's "Firing Interval", seconds as typed, in the column that says what it means: `interval` where the sheet types the gap since the torpedo before (0, 8, 8, 8), `since_first` where it types the time since the salvo's first (0, 8, 16, 24). One or the other for a whole attack, never both. A `0` after the first row starts another salvo, whose own time the sheet doesn't give. A typed minute (`1-05`) is written in seconds; a dash stays as typed |
| `spread` | The sheet's "Type Spread" where it types the kind (`divergent`, `longitudinal`, `NONE`); the words are `spread` in the YAML |
| `offset` | Where the sheet types an aim for each torpedo instead: its offset from the point of aim, as typed (`1.5R`, `0`, `1L` in degrees; `225'Aft`, `25'fwd`, `MOT` along the target) |
| `page` | The sheet's first page, the same as the attack's row in positions.csv |

`attack_sheets.yml` keys, each as typed and left out where the sheet has none:

- on nearly every sheet: `attack`, `type_attack`, `description`, `sunk`, `damaged`, `determined_by`, `target_line` and
  `own_ship` (the data lines), `spread`, `sea`, `overhaul`, `remarks`, `page`, `table_page` (the torpedo table's page),
  and `note` (what couldn't be read, and where the sheet disagrees with itself or the narrative);
- where the sheet has them: `hits` (typed once for the salvo), `torpedo_detail` (the table's rows of marks, serials and
  settings in words), `heading` and `sheet_heading` (the form's own heading where it differs), `time`, `date`,
  `position`, `draft`, `gyro`, `track`, `tubes`, `fire_control`, `sunk_or_damaged`, `probably_sunk`,
  `damaged_or_probably_sunk`, `actuation_actual`, `footnote` or `footnotes`, `sheet_note`;
- `sheet` (where one attack is typed on several sheets, `2(a)`, each citing its own first page) and `column` (where a
  summary table numbers its columns apart from the attacks, `(4)` over `3(b)`);
- for a patrol whose report has no data sheets, the attack is written from the narrative and says so: `torpedoes`,
  `type_of_target`, `shot`, `performance_satisfactory`, `location`, `narrative`, and `basis` (where each value came
  from).

The kit's `tools/check_attacks.py` recomputes every torpedo's track from own
course, gyro and target course and lists the ones that disagree; a typed value is never changed to agree.

## A patrol's Japanese record (japanese.yml) and claims (claims.yml)

The other side of a boat's attacks, from Japanese wartime records (JACAR,
`tools/jacar.py`) and, where no primary record has been found yet, from
combinedfleet.com. Transcribed the same way as the patrol reports: as
written, with the page, and with an English translation beside the original.

### japanese.yml fields (a list, one entry per record)

| Field | Meaning |
|---|---|
| `id` | `J01`, `J02`, … within the patrol |
| `source` | `jacar:<reference code>` (primary; the image is at `https://www.jacar.archives.go.jp/das/image/<code>`) or `combinedfleet:<page>` (secondary, e.g. `Daiyoku_t` = combinedfleet.com/Daiyoku_t.htm) |
| `page` | Page of the JACAR PDF (`jacar/<code>/pNN.jpg` in the kit's cache after `tools/jacar.py fetch`) |
| `ship`, `convoy` | Romanized as in English-language references (convoy TAMA-17 = タマ一七, Takao→Manila) |
| `event` | `departed`, `joined`, `torpedoed`, `sank`, `rescue`, `attacked_no_damage`, `sub_sighted`, `status`, `weather`, `air_cover` (an order for, or report of, a convoy's air escort), `loss_list` (a monthly loss table) |
| `date`, `time`, `zone` | As written. Zone `I` (−9, Tokyo time), which the Imperial Japanese Navy and its convoys kept |
| `lat_raw`, `lon_raw` | Converted from 北緯一九度〇六分 to `19-06N` (the original is in `original`) |
| `original` | The Japanese text, abridged with `…` |
| `translation` | English translation of `original` |
| `note` | Context, and agreement or disagreement with other sources |

A patrol's `claims.yml` pairs an attack with a Japanese record: `attack` (`ref` in positions.csv), `record` (a
`japanese.yml` id), `relation`, `note`. An attack can be another boat's, written `<boat>/<patrol>:<ref>` (e.g.
`ss-384-parche/1:Attack 2`). `relation` is `hit` (the attack caused that
record), `miss` (same moment, no damage), `probable` (time and place point to
this attack, but another boat is credited or was attacking too), `possible`
(times fit, but more than one attack could explain the record), or `no_loss`
(a claimed sinking with no matching entry in the Japanese loss list).

A pairing whose record is a loss carries, where JANAC lists it, `janac`: a list, one entry for each ship JANAC
lists for that loss, whoever it credits, as printed (`janac` in SOURCES.yml). Where the record has a ship damaged
that was lost later, the entry is JANAC's for that later loss, and its `note` says it was not this attack. Several
pairings with one record share their entries through a YAML anchor (`- &tosei {...}`, then `janac: [*tosei]`).

| Field | Meaning |
|---|---|
| `ship`, `date`, `type`, `tons` | As the list prints them (`type` as its "Type of Vessel"; `tons` gross for a merchant ship, standard for a warship) |
| `lat_raw`, `lon_raw` | The list's location, as printed (`19-26N`, `118-45E`) |
| `agent` | For a submarine's credit the boat the appendix names (`BANG`); otherwise the list's agent (`Army Mine`, `Navy Carrier-Based Aircraft`) |
| `probable` | `true` where the list prints the agent with an asterisk ("*Probable Agent"), else `false` |
| `ref` | The list's page: `janac:4/pN` (merchant losses) or `janac:3/pN` (naval losses) |
| `appendix` | The appendix's page for a submarine's credit: `janac:6/pN` |
| `note` | Ours, where needed |

`build_engagement.py` checks the fields and both pages; the engagement page shows the entry as a column of its own in
the Sources view, a postwar assessment beside the records. The pairing's `note` keeps the argument (where JANAC
disagrees with the records, and why); the credit itself is in `janac`, not repeated in the note.

## A convoy (convoys/<id>/convoy.md)

The convoy as a whole, in YAML front matter, and in the body which values are reported, secondary or inferred. An
empty value means not recorded; `(inferred)` or `(secondary)` after a value labels it.

| Field | Meaning |
|---|---|
| `convoy`, `name_ja` | Its name, romanized and as written (TE-04, テ04) |
| `plain` | What it was, in a line, in our words (a six-ship Yulin–Moji convoy carrying iron ore) |
| `from`, `to`, `via`, `sailed`, `arrived` | Ports and dates as the records give them |
| `size` | How many ships, as a record counts them |
| `cargo` | The convoy's, in a few words |
| `attacked_by` | Patrols, as `<boat>/<n>` |
| `sources` | Each `jacar:<code> pN` (or another citation) with a comment saying what it gives |
| `route` | Its way through the nodes of the kit's `reference/lanes/lanes.yml`, in order (the one file a convoy needs from outside this repository). No lane is traced from a chart yet, so every waypoint is assumed, and each says why |
| `voyage` | Stops and known points, Tokyo time: `at` (`YYYY-MM-DD HHMM I`, or the day), `place` (a lanes node), `event` (`sailed`, `joined`, `arrived`), `words`, `source`, `basis`, `approx` |
| `ships` | Who was in it, below |

Each entry in `ships` is one ship, merchant or escort, from a record that names it in the convoy. Her own events
(torpedoed, sank, rescue) stay in the patrol's `japanese.yml`; this is who was in the convoy, what each carried and
where it was bound.

| Field | Meaning |
|---|---|
| `ship` | Romanized as in English-language references |
| `role` | `merchant`, `escort`; `designated rescue ship`, `oiler` or `transport` where the record says so |
| `number` | Its number in the convoy (第十番船 = 10), if a record gives it |
| `from`, `to` | Dates in the convoy (sailed or joined; arrived, left or sank); left out if not recorded |
| `cargo`, `cargo_t`, `cargo_for` | What it carried, metric tons as written, and where it was to be landed, as the record says. Left out means not recorded, not "empty" |
| `fate` | Lost or hit in the convoy, with the `japanese.yml` entry |
| `source`, `page` | The record (`jacar:<code>`) and page |
| `basis` | `reported` (the record says it), `secondary`, `inferred` |
| `note` | The words read, and anything assumed |
| `sil`, `sil_basis` | Her silhouette (an id in `silhouettes/silhouettes.yml`, or a kind: `cargo`, `tanker`, `escort`, `gunboat`, `destroyer`), and what the plate is to her: `own`, `class` (her class's plate lists her), `class, assumed: ...` (it doesn't name her), `representative` (a type standing for her) |

## US radio intelligence (frupac.yml)

The National Museum of the Pacific War's Fleet Radio Unit Pacific map
collection (846 overlays, mid-1943 to 1945, on UNT's Portal to Texas History)
plots what US radio intelligence knew of Japanese shipping, day by day, in
pencil. `tools/frupac.py` finds the maps for a ship or a date. The zoom
viewer (`https://texashistory.unt.edu/ark:/67531/<map>/m1/1/zoom/`) serves
full-resolution tiles and the notes are legible there; the plain page images
are only ~1500 px wide. The collection is CC BY-NC-ND, so the maps are linked
and read in place, never copied.

### frupac.yml fields (a list, one entry per note)

| Field | Meaning |
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
The kit's `tools/check_crossrefs.py` prints each note against its attack in UTC.

**In an engagement:** the kit's `tools/build_engagement.py` reads a tracked boat's `frupac.yml` like her
`japanese.yml`. Every note whose `date` and `time` (zone I assumed) fall in an engagement's window becomes an entry of
it, with `actor: FRUPAC`, `of: us`, `basis: assumed` and the zone assumption in its `note`; the note's own `event` word
is kept beside the engagement's kind. FRUPAC is a source about the convoy, not a participant. The mapping of event
words, and how the pages show the notes, is in the kit's `guides/ENGAGEMENTS.md`.
