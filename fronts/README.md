# Fronts

The front line and the units as a dated situation map drew them: the army group's picture of a day, for the engagement
pages to draw under their own records. Context, not the units' positions: a symbol stands in its unit's area, and the
line is the front as the staff drew it at the map's hour.

## HQ Twelfth Army Group, 7–17 March 1945

HQ Twelfth Army Group's daily situation maps, 1:1,000,000, each "to accompany G-3 report no. …: situation as of …1200 Mar
1945" (SOURCES.yml `loc-12ag`). All eleven days of the Remagen engagement (`engagements/remagen-1945-03-07/`) are traced:
7, 9, 11, 13, 15 and 17 March first, by hand and tool together; 8, 10, 12, 14 and 16 March then by five agents working
from the skill, a day each, and reviewed (the sides checked, every doubtful stretch looked at, the labels' qualifiers read
again on the first six days):

| Map | Sheet | G-3 report | Symbols (listed) |
|---|---|---|---|
| `12ag-1945-03-07` | [ict21276](https://www.loc.gov/resource/g5701s.ict21276/) | 275 | 39 |
| `12ag-1945-03-08` | [ict21277](https://www.loc.gov/resource/g5701s.ict21277/) | 276 | 58 |
| `12ag-1945-03-09` | [ict21278](https://www.loc.gov/resource/g5701s.ict21278/) | 277 | 54 |
| `12ag-1945-03-10` | [ict21279](https://www.loc.gov/resource/g5701s.ict21279/) | 278 | 58 (6) |
| `12ag-1945-03-11` | [ict21280](https://www.loc.gov/resource/g5701s.ict21280/) | 279 | 55 (7) |
| `12ag-1945-03-12` | [ict21281](https://www.loc.gov/resource/g5701s.ict21281/) | 280 | 64 (7) |
| `12ag-1945-03-13` | [ict21282](https://www.loc.gov/resource/g5701s.ict21282/) | 281 | 58 (7) |
| `12ag-1945-03-14` | [ict21283](https://www.loc.gov/resource/g5701s.ict21283/) | 282 | 63 (12) |
| `12ag-1945-03-15` | [ict21284](https://www.loc.gov/resource/g5701s.ict21284/) | 283 | 55 (14) |
| `12ag-1945-03-16` | [ict21285](https://www.loc.gov/resource/g5701s.ict21285/) | 284 | 55 (14) |
| `12ag-1945-03-17` | [ict21286](https://www.loc.gov/resource/g5701s.ict21286/) | 285 | 47 (16) |

The sheets run in order, ict21269 + the day and report no. 268 + the day, each read on the sheet's title. Only the part of each sheet between Grevenbroich and the
Moselle is traced, about 6.4 to 8.0 E and 50.15 to 51.1 N, where the towns the fit uses lie.

How to trace another day: the skill `trace-situation-map` (the kit's `.claude/skills/`), all through `tools/trace_front.py`.
Each map has three files:

- `<map>-gcps.csv` (hand-checked, or matched): the 20 town rings the scan is fitted to. `x`, `y`: the ring's centre on the
  full scan (about 6670 x 5975); `read`: how it was found; `lat`, `lon`: the town today, from OSM Nominatim (`query`).
  On 7 March each ring was read by eye, or detected (the ring's enclosed paper, nearest the place the other towns
  predict) and checked by eye. The later sheets are printings of the same base map: each town is found again by matching
  a patch of the 7 March sheet round its ring (`trace_front.py --gcps-from`), and the matches are checked against one
  another (they agree on one affine transform between the sheets to about half a pixel, 40 m); a town whose match doesn't
  agree (Gemünd on the 9th and the 13th, its ring under that day's overprint) is placed through the transform, and says so.
- `<map>-units.csv` (hand-read): the unit symbols, each as drawn. `x`, `y`: the box's centre on the scan; `of`: `us` (an
  open box) or `de` (a hatched box, the map's "Enemy"); `echelon`: the marks over the box (`x` a brigade, `xx` a
  division, `xxx` a corps, `xxxx` an army, `xxxxx` an army group, `xxxxxx` the "C in C"); `arm`: the mark in the box, read
  by the Army's symbols (FM 21-30): `infantry` (crossed), `armored` (an oval), `armored-infantry` (both), `airborne` (the
  curved mark), `unread`; empty for a headquarters; `label`: the number or name as written (`?` for a figure that can't be
  read; "262?" carries the map's own question mark); `unit`: the unit in `army/units.csv` or `army/relations.csv` the
  symbol is, where that is certain (the map's US "9" with the oval is the 9th Armored Division, `9ad`), else empty;
  `list`: `bridgehead` for a symbol in the map's list of the divisions facing the bridgehead (from 11 March: a bracketed
  column, then a box headed "BRIDGEHEAD N.-S."), listed and not placed, which a page shows as a list; `map`: the sheet.
  On the later sheets the boxes were found by their edges (a top and a bottom of one length, joined by short sides) and
  each read on a numbered sheet; the ones the finder missed (about a fifth, a box touching its number or a line) were read
  by eye on the sheet. Labels keep the map's qualifiers: "9(-)" (the division less some of its units), "1(+)" (with
  others attached), "(ELMS)" (elements): the tie to the kit's units reads the designation without them. 9 March writes
  "67" where the 7th and 11th write "62": as written. From 10 March the map lists the divisions facing the bridgehead, at
  first in a bracketed column, from 14 March also in the box "BRIDGEHEAD N.-S." with a second bracketed column joined by a
  line to the bridgehead's south side: all of them `list` `bridgehead`.
- `<map>.geojson` (generated by `tools/trace_front.py`, which says how to fetch the scans and rerun it): the front as
  LineStrings (`kind` `front`; `how` each was turned), each running so that the enemy's side lies to its left, and the
  units as Points (`kind` `unit`) through the fit; `fit_km` on each, and the map's `date`, `as_of`, `title`, `cite` and the
  traced `box` on the collection.

**The front is ticked on the map's own side.** The sheet's legend draws the front line with ticks on one side, and on
every stretch traced the US divisions lie on the ticked side (west of the Rhine at Bonn, inside the Remagen point, north
of the Eifel line by the 2nd and 28th Divisions). The pages tick it the same way.

How the front was traced. The fit: a 2nd-order polynomial to the 20 towns puts them 0.4–0.5 km rms from where they are,
0.7 km rms left out one at a time (worst 1.5–1.7 km, Gemünd): this map is drawn closely to its projection (a conformal
conic). The front is the sheet's heaviest, blackest line (the roads are grey), kept by its weight and thinned to a centre
line. On 7 March it was followed through waypoints read by eye. On the later days, where Third Army's corridors and the
bridgehead tangle it, the centre line is cut at its junctions into stretches (short heavy pieces kept: a corridor's head is
a short arc set apart from its sides by the division's own symbol), the army group boundary from Aachen is left out by a
box, and each stretch is turned by its ticks so that they lie on its right. A tick is counted only as the map draws one: a
short stroke as dark as the line (about 35 in every channel), attached to the line's edge and ending on paper within about
14 px. A darkness test alone was not enough: the Rhine's blue is dark at its edge, and on the lighter sheets (10 March) the
grey roads that run beside the front along the river (95–100) passed for ticks and turned whole reaches of it the wrong
way. Stretches that meet two at a time are links of one line, chained and turned together by their summed evidence; a
fork breaks the chain. The few short pieces that still couldn't be told (a corridor's head, a bend at a junction) were
each looked at on the scan, and are turned or confirmed by hand in the tool, with the reason; a blunt dead-end spur toward
Zell on 14 and 15 March, with no ticks either side, is left out. Each day's trace was checked on its overlay, and the
pages' side test (`Engage.frontSide`) run on the 20 towns of every day: the west bank US, the east bank German, a
corridor's inside US.

The line itself is about 1.5 km wide at this scale; with the fit, a point on the front is good to a km or two, and the
line is the staff's drawing at the map's hour, not a surveyed trace. Stretches are cut at their junctions, a gap of a few
hundred metres. The traced edges of the sheet are the least certain.

What the maps show. At noon on 7 March the front's point is about 8 km short of the Rhine at Remagen, about 3 km from
Lantershofen (the 60th Armored Infantry Battalion's station that morning), with the 9th Armored Division's symbol behind
it; the Ludendorff bridge was taken at about 1550 (the Remagen engagement's records), so that is the front a few hours
before. By the 9th the west bank is the army group's from Düsseldorf to Remagen, a small bridgehead lies across the river,
and Third Army's corridors reach the Rhine by Andernach. By the 13th the bridgehead runs from Königswinter past Linz; by
the 17th it is wider again, and the map lists ten German divisions and brigades facing it.
