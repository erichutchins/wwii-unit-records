# USS Haynsworth (DD-700): war diaries, November 1944 to June 1945, and where she was before

`haynsworth/positions.csv` has the same columns as `patrol-N/positions.csv`, transcribed
from the ship's war diaries for November 1944 ([NARA 78694496](https://catalog.archives.gov/id/78694496),
7 pages), December 1944 ([NARA 139832917](https://catalog.archives.gov/id/139832917),
9 pages), January 1945 ([NARA 139846605](https://catalog.archives.gov/id/139846605),
12 pages), February 1945 ([NARA 139903592](https://catalog.archives.gov/id/139903592),
8 pages), March 1945 ([NARA 139968200](https://catalog.archives.gov/id/139968200),
11 pages), April 1945 ([NARA 633422068](https://catalog.archives.gov/id/633422068), 8 pages), May 1945
([NARA 140048093](https://catalog.archives.gov/id/140048093), 2 pages) and June 1945
([NARA 101733725](https://catalog.archives.gov/id/101733725), 2 pages), RG 38;
scans download to the kit's cache as `nara/rg367-<id>/`. Her other monthly diaries, July to October 1945, are in the catalog too and not yet transcribed (`../../inventory.yml`). Her deck logs are
online only from 1957.

- `source` is `diary` (a 0800 / 1200 / 2000 position from the diary's daily table) or
  `narrative` (ports and berths, with the diary's times). Berth coordinates are not in
  the diary; Ulithi, Eniwetok and Pearl Harbor use standard harbour positions.
- `air`, `attack` and `event` rows are logged events with a time but **no position**. Their
  coordinates are left blank and `check_track.py haynsworth` places each one by interpolating
  between the fixes either side (shown as `~26-58N`, `assumed: true`, and labelled on the page).
  The 6 April kamikaze hit (`attack`) has no time in the diary: it is placed at 1255, after the
  1245 dog-fight and before the fires were under control (about 1300).
- Zones: the March diary types no zone letter, only "Zone description -10" (K) on 1 March and "retarded all clocks to -9 zone time" (I) at 0400 on 14 March; the letters are written from those. In April, -9 (I) at Okinawa, then the diary's clock changes through K, L, M, the date line (the
  diary repeats 23 April; the second 23rd is zone Y), X, WX, W, VW (Hawaii war time), V and UV.
- November: the diary types no zone letter, and its only zone line, "Time zone + 4." on 1 Nov, does not fit Hawaii; VW (+9½, Hawaii war time) is written for the whole month, as in December, which types "Time Zone + 9½" at Pearl Harbor (an assumption, said on the first row). The month is exercises out of Pearl Harbor with DesDiv 123 (Kahoolawe shore bombardment, torpedo and AA drills), then repairs and fighter-director installation in the Navy Yard from 18 Nov. The table gives 0800 / 1200 / 2000 on 1 to 4, 6, 7, 9 to 13 and 16 to 18 Nov; 5, 8, 14 and 15 Nov have no table, and 19 to 30 Nov is one entry with no times, so no rows (the 5 Nov berth shift and the 14 Nov berth shift are narrative port rows). Berths in the 2000 table rows are written as port rows with the standard Pearl Harbor position. The 4 Nov 0800 position (20-30N 158-00W) repeats the 3 Nov 2000 one while the narrative has her anchored off Kahoolawe at 0706 and under way at 0718, so the table contradicts the narrative: kept as typed with `on_track=no`, no fix. The 6 Nov 0800 latitude 22-16N is 44 kn from the harbour 75 minutes after leaving the berth; 21-16N (one digit) fits the departure and the 1200 fix, so it is read in `lat_fix`. The 10 Nov table is typed the same at 0800, 1200 and 2000 (and 12 Nov 0800 repeats the 10th's) and is kept as typed, since the positions are near Kahoolawe and no speed is impossible. On 13 Nov the narrative moors at Berth K-1 at 1848 and the table's 2000 row says K-8; both are the harbour position. The 16 Nov collision with LOWRY while backing (0706), the 17 Nov drone kill (1445) and the 18 Nov order to leave the formation (1405) are `event` rows placed by interpolation.
- December: the diary types a time zone in plain numbers ("Time Zone + 9½" for 1 to 12 Dec at Pearl Harbor, then a clock change each day at 1600 as the ship steamed west), and the letters are written from those: VW (+9½), W (+10), WX (+10½), X (+11), XY (+11½), Y (+12), then M (-12) from 2400 on 20 Dec, LM (-11½), L (-11), KL (-10½) and K (-10, 27 Dec). The diary calls each of these changes "retarded", though the ship was going west. It types no change to -9 before 1 Jan, when the January diary says "Zone description -9", so K is kept to 31 Dec. The date line is crossed at the 2400 change on 20 Dec by dropping Thursday 21 Dec: there is no 21 Dec entry, and the 22 Dec fixes follow the 20 Dec ones by 12 hours of real time. 1 to 12 Dec, 15 Dec, 28 Dec (after the 0851 entry) and 29 Dec are entries with no times and no table, so no rows. Two table positions are kept as typed with `on_track=no` and no fix, since the speeds show a digit is wrong but not which: 14 Dec 0800 (21-50N, 43 kn from the harbour) and 16 Dec 0800 (18-21N, 180 nm from the harbour 29 minutes after getting underway). The 25 Dec table is typed the same as the 24th's (the 2000 latitude 11-35N for 11-36N), though the ship was under way for Guam (the 24 Dec 2000 fix to the 26 Dec 0800 one is 15 kn), so its rows are kept as typed with `on_track=no`, as in March. The diary records no weather in December (the ship was in Hawaiian waters and then crossing the Central Pacific, not with Task Force 38 in Typhoon Cobra). 14 Dec 1840 (a change of command) and 30 Dec 1100 (joining T.G. 38.2) are `event` rows placed by interpolation. The diary's Eniwetok berths (J-6, H-2) and the Ulithi berth (111) are written with the standard harbour positions.
- January: the diary types no zone letter, only "Zone description -9" on 1 Jan, so I (-9) is written from then to the clock change in the diary's last entry: at 0710 on 26 Jan "set all clocks ahead one hour to -10 zone time" (K from there; the 0647 and 0710 rows are typed before the change, so I). The January table runs 1 to 25 Jan (T.G. 38.2: Formosa and Luzon strikes, the Camranh Bay strike of 12 Jan, the South China Sea sweep and Hong Kong/Hainan strikes of 16 Jan, the Ballintang Channel exit on 20 Jan, Formosa and Okinawa Jima strikes of 21-22 Jan); 26 Jan has no table, only the entry into Ulithi (0647, port position) and mooring in berth 414 (1828); 27 to 31 Jan is one entry with no times, so no row. The 3 Jan 0545 "vicinity of 22 30 N, 122 50 E" is a narrative position, not a table fix, and is kept with `on_track=no`. The 12 Jan "rejoined the screen at 9907" has a 0 struck over the 9 on the scan and is written 0907. The 22 Jan 2000 to 23 Jan 0800 leg is 25.3 kn (304 nm), at the speed screen's edge, and is kept as typed.
- March: the 24 March table is typed identical to the 25th's, though the narrative has the group off Okinawa until 2000 that day, so the 24th's rows are kept as typed with `on_track=no`. On 21 March the third row is typed 2400, not 2000: kept as typed, and written as 0000 on 22 March in the fix columns so the track can read it.
- February: the diary types "Zone description -10" on 1 Feb and no clock change after it, so the whole month is K, including the days at Ulithi (139E) and off Honshu (141E). The table starts on 10 Feb (the 1 to 9 Feb entries are berths in Ulithi Lagoon, written as port rows with the standard harbour position and the diary's times, and 10 Feb's 0800 row, "Berth 417", the same). Two table entries were checked on the scan: the 10 Feb 1200 position (07-52N 140-00E) is 35 kn from Ulithi and is kept as typed with `on_track=no`, since the right digit can't be told from the page; and the 15 Feb 2000 longitude 141-21E is 36 kn from the 1200 fix and is read as 144-21E in `lon_fix` (the latitude and the next fix fit that). Events with a time (the picket boats sunk on 16 Feb, the Iwo Jima air alerts, the 25 Feb rescue) are `event` and `air` rows placed by interpolation, as in March.
- May and June: the May diary types its zones as plain numbers: "Time zone in use + 8½" and a change to + 8 at 0100 on 1 May, + 7½ at 0100 on 2 May, + 7 at 0930 on 3 May, so U, TU and T are written from those (the 1 May rows are U, as the change was at 0100). Alone from Pearl Harbor to Mare Island, the table's fixes run 1 to 3 May (speeds 17 to 22 kn, 0 too-fast legs). The 3 May 1200 entry is the words "San Francisco Bay", so it is an `event` row placed by interpolation; the 2000 entry reads "Pier #3, Mare Island Ammunition Depot" while the narrative moors her at pier #35 at 1445 with no later move, so it is kept as a port row and the discrepancy is said on it. Mare Island's berths (the Navy Yard, the ammunition depot) all use one standard position (38-04N 122-16W), Hunters Point 37-43N 122-22W; neither is in the diary. 5 to 31 May and 1 to 26 June are one entry each ("battle damage repairs and alterations", zone "t7"), so no rows; the 28 June compass calibration and the 30 June 24 rounds of 5"/38 AAC have no time and no row. The diaries' port-to-port legs on 27 to 30 June are port rows with the typed times, so their implied speeds (1 to 3 kn) only show the berths are a few miles apart.
- Corrections: 19 Apr 0800 longitude 156-37E → 154-37E and 20 Apr 0800 longitude 170-22E →
  160-22E (both typos that put the ship 30+ kn from its neighbours); a stray `8` after
  `21-22N` on 27 Apr; `200` for 2000 on 11 Apr.
- The speed screen is 25 kn plus 30 nm (`max_kts` in her `ship.yml`). The leg from 17 Apr 2000
  to 18 Apr 0800 averages 26 kn, just inside the tolerance; the scan reads 142-08E as typed.

View it at `site/patrols.html?ship=haynsworth`. Regenerate with
`uv run tools/check_track.py haynsworth --geojson`.

## Before November 1944: no war diary found

Commissioned 22 June 1944 (the muster roll's first sheet, `rg24-127361253/p0005`). A catalog search on 2026-10-23 (titles
with Haynsworth and DD700; the war diaries series 4697018) finds no war diary or action report for June to
October 1944: the first is November. What does place her is the **muster roll's forwarding sheets** (NARA
[127361253](https://catalog.archives.gov/id/127361253), "Haynsworth (DD-700), 6/22/44-1/1/49", RG 24, 409 pages), which type the place each
quarterly roll was forwarded from. They place the ship only to a port, and only on the day of the paperwork, so none is a row in
`positions.csv` (the track would draw a point at a harbour for a date the ship may have left):

| Roll | Forwarded | From (as typed) | Page |
|---|---|---|---|
| Commissioning, 22 Jun 1944 | 1 Jul 1944 | c/o Fleet Post Office, New York, N.Y. | `rg24-127361253/p0005` |
| 30 Jun 1944 | 4 Jul 1944 | Brooklyn Navy Yard, New York, N.Y. | `rg24-127361253/p0003` |
| 30 Sep 1944 | 11 Oct 1944 | San Pedro, California | `rg24-127361253/p0059` |
| 31 Dec 1944 | 16 Jan 1945 | Outside Cont. U.S. | `rg24-127361253/p0111` |

So she was at the New York yard at commissioning and still there on 4 July, and at San Pedro (Los Angeles harbour) around 11 October,
three weeks before the November diary has her at Pearl Harbor. Nothing in the sheets dates the passage between (shakedown, the
Atlantic, the Panama Canal). The rolls are crew rosters, so nothing past the forwarding sheets is read or copied here; the Reports of
Changes name the places men were received from and sent to, a further source for dates (not read).
