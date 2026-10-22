# USS Haynsworth (DD-700): war diaries, February to April 1945

`haynsworth/positions.csv` has the same columns as `patrol-N/positions.csv`, transcribed
from the ship's war diaries for February 1945 ([NARA 139903592](https://catalog.archives.gov/id/139903592),
8 pages), March 1945 ([NARA 139968200](https://catalog.archives.gov/id/139968200),
11 pages) and April 1945 ([NARA 633422068](https://catalog.archives.gov/id/633422068), 8 pages), RG 38;
scans download to the kit's cache as `nara/rg367-<id>/`. Her other monthly diaries, November 1944 to
January 1945 and May to October 1945, are in the catalog too and not yet transcribed (`../../inventory.yml`). Her deck logs are
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
- March: the 24 March table is typed identical to the 25th's, though the narrative has the group off Okinawa until 2000 that day, so the 24th's rows are kept as typed with `on_track=no`. On 21 March the third row is typed 2400, not 2000: kept as typed, and written as 0000 on 22 March in the fix columns so the track can read it.
- February: the diary types "Zone description -10" on 1 Feb and no clock change after it, so the whole month is K, including the days at Ulithi (139E) and off Honshu (141E). The table starts on 10 Feb (the 1 to 9 Feb entries are berths in Ulithi Lagoon, written as port rows with the standard harbour position and the diary's times, and 10 Feb's 0800 row, "Berth 417", the same). Two table entries were checked on the scan: the 10 Feb 1200 position (07-52N 140-00E) is 35 kn from Ulithi and is kept as typed with `on_track=no`, since the right digit can't be told from the page; and the 15 Feb 2000 longitude 141-21E is 36 kn from the 1200 fix and is read as 144-21E in `lon_fix` (the latitude and the next fix fit that). Events with a time (the picket boats sunk on 16 Feb, the Iwo Jima air alerts, the 25 Feb rescue) are `event` and `air` rows placed by interpolation, as in March.
- Corrections: 19 Apr 0800 longitude 156-37E → 154-37E and 20 Apr 0800 longitude 170-22E →
  160-22E (both typos that put the ship 30+ kn from its neighbours); a stray `8` after
  `21-22N` on 27 Apr; `200` for 2000 on 11 Apr.
- The speed screen is 25 kn plus 30 nm (`max_kts` in her `ship.yml`). The leg from 17 Apr 2000
  to 18 Apr 0800 averages 26 kn, just inside the tolerance; the scan reads 142-08E as typed.

View it at `site/patrols.html?ship=haynsworth`. Regenerate with
`uv run tools/check_track.py haynsworth --geojson`.
