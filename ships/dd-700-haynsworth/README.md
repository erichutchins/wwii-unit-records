# USS Haynsworth (DD-700): April 1945 war diary

`haynsworth/positions.csv` has the same columns as `patrol-N/positions.csv`, transcribed
from the ship's April 1945 war diary ([NARA 633422068](https://catalog.archives.gov/id/633422068),
8 pages, RG 38; scans download to the kit's cache as `nara/rg367-633422068/`). It is the only Haynsworth
war diary online; her other months are not in the NARA catalog. Her deck logs are online
only from 1957.

- `source` is `diary` (a 0800 / 1200 / 2000 position from the diary's daily table) or
  `narrative` (ports and berths, with the diary's times). Berth coordinates are not in
  the diary; Ulithi, Eniwetok and Pearl Harbor use standard harbour positions.
- `air`, `attack` and `event` rows are logged events with a time but **no position**. Their
  coordinates are left blank and `check_track.py haynsworth` places each one by interpolating
  between the fixes either side (shown as `~26-58N`, `assumed: true`, and labelled on the page).
  The 6 April kamikaze hit (`attack`) has no time in the diary: it is placed at 1255, after the
  1245 dog-fight and before the fires were under control (about 1300).
- Zones: -9 (I) at Okinawa, then the diary's clock changes through K, L, M, the date line (the
  diary repeats 23 April; the second 23rd is zone Y), X, WX, W, VW (Hawaii war time), V and UV.
- Corrections: 19 Apr 0800 longitude 156-37E → 154-37E and 20 Apr 0800 longitude 170-22E →
  160-22E (both typos that put the ship 30+ kn from its neighbours); a stray `8` after
  `21-22N` on 27 Apr; `200` for 2000 on 11 Apr.
- The speed screen is 25 kn plus 30 nm (`max_kts` in her `ship.yml`). The leg from 17 Apr 2000
  to 18 Apr 0800 averages 26 kn, just inside the tolerance; the scan reads 142-08E as typed.

View it at `site/patrols.html?ship=haynsworth`. Regenerate with
`uv run tools/check_track.py haynsworth --geojson`.
