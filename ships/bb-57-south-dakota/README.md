# USS South Dakota (BB-57): war diaries, November 1942 onward (in progress)

`positions.csv` has the same columns as `patrol-N/positions.csv`. So far it holds **1 November to 18 December 1942**,
transcribed from the typed war diary for 20 March 1942 to 28 February 1943
([NARA 78189543](https://catalog.archives.gov/id/78189543), 22 pages), pages 14 to 20, **January to August 1944**
(the typed monthly diaries NARA 78337817, 78361250, 78391388, 78435161, 78477472, 78513245, 78580035 and 78647682; see Notes by month) and **September to December 1944**
(NARA 139889516, one 42-page diary for the four months, all of it read). Every other month from
November 1942 to May 1945 is found in the catalog and listed in `../../inventory.yml`; none else is transcribed yet.

- `source` is `diary` (an 0800 / 1200 / 2000 position typed under the day), `narrative` (a departure or arrival
  with the diary's time, written with the standard harbour position; the diary types no berth coordinates) or
  `event` (the equator crossing, which has a typed longitude).
- The diary types its zone as plain numbers in the day's heading ("Zone -11", "Zone (plus) 9 (plus) 8"), and the
  letters are written from those: L (-11, Noumea), M (-12), X (+11, after the date line), W, V, U, T, S, R, Q
  (+10 down to +4, one change a day at 1300 or 1800 on the way to Panama). "Changed time zone ... at 1300" puts
  the 1200 row in the old zone and the 2000 row in the new. 12 to 16 November type no zone line: M is carried from the
  11th (assumed, said on the rows).
- The date line is crossed eastbound on 29 November: the diary types **29 November twice**, the first in Zone -12
  (M) and the second in Zone plus 11 (X). Both sets of rows carry the date as typed; the zone letters keep them in order.
- Seconds in the diary's positions (`-30"`, `-15"`, `-45"`) are written as fractions of a minute (`.5`, `.25`, `.75`) and
  said in the row's note.
- 18 December (arrival at the New York Navy Yard) types no time and no zone: noon and R are assumed in `time_fix`
  and `fix_note`. 15 to 17 December have no entries.
- **The night action of 14-15 November 1942 has no row.** The diary gives a 1200 position on the 14th, "Off Russel
  Island" at 2000 with no coordinates, and the action at 0018 on the 15th by reference to the action report. The
  ship went north toward Savo Island that evening and was back south by 0800 on the 15th, so a position interpolated
  between the fixes would be well away from where she was. The action report ([NARA 134006513](https://catalog.archives.gov/id/134006513),
  196 pages) is the place to get one.
- Before 1 November: 29 and 30 October (return from Santa Cruz to Noumea) are typed on p14 with positions and are
  not transcribed, because the work started at November. The one row taken from them is the 30 October 1415 mooring at
  Noumea, the anchor of the 31 October - 11 November stay (zone L assumed: the diary types Zone -11 from 31 October).
- The speed screen is 28 kn (`max_kts` in `ship.yml`); the diary's own speeds run to 26 kn.

## What is in the catalog for the rest of the range

Monthly war diaries ("USS SOUTH DAKOTA - War Diary", series 4697018), by catalog ID and pages:

| Month | NARA | Pages | What it is |
|---|---|---|---|
| Feb 1943 | 134088381 | 49 | handwritten log copies; pp. 1-24 are Brooklyn, in dry dock, no positions |
| Mar, Apr, May, Jun, Jul 1943 | 134160670, 134195102, 139749322, 134273752, 78132408 | 47, 43, 49, 46, 65 | not read |
| Aug 1943 | | | **not in the catalog** (searched) |
| Sep, Oct, Nov, Dec 1943 | 78199368, 136045167, 78249593, 78271510 | 69, 73, 100, 5 | not read |
| Jan 1944 | 78337817 | 10 | typed narrative; a 0800 / 1200 / 2000 table under each day; transcribed |
| Feb, Mar 1944 | 78361250, 78391388 | 8, 8 | typed; transcribed |
| Apr, May 1944 | 78435161, 78477472 | 11, 4 | typed; transcribed |
| Jun, Jul, Aug 1944 | 78513245, 78580035, 78647682 | 9, 3, 2 | typed; transcribed (Aug: dry dock, no positions to 25 Aug) |
| Sep to Dec 1944 | 139889516 | 42 | one diary for the four months; typed; all transcribed (pp. 1-42) |
| Jan, Feb 1945 | 139891872, 139900467 | 14, 13 | not read |
| Mar 1945 | | | **no monthly diary**; the report of operations 18 Mar - 11 May 1945 is NARA 77802097 (4 pp.) |
| Apr, May 1945 | 633438508, 101760567 | 23, 14 | not read |

Her action reports are separate items (Savo Island 134006513; Palau 78395988; the Marianas, Formosa and Philippines
operations and others, found by searching "SOUTH DAKOTA" in the same series) and carry their own track charts.

The map draws a straight line between consecutive fixes, so the untranscribed gaps (the whole of 1943, and the weeks after 18 Dec 1942 and before 1 Jan 1944) appear as long lines and count toward the page's distance figure; they are not her track. The page also shows 1 Nov 1942 - 31 Dec 1944 as one period, because a diary ship's page has one period.

View it at `site/patrols.html?ship=south%20dakota` (checked in light and dark mode, no console errors; the alias has a space). Regenerate with `uv run tools/check_track.py south-dakota --geojson`.

## Notes by month

- **January 1944** (NARA 78337817, pp. 3-10). In Havannah Harbor, Efate, to 18 January (the 18th's 0800 column types
  "Havannah Harbor" for its coordinates, so it is a narrative row with the standard harbour position). Task Group 37.2
  sailed for Funafuti, anchored there 1420 on 20 January, left on the 23rd, and joined Task Force 58 for Flintlock
  (the 30 January bombardment of Roi and Namur is in the narrative, with no row, because the ship manoeuvred between
  fixes). **Zone:** no zone line is typed for 16 to 20 January; M (-12) is carried from the 2 January entry ("1235
  (-12 time)") and said on the rows (assumed). **20 January is typed twice**: the first headed "(East Long.)" with a
  table, the second headed "(West Longitude)" with "At 0000 changed time to minus 12, west longitude date" and the
  anchoring at Funafuti. The rows keep both dates as typed; M is written for the first 20th and Y (+12) for the
  second and every row after it (assumed: the diary says only "minus 12" and "west longitude date"; the Y reading
  is the same clock with the date put back a day, as the February diary types "Zone plus 12 time" and the March
  diary skips 24 March in changing "from plus 12 to minus 11"). The diary's 23 January 0800 column is blank and the
  30 January 1200 column types "Off Roi Is." / "Kwajalein": no rows for them.
- **February 1944** (NARA 78361250). With Task Force 58 off Kwajalein 1 to 3 February, at Majuro 4 to 12 February
  (anchored 1849 on the 4th, underway 1549 on the 12th), then the Truk strike and the sweep toward the Marianas to
  25 February and back to Majuro on the 26th. Zone Y throughout (carried from January until the diary types "Zone
  plus 12 time" on 12 February). Seconds in the positions are written as fractions of a minute and said in each
  row's note (thirds rounded to two places: 10" = .17, 40" = .67). The 12 February 2000 position is typed as dead
  reckoning (D.R.). **15 February 1200 (10-49.5N 155-33.5E) is `on_track=no`:** read twice on the zoomed scan, the
  legs on either side need 46 kn and 28 kn; either the latitude or the longitude is a typing error and the scan does
  not say which, so no fix is made. The air strikes are in the narrative and have no rows.
- **March 1944** (NARA 78391388). Underway from Majuro 1027 on 22 March (Task Group 58.9 for the Palau operation),
  the 22nd's 2000 position typed as a single line rather than a table. Zone Y (carried, assumed) to 23 March. **The
  diary types "At 1900 we set the clocks back one hour and at 2400 set the clocks ahead 24 hours to agree with minus
  11 zone time"**: 24 March is skipped, 25 March onward is L (-11). A clock one hour back of plus 12 is plus 13, which
  the zone table does not have, so the 23 March 2000 row is written as Y (assumed; at most one hour, about 17 nm,
  of position). Equator crossed 1355 on 25 March at the typed longitude (event row, latitude 00-00 from the words).
  The Palau strikes of 30 and 31 March, the air attacks of the 29th and 30th and the 31 March sinking of a freighter
  are in the narrative with no rows.
- **April 1944** (NARA 78435161, pp. 1-11). No zone line is typed for 1 to 4 April: L (-11) is carried from March
  (assumed, said on the rows). Task Force 58's Woleai strike was on 1 April (narrative only); the ship fuelled on
  2 April and steamed east. **5 April is typed twice**: "(minus 11)" with a table (L), then "(plus 12)" with a second
  table (Y), after "At 0000 set clocks ahead 23 hours, repeating 5 April, to conform to plus 12 zone time" (the date
  line, crossed eastbound; both dates are kept as typed and the zone letters keep the rows in order). Anchored at
  Majuro 1401 on 6 April (berth X-9) and underway 1211 on 13 April for the Hollandia operation ("Desecrate Two").
  **Clock changes at sea:** 14 April 2100 clocks back one hour "preparatory to changing to minus 11" (the three 14 April
  rows are before it, Y); "At 0000 advanced the clocks 23 hours, and dropped 15 April" puts 16 April in L, and 15
  April has no entry; 17 April 1830 clocks back one hour to minus 10 (K, from the 2000 row; K is carried to 28
  April). The 29 April heading types "(minus 11)", but the diary types no change from minus 10 on 28 April, so K is
  carried through the 28th and L starts at the first 29 April row (said on the row); "At 1700 set all clocks ahead one
  hour to conform to minus 12" makes the first 29 April 2000 row M; "At 0000 set clocks back 24 hours, repeating
  Saturday 29 April, to conform to zone plus 12" puts the second 29 April, and 30 April, in Y. Hollandia strikes
  21 to 23 April, the Truk strikes 29 and 30 April, and the many fuelling, radar-contact and aircraft-shot-down
  entries are in the narrative with no rows. The legs between the 2000 and next 0800 rows on 21 to 24 April are
  7 to 25 nm: the narrative shows the force steaming away and back (courses 330 to 175, 335 to 180) on the strike
  stations. **28 April 0800 longitude** is typed `146° 43' 60"E`; the seconds read 60 twice on the zoomed scan (00"
  in the neighbouring cell), which is one minute, written 146-44E; a 00" would be 146-43E, under 1 nm different,
  so no fix is made. 30 April 0800 to 2000 covers 72 nm in 12 hours (6 kn) under strike operations.
- **May 1944** (NARA 78477472, pp. 1-4). The 1 May bombardment of Ponape (fire opened 1543, ceased 1648, with
  Battleship Division 9 on its own course at 5000 to 10000 yards) is in the narrative with no row because the ship
  manoeuvred between fixes. Y is carried from 29 April (no zone line typed in May until 19 May, assumed, said on
  the rows). Task Force 58 went on to Majuro: anchored 0904 on 4 May in berth 81. 5 to 14 May is a single entry
  ("Remained at anchor"), with a berth shift to the AA firing area on 9 May (underway 1155, back 1625) and no
  coordinates. Underway 1020 on 15 May for firing exercises, anchored again 1641 on 16 May (berth 81); the 16 May
  table types 0800 and 1200 only. 17 to 31 May is a single entry of berth shifts to the AA firing area (18, 25 and
  30 May), with no rows; "On 19 May set clocks ahead 23 hours to agree with minus 11 zone time" (Y to L) is typed
  but no position follows it.
- **June 1944** (NARA 78513245, pp. 1-9; the catalog title is the month's war diary). Anchored at Majuro (berth 81) to
  6 June; underway 0827 for Operation Forager with Task Group 58.7 (Battleship Division 9 detached to Task Group 58.3 on
  8 June). The 13 June bombardment of Saipan (main battery fire 1042 to 1726, 369 rounds of 16-inch and 1270 of 5-inch
  as the diary types it) and the air attacks of 15 to 19 June are in the narrative with no rows, because the ship
  manoeuvred between fixes; the Battle of the Philippine Sea (the bomb hit at 1050 on 19 June, the chase west on
  20 June) is the same. Three **burials at sea have typed coordinates** and are event rows: 19 June 1701 (14-05-15N
  144-04-00E), 20 June 1010 and 21 June 1720; the names the diary lists are not transcribed. Left Task Group 58.7
  on 23 June for Task Group 58.2 and anchored at Eniwetok at 0915 on 27 June (berth 421); underway for Pearl Harbor
  at 1800 and cleared the atoll 1840. **Zones:** the June diary types no zone line until 26 June (0030 "changed to
  -11 zone time"), then "At 2400 changed to minus 12" on the 27th, "At 2400 set all clocks back 24 hours to plus 12"
  on the first 29th and "At 2400 changed to plus 11" on the second. **29 June is typed twice** (the date line,
  eastbound; both dates kept as typed, M for the first and Y for the second, X from 30 June). L is carried from
  the May diary's 19 May line for 6 to 9 June (assumed). The 26 June line shows the clocks were not at -11 before
  it, so they had been put to -10 on the way to the Marianas, but that change is not typed anywhere: K is written
  from 10 June, the first day the ship was west of 157.5 E, and for every row to 25 June (assumed; if the change was
  earlier or later, a row is one hour, about 17 nm, out). **10 June 2000 (14-16N 158-15.25E) is `on_track=no`:** the longitude is typed 158
  and read clearly, the ship was steaming 250 degrees all day, and the neighbouring fixes (154-17E at 1200; 149-39E
  at 0800 on the 11th) make the legs 29 and 41 kn; a value near 152 would fit but the scan does not say which digit,
  so no fix is made. 10 June 0800's longitude minutes are blotted (read 27). Blank columns: 6 June 0800 and 1200,
  13 June 1200, 15 June 2000, 19 June 1200.
- **July 1944** (NARA 78580035, pp. 1-3; the catalog title reads "7/1-31-44"). At sea for Pearl Harbor (20 kn),
  moored at pier F-3 at 1024 on 2 July, underway 1253 on 3 July for Puget Sound with passengers (Task Group 12.4,
  with two destroyers; departure from Pearl Harbor 1339), anchored in berth C, Sinclair Inlet, 1612 on 10 July,
  moored at pier 3A of the Navy Yard 0706 on 11 July and in dry dock from 2100 (resting on the blocks 2145), where she
  stayed to 31 July (a range entry, no times, no positions). **No zone line is typed in July:** X (plus 11, from
  the 2400 line on 29 June) is carried on every row (assumed); the ship passed through the plus 10, 9 and 8 zones
  on the way, so the letters are probably wrong by up to three hours for most of the month and are said so on each
  row (the legs are checked at 13 to 20 kn with the letters as written). Berth positions are the standard
  harbour positions (Pearl Harbor 21-21N 157-58W as in the later diaries; Puget Sound Navy Yard, Bremerton, 47-33N
  122-38W, placed here since no diary types one). **1 July 0800 (19-16.75N 167-04.33W) is `on_track=no`:** the 1200
  fix is 199 nm and 50 kn away and the previous 2000 fix 83 nm in 12 hours (the diary types 20 kn); the latitude fits and
  the longitude degrees (about 164 to 165 would fit) are the probable error, but the scan does not say which digit.
  **2 July 0800 (24-49.5N 154-34.58W) is `on_track=no`:** the narrative has Oahu 30 miles away at 0600 and the ship
  moored at 1024, about 200 nm from this position, which is almost the same place as the 4 July 0800 fix; no
  correction is made. The 5 July purple hearts and the 3 July passengers are narrative only.
- **August 1944** (NARA 78647682, pp. 1-2). 1 to 21 August is one entry (dry dock number 2, Puget Sound Navy Yard,
  repair of the 19 June battle damage; flooded and shifted to pier five on 6 August; Rear Admiral Gatch's visit 1201
  on 11 August; 21 August post-repair trials, 28.1 kn on the pit log, and anchored in Sinclair Inlet), with no
  positions; 22 to 26 August at anchor and then, on 25 August, Task Unit 12.5.1 left Puget Sound for Pearl Harbor
  (about 2230 leaving the Strait of Juan de Fuca). Rows pin the ship at the Navy Yard at 1201 on 11 August (a typed
  time) and at the mouth of the Strait at 2230 on 25 August (the time is typed; **the position is placed, an estimate
  at about Cape Flattery**, since the diary types none); between them the track is drawn straight across Puget Sound
  because no other time is typed. Tables 26 to 31 August, one per day (31 August 0800 only; arrived Pearl Harbor
  that day, no time or berth typed, so no row). Zones: the diary types no zone line before 27 August, when it says
  "Set clocks back one hour to plus nine time zone" with no time, which puts the earlier clocks at plus 8 (U, assumed
  for 25 and 26 August; the July and early-August rows are X by carrying, so the letters are not continuous); the
  27 August 0800 and 1200 rows are U and the 2000 row V (assumed, as the hour is not typed), and "Set clocks back
  one-half hour to plus nine and one-half" on the 30th, also untimed, puts the 30 August 2000 row and 31 August in
  VW. The 29 August 0800 longitude seconds are typed 14" (the others 15"), and 30 August 2000 is typed 04" and 05"
  (written .07 and .08).
- **September 1944** (NARA 139889516, pp. 1-8; the one folder holds the war diaries for September, October, November and December 1944, 42 pages). At Pearl Harbor (berth Fox Three, Ford Island) to 5 September; underway 0707 on 6 September with two destroyers as escorts for exercises off Oahu (fixes 6 to 8 September), moored again at Fox Three on the evening of the 8th (passed buoy 1 at 1734; no mooring time typed). Underway 1009 on 11 September with Task Unit 12.5.1 for Seeadler Harbor; propeller damage was found, she turned back, moored, shifted to dry dock 1 at 1430 on 12 September (drydocked 13 to 15 September), backed out at 1204 on 16 September for post-repair trials and moored at berth How Three at 1037 on 17 September. Underway 0857 on 18 September for Seeadler Harbor, Manus (Task Unit 12.5.1; speed of advance 16 knots). Orders from Commander Third Fleet on 24 September changed the destination to Ulithi: the ship entered the lagoon through Mugai passage at 1100 on 30 September, "the first United States battleship to enter the harbor", and anchored in berth seven (no anchoring time typed). The table format is the same as 1944 earlier (0800 / 1200 / 2000, degrees, minutes and seconds); some days type only one or two columns (8, 11 and 16 September). **Zones:** the diary types "Keeping plus 9 1/2 Zone Time" on 1 to 5 September, so VW is written from 6 to 18 September (carried, assumed, said on the rows); then "At 1900 set all clocks back one-half hour to plus 10" (18 September, W), "At 1830 ... back one hour to plus 11" (20 September, X), "At 1830 ... back one hour to plus 12" (21 September, Y) and, on 22 September, "At 2400 set all clocks ahead to minus 12 zone time", and the diary goes from 22 to **24 September** (23 September is not typed; the date line crossed westbound, so the clocks go from Y to M with the date jumping). Then minus 11 at 1830 on 25 September (L) and minus 10 at 1830 on 27 September (K). The 1830 changes put the 2000 row in the new zone and the 0800 and 1200 rows in the old. **30 September 1200 (04-41.75N 142-22.5E) and 2000 (06-19N 141-00E) are `on_track=no`:** both are exact repeats of the 29 September 1200 and 2000 fixes, and the narrative has the ship entering Ulithi at 1100 on the 30th and at anchor after; a carried-over table, the true positions not typed, so no fix is made. The 30 September 0800 fix and the 1100 entry row (standard harbour position) are the last good positions. Two legs are odd but under the 28-kn screen and are left as typed: **20 September 2000** (14-05.75N 170-36.75W) is 38 nm north of the 1200 fix while the ship was steaming southwest, and the leg from it to 21 September 0800 is 297 nm in 12 hours (24.7 kn, against 15 to 18 kn on the other legs); and **29 September 0800** (03-58.25N 144-05.5E) is reached at 10 kn from the 28 September 2000 fix and left at 27.9 kn for the 1200 fix. The digits were read on the zoomed scan (20 September) or the half-page scan (29 September); a typing slip in a degree digit may be behind either, but the scan does not say which, so no fix and no `on_track=no` is made.
- **October 1944** (NARA 139889516, pp. 11-23; 1 to 31 October, the 25 to 31 October paragraph below). At anchor in berth seven, Ulithi, 1 to 3 October; underway 0805 on 3 October in company with Task Force 34 and Task Groups 38.2 and 38.3 to avoid typhoon weather ("sorties"), back in the lagoon at 0953 on 4 October (berth seven; the Aldebaran rammed her port side at 1130, damage superficial). On 5 October Commander Battleship Division 9 broke his flag in the ship; on 6 October she reported to Commander Task Group 38.3 and sailed at 1653 (channel buoys cleared 1750). The 6 and 7 October table is one table headed "Positions: 2000 6 Oct. 0800 7 Oct. 1200 7 Oct. 2000 7 Oct."; fuelling at 19-00N 139-00E on 8 October. **Zone:** the diary types "Keeping minus 9 zone time" on 1 October, so I (-9) is written for every October row (assumed, said on the first rows), although the 30 September rows are K and no change to minus 9 is typed; if the clocks were not changed, the October rows are one hour (about 16 nm) out in UTC. The air strikes on Okinawa (10 October), Formosa (12 to 14 October; the torpedoing of the cruiser Canberra about 1830 on 13 October, the seven torpedo planes of 14 October) and the Philippines are in the narrative with no rows, because the ship manoeuvred between fixes; the one coordinate the diary types for an event is the position of the first launching on 10 October (24-24.5N 128-52E at 0535, an event row). 12 October's narrative on p16 has no table. **7 October 0800 (11-42.25N 134-34E) and 9 October 2000 (12-31.5N 132-37.5E) are `on_track=no`:** the first is about 5 degrees of longitude west of its neighbours (a 57-kn leg to the 1200 fix), the second needs 510 nm in 8 hours from the 1200 fix; the scan was read twice and the digits are clear, so the errors are the diary's and the scan does not say what they should be; no fix is made. 7 October 2000 types a question mark after the longitude and 11 October 2000 an exclamation mark after the latitude (both written as typed without the mark). **21 October 1200 to 2000** is 234 nm in 8 hours (29.2 kn on the rows) as typed, at the edge of the screen; the digits were read on the zoomed scan and the fix is left as typed. 19 to 22 October at sea east of the Philippines; 23 October 0610 Washington, Alabama and a destroyer division left to join Task Group 38.4; 24 October the loss of the Princeton and the air attacks from 1300 are in the narrative.
- **October 1944, 25 to 31 October** (pp. 21-23). Tables 0800 / 1200 / 2000 for each day, I carried (assumed) as before; the 25 October table is at the bottom of p21 and the day's narrative runs on to p22. The action of 25 October and the days after it are in the narrative with no rows, because the ship manoeuvred between fixes. The 31 October 2000 fix is 13-11.75N 133-21E, and 1 November begins the November diary.
- **November 1944** (NARA 139889516, pp. 26-34; the month's diary begins on p26, 1 November). Zone I (-9) is typed on 1 November ("Keeping Minus 9 Zone time") and every row is I. On 1 November the ship is in Task Group 38.4; **2 November** the diary types only a 2000 position, and the narrative has her detached at 0233 to meet Task Group 38.1 off Ulithi, entering Mugai channel 0531, anchored in berth A-6 at 0652 and underway again 1223 (two narrative rows, standard Ulithi harbour position). 4 November the ship joins Task Group 38.3 (Rear Admiral Sherman) at 1150; **5 November** the 0613 strikes on Luzon, the 1339 air attack on the group and, at 1604, a burial at sea with typed coordinates (an event row, 16-10.5N 124-02.05E). **The three 4 November fixes are `on_track=no`:** the 0800 fix (15-22N 122-58E) is 544 nm from the 3 November 2000 fix (13-02N 132-00E), the 1200 and 2000 columns are the same as the 5 November 1200 and 2000 columns, and the 5 November table fits the burial position; the scan was read twice and the digits are clear, so the error is the diary's and no fix is made (the 5 November rows carry the repeat in their notes). 7 November longitude 1200 is typed with "N" for "E" (read E); 14 November 1200 has an apostrophe for the degree sign in the longitude (read 124 degrees). 10 November: the group turned for a striking position east of Samar at 26 knots (Washington and North Carolina dropped out in heavy seas); 12 and 13 November fuelling, 13 and 14 November strikes on Luzon (bogies, no direct attack on this ship); 15 November retiring toward Ulithi; anchored in berth 26 at 0728 on 17 November (a narrative row), Vice Admiral W. A. Lee's flag shifted to the ship on 18 November, underway 0458 on 22 November (no table 17 to 21 November); 24 and 25 November strikes east of Luzon (25 November 1214, kamikaze attack, Essex damaged); fuelling and anti-aircraft practice 26 to 30 November (the Commanding Officer was relieved at sea by transfer to the destroyer Cotten on 30 November). The 28 November 1200 and 2000 longitudes (130-21.75E, 131-32.25E) are identical to the 27 November ones, and the 29 November 0800 longitude (132-06.25E) to the 28 November 0800 one, while the latitudes differ; as typed, within the screen, and left without a mark.
- **December 1944** (NARA 139889516, pp. 35-42; p35 is the title page). 1 December types "Keeping minus 9 zone time", then I until "At 1800 on 4 December set all clocks ahead one hour to minus ten" (K for the rows after it, none until the 11th), and "At 0800 set all clocks back one hour to conform with minus nine zone time" on 11 December (the 0714 underway row is K, the 1200 and 2000 rows I). 2 December types 0800 and 1200 only; anchored in berth 6, Ulithi, at 1908 (entered Mugai channel 1608); 3 to 11 December at anchor (a range entry), with a change of commanding officer on 9 December. **11 December 1200 and 2000 are `on_track=no`:** the table (10-58N 140-25.5E; 11-22.25N 138-32.5E) is repeated exactly in the 30 December table, where it fits the day's courses and the 31 December fix, and on 11 December the 2000 position is 383 nm and 32 kn from the 12 December 0800 fix; no fix is made. 11 to 13 December fuelling and simulated air attacks; **14 to 16 December** one table with an 0800 / 1200 / **2200** column set for the three days (written as 2200 with the single-table fact in each note), the 24-hour strikes on Luzon airfields in support of the Mindoro landings (narrative, no rows); 17 December fuelling postponed for weather (rough weather bill 1257); **18 December Typhoon Cobra**: the diary has the vessel within twenty miles of the centre at about 1430, rolling to 22 degrees, minor weather damage, "steamed generally to the southeast"; the three 18 December fixes are typed and read; 19 to 20 December fuelling and the attempt to return to Luzon (retired eastward at 0155 on the 20th); 21 December Task Group 38.3 starts back to Ulithi at about 0900; 22 December fuelling (Kankakee); 24 December entered Mugai channel at 1115 and anchored in berth 4 at 1152, with "At 1200 set all clocks ahead one hour to conform to minus ten" (the anchoring row is I, the 0800 row I; 24 to 30 December is a range entry at anchor with no positions). **30 December**: underway 0630 with Task Group 38.1 (flagship of the Commander Battleship Squadron Two and Task Force 34, Operation Order 18-44) and "At 0730 set all clocks back one hour to conform to minus nine" (underway row K, the 0800 / 1200 / 2000 rows I); the 1200 and 2000 columns repeat the 11 December table (see above) and are kept. 31 December: 0800 / 1200 / 2000 typed; exercise "Moosetrap" 0830 to 1115; the 31 December 0800 to 1200 leg is 26 nm and the 1200 to 2000 leg 86 nm against a fleet speed of 22 knots in the narrative, under the screen and left as typed. **Two legs are odd but under the screen and left as typed:** 16 December 2200 to 17 December 0800 (242 nm in 10 hours, 24.2 kn, the high-speed retirement after the Luzon strikes) and 2 November 2000 to 3 November 0800 (287 nm, 23.9 kn, the high-speed run west from Ulithi).
