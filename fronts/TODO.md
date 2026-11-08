# Fronts: what is left (8 November 2026)

365 of the catalogue's 415 days (`sitmaps.csv`) are traced, reviewed and committed. This file lists the rest,
in the order worth doing, with what each needs. The method is in `guides/SITUATION-MAPS.md` and the skill
`trace-situation-map`; the keys a day's YAML takes are in `README.md`. One day is one reader agent; the reviewer
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
- **check_fronts.py** (`uv run tools/check_fronts.py FIRST LAST`) has not been run across every committed range
  since the last days went in; run it over each month and look at what it flags.

## 3. Tool

- `dark:` (per-sheet grey cutoff) is in; it works both ways: higher for pale prints (June 1944, 4 March and
  21 and 27 November), lower for a heavy one (1 April 1945, `dark: 45`).
- Not done: joining a line where its ticks fuse with it and break it into pieces (the June sheets' trouble). Hand
  waypoints work around it; a fix in the stretch method would save reading them.
