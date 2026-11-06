---
title: The Remagen bridge, 7-17 March 1945
short: Remagen · 7-17 March 1945
eyebrow: III Corps' after action report
theater: europe
clock: A
window: {from: 1945-03-07T13:00Z, to: 1945-03-17T15:00Z}
# the map's base: today's relief and the Rhine; the front and the units as the 12th Army Group drew them at noon, each
# day of the window
relief: remagen
fronts: [12ag-1945-03-07, 12ag-1945-03-08, 12ag-1945-03-09, 12ag-1945-03-10, 12ag-1945-03-11, 12ag-1945-03-12,
  12ag-1945-03-13, 12ag-1945-03-14, 12ag-1945-03-15, 12ag-1945-03-16, 12ag-1945-03-17]
participants:
  - id: 9ad
    name: 9th Armored Division
    of: us
    kind: army
    unit: 9ad
    note: its Combat Command B took the bridge
  - id: 60aib
    name: 60th Armored Infantry Battalion
    of: us
    kind: army
    unit: 60aib
---

The 9th Armored Division's Combat Command B finds the Ludendorff railroad bridge at Remagen standing on the
afternoon of 7 March 1945 and crosses it; for ten days the Germans try to bring it down from the air, with
artillery, with V-2s and with swimmers, and on the afternoon of 17 March it collapses. Told here from one record so
far: Headquarters III Corps' after action report for March 1945 (its narrative,
its G-2 report and its engineer journal).

## Outcome

The Ludendorff bridge was "captured intact at 1550A" on 7 March by the 9th Armored Division
[[cite:iiicorps-aar-1945-03/p72]], and stood for ten days. The Corps' G-2 report counts "372 enemy aircraft made 223
raids in nine days on the bridge" [[cite:iiicorps-aar-1945-03/p73]]; the narrative gives the antiaircraft claims day by
day from 8 to 15 March, the Corps' totals for all its antiaircraft units together, the heaviest on 12 and 13 March
with 26 shot down each day [[cite:iiicorps-aar-1945-03/p40]] [[cite:iiicorps-aar-1945-03/p43]], none yet checked
against a German loss return. On 17 March V-2s fell near the bridges: the engineer journal has one officer and four
men killed and 33 wounded at 1155 [[cite:iiicorps-aar-1945-03/p122]]. At 1500 that afternoon the bridge, "weakened by
demolitions, artillery fire, near misses of bombs, and by heavy traffic", collapsed [[cite:iiicorps-aar-1945-03/p75]],
with two engineer companies working on it, about 90 casualties, and "no enemy action in the area" at the time
[[cite:iiicorps-aar-1945-03/p122]].

## The claims at the bridge

From 8 to 15 March the narrative gives, day by day, the raids on the bridge, the aircraft in them, and how many were
"destroyed" (or "shot down") and "damaged". These are **the Corps' totals for all the antiaircraft units at the
bridge together**: the narrative doesn't split them by battalion (only on 8 March does it name the battalions in the
same paragraph, the 482nd AAA AW Bn and the 413th AAA Gun Bn). They are claims, not losses: they have not been checked
against the Luftwaffe's loss returns, which are not online. From 11 March the report gives each day's period, 0600A
to 0600A the next morning; before that it says only "during the day". The aircraft types are the US side's
identifications (Stukas on 8 March, "ME-262s" on 14 March).

## The clock

The report's times carry the letter A (UTC+1), as in "1550A". The engineer journal's entries (pdf 122) are typed
without a letter ("171505 Mar"); they are taken as A, the report's own time, and say so.

## Reading the map

The bridge is placed at the G-2 report's reference "F6520" (pdf 72), decoded on the Nord de Guerre grid
(`tools/ndg_grid.py`): a four-figure reference names a 1 km square, and the point is its south-west corner;
OpenStreetMap's bridge lies about 250 m north-east of it, inside the square. Remagen and Erpel are drawn at their
centres (OpenStreetMap), and the heavy ponton bridge at the narrative's "wF673186" (pdf 38), decoded the same way.

Under them, the front and the divisions are the 12th Army Group's situation maps for 1200 on each day from 7 to 17
March, traced [[cite:loc-12ag/ict21276]]: the army group's own units and its intelligence picture of the Germans',
each symbol in its unit's area, not at a position (`fronts/README.md`); the account shows the first, and the records
depth steps through them. At noon on the 7th the map draws the front's point about 8 km short of the Rhine, near
Lantershofen, where the 60th Armored Infantry Battalion's task force had closed in at 0205
[[cite:eucmh60aib/1945-03]]; the bridge was taken that afternoon, so that map shows the morning, not the crossing.
From the 9th the maps draw the bridgehead, and from the 11th they list the German divisions facing it, which the page
shows as the map does, as a list. The 60th's dashed line is its own stations from 28 February, joined straight, to the
day shown.

## Sources and what's missing

The narrative's pages for 17-19 March are not in the scan (printed -41- onward; pdf 48 is a map and 49 a photograph),
so 17 March here is the G-2 section's and the engineer journal's. Still to find: the 9th Armored Division's, CC B's,
the 27th Armored Infantry Battalion's and the 14th Tank Battalion's own reports, and the antiaircraft battalions' and
groups' reports (claims by unit), all in NARA RG 407 and not online; and the German side: the Luftwaffe's loss
returns, the Wehrmachtbericht for these days, and the V-2 battery's firings. The German units on the ground are so far
only as the US records identified them from prisoners: the Corps' G-2 report (pdf 74, 77) and the 60th Armored Infantry
Battalion's report for 14 March. No German record is entered yet.

The folder's files, for anyone reading the records themselves:

Every entry cites its PDF page in `ref`, with the printed page in its note.
