# Fronts: what is left (8 November 2026)

365 of the catalogue's 415 days (`sitmaps.csv`) are traced, reviewed and committed. This file lists the rest
(and, in section 3, the days whose unit symbols are not read), in the order worth doing, with what each needs.
The method is in `guides/SITUATION-MAPS.md` and the skill `trace-situation-map`; the keys a day's YAML takes are in `README.md`. One day is one reader agent; the reviewer
looks at the overlay before committing it, and adds a `# Reviewed:` line.

## 1. Days not yet traced (50)

### 10 September 1944 (1 day, B10)

A double sheet: two plates pasted on one scan, each with its own graticule (`bases.yml`). The left plate (FUSAG
"SHEET 1", 5W-1E, 46-50N, graticule every 30', the title and legend) covers Brittany; the right (the 12th Army
Group plate, about 3-8E, 48-51N) covers the Scheldt to the Rhine. Looked at 8 Nov 2026: the right plate draws no
ticked front, like 6-9 and 11-28 September, but the left one does: a ticked perimeter round Brest (about x 680-1140,
y 2340-2600, ticks north and east, the US side) and a ticked arc round Lorient (about x 1800-1990, y 3195-3280).
The tool fits one transform per day, so this day needs a base for the left plate (towns from its own crossings,
`sources/fronts-work/bases/B10-margins.txt` plus interior crossings read with `tools/sheet_towns.py crops
--graticule`) and the two perimeters traced on it, with the right plate recorded as drawing no front. Nothing is
written for it yet.

### 8 June - 26 July 1945 (49 days, B15): empty fronts, by the rule below

The post-war sheets: B14's map with the state boundaries overprinted in red. 20 May - 7 June are done. From 8 May
the ticked line is the line of contact with the Soviet armies, not a front against the enemy. Through 31 May the
sheets tick it (only its ticked stretches are traced; the heavy EAST BOUNDARY TWELFTH A.G. drawn bare or with x
marks is the army group's boundary and is boxed). From 1 June the whole line is drawn bare and the legend has lost
its ENEMY sample (it keeps a FRONT LINE sample). **Eric's decision (8 Nov 2026): from the first sheet with no ticked
line of contact, the post-war days are empty fronts** ("no front drawn"), with what is drawn written in the notes.
Ticked bands the sheets don't explain (a band from the Radstadt corner to Liezen, and outlines running south from
Heiligenblut into Carinthia) are boxed and noted on those days, not traced.

- Carry on forward from 7 June (`12ag-1945-06-07.yml`), matched day to day. Read each sheet's
  title (top right: `--title 4100 150 1900 1000`), its legend (bottom left; the sheets sit at different heights),
  and look at 4x along the whole line for ticks. If a sheet ticks the line of contact again, trace its ticked
  stretches as on 31 May.
- An empty day: move the day before's boxes by a fit to the towns (the shift varies across these sheets by up to
  20-30 px; an affine or quadratic fit of the matched towns works), check them against a run with no boxes, add
  any needed until a run traces nothing.
- These go fast (5-7 minutes a day for a reader).

## 2. Known weak spots in committed days

Each is written in its day's YAML.

- **The post-war bands, 22-31 May 1945.** Those days trace the ticked bands in the Tauern and running into
  Carinthia (and the Radstadt band's ticked edge) as part of the line of contact, because the line was ticked and
  the legend had its front-line and enemy samples. From 1 June the same kind of band is boxed (Eric's rule). Worth
  a look at what the bands mark (the British zone in Carinthia?) and whether 22-31 May should keep them.
- **20 May 1945's review** says all of B15's days are like it (a ticked line of contact); that holds only to 31 May.
- **Gaps on the post-war line**: the start above Dömitz under the red border (29 May); the Elbe at Wittenberge and
  the Radstadt band's second heavy line left as unsure runs (25-31 May).
- **15 March 1945**: about 60 px untraced at Saarlautern and 45 px at Neuwied (radius 5); **19 March** about 60 px
  west of Ottweiler where the army-group boundary crosses.
- **Open-end artefacts.** On the June 1944 sheets, towns past the open end of the line read on the wrong side,
  most often 0.5E 49.5N (and sometimes 1E 49N or 49.5N) east of the Seine mouth reading own, though German-held.
  The side test weighs the nearest runs, and nothing separates those towns from the sea. Ostend reads either way
  against the open Walcheren arc in November 1944 for the same reason.
- **1 July 1944**: traced by the stretch method at radius 5, `dark: 130`; about 16 km untraced (the west tip
  below Carteret and the Vire above St-Lô). Redo with hand waypoints like 30 June.
- **Gaps where the map's own line breaks**: east of Quettehou on 24-25 June 1944 (3-6 km, the ink in specks);
  the dotted west corner at St-Sauveur on 16 June 1944 (about 1 km); about 5 km at Saarlautern on 10 March 1945,
  where a boundary joins the front.
- **7 June 1944**: four short bends untraced (about 8-10 km of some 38); its teeth hang inland, the reverse of
  every other sheet, and all six stretches are flipped. Could be redone with waypoints.
- **The breakout, 25 July - 15 August 1944: redo before its symbols are read** (section 3, row 4). The B01 and B02
  sheets to 4 August were traced at radius 3 and leave large gaps: about 108 km of some 134 on 30 July, about 112 km
  on 2 August. Redo them across the whole sheet, trying radius 4 and 5 as on 7-17 March 1945, with hand waypoints
  where the ticks break the line. Not at a fixed radius: the 1:500,000 sheets from 5 August (B03, B04) draw the line
  finer and were traced deliberately at 2-4 (each day's YAML says why). The redo is also where the arrows and open
  ends below (section 4) are first recorded: 2 August boxes the 4th Armored's arrow out as "not front", and its line
  stops at the bay north of Avranches with Third Army already through.
- **check_fronts.py** (`uv run tools/check_fronts.py FIRST LAST`) has not been run across every committed range
  since the last days went in; run it over each month and look at what it flags.

## 3. Unit symbols: 391 days not read, 11 read only in part

The unit symbols are read on 24 of the 415 days (`<map>-units.csv`; columns in `README.md`). Across the whole sheet
on thirteen: 16-23 December 1944, 21 and 28 January and 4, 11 and 18 February 1945 (176 to 226 symbols a day). Within the Remagen window only (about
6.4-7.8 E, 50.0-51.2 N; 39 to 64 symbols) on 7-17 March 1945, whose fronts are now traced on the whole sheet. Every
other day has its front (or an empty front) and no symbols. Fronts not yet traced (section 1) are marked below.

In the order to read them, following five units through the sheets: Company B, 313th Infantry (79th Division);
HQ Battery, 128th AAA Gun Bn; the 9th Armored Division, and in it the 19th Tank Battalion's Service Company
(`19tb-serv`; the battalion served under Combat Command A, `9ad-cca`); Battery D, 106th AAA AW Bn (their stations
are in `army/stations.csv`). The battalions and batteries aren't drawn on these sheets (below), so the division or
its combat command is as near as the maps come to them. Rows 1-4 finish the stretches where the units were close and
where an engagement is waiting on the symbols.

| # | Days | Base | Days to read | Front | The units |
|---|---|---|---|---|---|
| 1 | 12 January - 22 February 1945 (21 and 28 January, 4, 11 and 18 February read) | B11 | 37 | traced | the 128th AAA and the 9th Armored between Thionville and Metz; the 106th AAA in northern Alsace |
| 2 | 24 December 1944 - 11 January 1945 | B11 | 19 | traced | the 9th Armored after the Bulge, the 128th AAA at Nancy, the 106th AAA in northern Alsace; the Bulge engagement's frames show the front alone after 23 December until these are read |
| 3 | 26 June - 11 July 1944 | B01 | 16 | traced | the 313th Infantry in the Cotentin, the 128th AAA at Cherbourg |
| 4 | 25 July - 15 August 1944 (the front redone first, below) | B01-B04 | 22 | traced, with gaps | the breakout: the armour's arrows beyond the line, the 128th AAA from Cherbourg into Brittany |
| 5 | 7-17 March 1945, the whole sheet beyond the Remagen window | B11 | 11 | traced | the 9th Armored's combat commands in the bridgehead, the 128th AAA at Metz, the 106th AAA to Sarreguemines |
| 6 | 18 March - 5 April 1945 | B11, B12 | 19 | traced | the 9th Armored at Koblenz, the 128th AAA to Boppard, the 106th AAA through the Palatinate to the Rhine and the Main |
| 7 | 18 October - 15 December 1944 | B09, B11 | 58 | traced | the 9th Armored at Mersch, the 128th AAA at Nancy, the 106th AAA at Rambervillers and in northern Alsace |
| 8 | 6 September - 17 October 1944 | B09, B10 | 42 | traced, but 10 September not (section 1); to 28 September empty fronts | the 128th AAA at Toul and Nancy, the 106th AAA to Épinal |
| 9 | 6 April - 8 May 1945 | B12, B13, B14 | 33 | traced | the 9th Armored to Leipzig and Bavaria, the 128th AAA at Grafenwöhr and Plattling |
| 10 | 12 July - 24 July and 16 August - 5 September 1944 | B01-B08 | 34 | traced | the 128th AAA across France; the 106th AAA in southern France from 15 August, if the sheets reach it |
| 11 | 23 February - 6 March 1945 | B11 | 12 | traced | the 128th AAA at Metz, the 9th Armored toward the Rhine |
| 12 | 6-25 June 1944 | B01 | 20 | traced | none of the five ashore yet |
| 13 | 9 May - 26 July 1945 | B14, B15 | 79 | traced to 7 June (from 1 June empty fronts); 8 June on not (section 1) | the occupation |

(The catalogue has no sheet for 12 November 1944.)

- One day is one reader agent, reading the symbols as drawn (the skill `trace-situation-map`; the December and
  January days are the worked examples). Give it the day before's units file to match against, and ask for the
  whole sheet.
- The box finder misses a third to half of a whole sheet's symbols (the British boxes, most corps and armies);
  the readers read those off the overview's tiles. Every US "9" is magnified (the 9th Armored's oval), the enemy's
  panzer and paratroop marks read, and a map's boxes or lists of unplaced divisions recorded with `list:` (the words
  in `README.md`; a new marking gets a new word there first).
- A whole sheet takes a reader far longer than a front (150-230 symbols), so the order above matters.
- After 8 May 1945 the symbols are the occupation's, not a battle's: say so in the day's notes.

### Reading closer (from 8 November 2026)

- **A divided division, part by part.** Where a division is drawn in parts, read each part as drawn ("9(-)", "CCA",
  "CCB", "CCR", a task force, "(+)" and "(-)"), and tie a combat command to its own key where the kit has one
  (`9ad-cca`). On the 24 days read so far the US symbols are divisions and above only (no brigade, combat command or
  battalion box), and the 9th Armored is drawn whole or as "9(-)"/"9(+)"; look for its parts above all on
  16 December 1944 - 11 January 1945 and 7-17 March 1945.
- **Fill `unit` wherever a symbol is certainly a unit the kit has** (`army/units.csv`, or a key `army/relations.csv`
  uses). The read days tie the corps, the armies, the 1st Division and the 9th Armored; they leave the 79th
  Division's "79" and "79(+)" untied although `79th-division` is in `relations.csv`. Tie it on the days already read
  and on every new one, and the same for any other division that gets a key.
- **Keep every reading checkable**: the box's x,y, the label exactly as drawn, and in the notes every symbol that is a
  list entry rather than placed (`fit_km` is on each point in the GeoJSON). Where a followed division hasn't moved
  since the day before, say so in the day's YAML ("the 9th Armored's oval where it was on the 20th"), so a quiet
  stretch reads as a reading, not a gap.
- **List words** (`README.md`): `marseilles`, `le-havre`, `cherbourg`, `westwall`, `bracket`, `arrow`,
  `dieppe-rouen`, `upper-alsace-pocket` and `upper-rhine-area` say what each box is on the sheet; not yet how a page
  should show each one. Add a line to each when a page first draws them.

## 4. Tool

- `dark:` (per-sheet grey cutoff) is in; it works both ways: higher for pale prints (June 1944, 4 March and
  21 and 27 November), lower for a heavy one (1 April 1945, `dark: 45`).
- Not done: joining a line where its ticks fuse with it and break it into pieces (the June sheets' trouble). Hand
  waypoints work around it; a fix in the stretch method would save reading them.
- **Not done: new kinds in the GeoJSON**, each with its key in `README.md` before a day uses it:
  - `kind: arrow`, an attack arrow, traced tail to head with the unit it is labelled with, instead of boxed out as
    "not front". On the breakout days the arrows are the only mark of the armoured spearheads beyond the line.
  - `kind: boundary`, the army group, army and corps boundaries with their labels (TWELFTH/SIXTH and the rest),
    instead of only boxed out, so a page can say whose ground a unit's area lay in (the 12th/6th Army Group seam in
    Lorraine and Alsace above all).
  - `open_ends: [{lon, lat, note}]` in a day's YAML, where the line stops short and the sheet shows its own side
    beyond it (2 August 1944 at the bay north of Avranches), so a page can draw "line not drawn beyond here". Today
    these are only comments.
- **Not done: `as_of_iso`** beside the typed `as_of` (the sheets type "2400 HRS 10 JULY 1944", "1200 HRS 16 DECEMBER
  1944", "281200 JAN. 1945"), so pages needn't each parse the forms. Write it as a local time with no offset, and keep
  the zone apart as an assumption to be checked: the sheets type no zone letter, and one offset won't do for the whole
  run if, as is likely, the armies in France kept British double summer time (UTC+2) in the summer of 1944 and one
  hour less from the autumn. Not checked: confirm from the army group's own dated records before any offset is written.
