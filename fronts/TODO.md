# Fronts: what is left (7 November 2026)

338 of the catalogue's 415 days (`sitmaps.csv`) are traced, reviewed and committed. This file lists the rest,
in the order worth doing, with what each needs. The method is in `guides/SITUATION-MAPS.md` and the skill
`trace-situation-map`; the keys a day's YAML takes are in `README.md`. One day is one reader agent; the reviewer
looks at the overlay before committing it, and adds a `# Reviewed:` line.

## 1. Days not yet traced (77)

### 11-17 March 1945: redo on the whole sheet (7 days, committed but partial)

These were first read for the Remagen engagement only: towns matched to 7 March's 20 hand-read rings, traced only
within their spread. 7-10 March are redone on the whole sheet; carry on day by day from 10 March.

- Per day: back up the three files; `--gcps-from` the day before (once, never piped); set `gcps_from`; copy the
  day before's boxes (moved by the median offset of the nearest towns) and checks; test the boxes with a run with
  none, and drop any that hold ticked front (Rhine-ink boxes go stale once the front reaches the river).
- Default cutoff (70) has held on 5-10 March; try `dark: 80`-`90` only if the Scheldt arcs come out in pieces.
- Each day has a units file the GeoJSON carries (don't change it; from 10 March some symbols are
  `list: bridgehead`). Check the symbols' count and labels are unchanged and give the largest move.
- Compare with the old reading in the Remagen window (about 6.6-7.6 E, 50.0-51.0 N).
- After each: `uv run tools/build_engagement.py`, and load `engagement.html?e=remagen-1945-03-07` in a browser
  (no console errors). Commit the engagement's JSON with the day.
- Watch the Remagen bridgehead: 9 March draws a rounded bulge east of the Rhine, 10 March a heavy line hugging the
  east bank to Linz. Trace what each sheet draws.

### 18-20 March 1945 (3 days, B11)

Never traced. Do them after 17 March's redo, matched to it, the same way.

### 18-23 June 1944 (6 days, B01)

The middle of June. These sheets' front is drawn thin and pale, and its teeth run into the line, so the
stretch method traces only half of it. Use hand waypoints (`runs:`), as on 6-17 and 24-30 June:

- Read every waypoint afresh on gridded 2x-4x crops of the bare scan (a 50 px grid labelled every 100 px),
  every 50-150 px and at every bend, enemy on the left. Waypoints shifted from the day before sit 10-30 px off
  the ink when the line has moved.
- Radius 4 with `dark: 110` works on most days; use 3, or 2, where the tool says "no ink between" (thin
  stretches; 17 June needed 2 for the Utah corridor's north face, 24 June 2 with `dark: 170`). The tool bridges
  about 40-60 px: where a symbol covers the line or its ink breaks into specks, end the run and start another.
- With runs, keep only the title, SECRET and legend boxes.
- Neighbours: 17 June (the Utah lodgement a corridor west toward Barneville, the coast reached 18 June) and
  24 June (the main line from the Orne to the west coast, and a ticked line round Cherbourg from the Hague to
  the Montebourg marsh). Cherbourg's ring tightens 19-25 June.
- Check the overlay along every reach on crops no wider than about 800 px.

### 10 September 1944 (1 day, B10)

A double sheet: two 1:1,000,000 plates pasted on one scan, each with its own graticule (`bases.yml`). The tool
fits one transform per day, so read each half's crossings as its own base from its own margins
(`sources/fronts-work/bases/B10-margins.txt`) and trace the halves apart. 6-28 September draw no ticked front
on the B09 sheets, so check first whether this sheet draws one at all; if not, it is an empty front, like its
neighbours.

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
