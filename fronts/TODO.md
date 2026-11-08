# Fronts: what is left (8 November 2026)

344 of the catalogue's 415 days (`sitmaps.csv`) are traced, reviewed and committed. This file lists the rest,
in the order worth doing, with what each needs. The method is in `guides/SITUATION-MAPS.md` and the skill
`trace-situation-map`; the keys a day's YAML takes are in `README.md`. One day is one reader agent; the reviewer
looks at the overlay before committing it, and adds a `# Reviewed:` line.

## 1. Days not yet traced (71), and two to redo

### 16-17 March 1945: redo on the whole sheet (2 days, committed but partial)

These were first read for the Remagen engagement only: towns matched to 7 March's 20 hand-read rings, traced only
within their spread. 7-15 March are redone on the whole sheet (8 Nov 2026); carry on from 15 March.

- Per day: back up the three files; `--gcps-from` the day before (once, never piped); set `gcps_from`; copy the
  day before's boxes (moved by the median offset of the nearest towns) and checks; test the boxes with a run with
  none, and drop any that hold ticked front (Rhine-ink boxes go stale once the front reaches the river).
- Default cutoff (70) has held on 5-15 March; try `dark: 80`-`90` only if the Scheldt arcs come out in pieces. 15 March
  needed `radius: 5`: at 4 the line broke at Linz and Saarlautern and Metz read enemy. Look at flips on 4x-5x crops.
- Each day has a units file the GeoJSON carries (don't change it; from 10 March some symbols are
  `list: bridgehead`). Check the symbols' count and labels are unchanged and give the largest move.
- Compare with the old reading in the Remagen window (about 6.6-7.6 E, 50.0-51.0 N).
- After each: `uv run tools/build_engagement.py`, and load `engagement.html?e=remagen-1945-03-07` in a browser
  (no console errors). Commit the engagement's JSON with the day.
- Watch the Remagen bridgehead: 9 March draws a rounded bulge east of the Rhine, 10 March a heavy line hugging the
  east bank to Linz. Trace what each sheet draws.

### 18-20 March 1945 (3 days, B11)

Never traced. Do them after 17 March's redo, matched to it, the same way.

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

### 21 May - 26 July 1945 (67 days, B15)

The post-war sheets: B14's map with the state boundaries overprinted in red. 20 May is traced (the base's first
day; `towns-B15.csv`). Carry on from it as the B14 lane did in May (whole sheet, the stretch method, boxes copied
and shifted, every shifted box checked against an unboxed trace because the scans differ in size). Read each
sheet's legend: the front line may give way to occupation or army-group boundaries, which are not front. Say what
each sheet draws and trace only a ticked line.

## 2. Known weak spots in committed days

Each is written in its day's YAML.

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
