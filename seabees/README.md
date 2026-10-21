# Seabees: naval construction battalions, 1942–1945

Where two Seabee battalions were, from their own records: the **20th Naval Construction
Battalion** from its forming at Norfolk in August 1942, through Nouméa, the split of 1943 (one half
to Woodlark and Kiriwina off New Guinea, the other to Vangunu, Viru Harbor and Rendova in New
Georgia), the Russell Islands, home leave, and Okinawa, until it was broken up there on 29 August
1945; and the **79th Battalion** in 1945, from Camp Parks to Saipan and Okinawa. Every row cites
its page (`ref`), in the forms listed in `../SOURCES.yml`.

| Unit | Records | Years |
|---|---|---|
| `20ncb` 20th Naval Construction Battalion | Muster rolls (NARA [190273312](https://catalog.archives.gov/id/190273312)), its Historical Information sheet, *Building the Navy's Bases*, *Marines in the Central Solomons* | 1942–1945 |
| `79ncb` 79th Naval Construction Battalion | Muster rolls ([190327559](https://catalog.archives.gov/id/190327559)), its Historical Information sheet | 1945 |

## Sources

- **Muster rolls** (NARA RG 24, series [594996](https://catalog.archives.gov/id/594996)): one file
  unit per battalion, about a thousand pages each. Every quarter a roll lists every man on board,
  and every month a Report of Changes lists the men received, transferred, re-rated or who died.
  **They rarely say where the battalion was.** The forwarding sheet of each quarterly roll gives a
  code name ("White Poppy" for Nouméa), a Navy number ("Navy 250"), or only "c/o FPO, San
  Francisco"; the transfers name the hospitals and bases men were sent to, which place the
  battalion near them. Navy numbers are decoded with the NHHC's
  [Navy Numbers](https://www.history.navy.mil/research/library/online-reading-room/title-list-alphabetically/u/us-navy-abbreviations-of-ww2/navy-numbers.html)
  list. Cited `rg24-<file unit>/pNNNN`, the catalog viewer's page.
- **Historical Information sheets** (`ncbhist-NNN/pN`): the Bureau of Yards and Docks' typed cards
  for each battalion, scanned by the Navy Seabee Museum: its embarkations (training center,
  advance base depot, date ready, date left, destination) and a log of its monthly reports and
  the letters and dispatches about it. These carry most of the dates of sailing and arriving.
  The left-margin date is when the entry was logged; rows use the dates in the entry itself.
  Download with a browser User-Agent: `https://www.history.navy.mil/content/dam/museums/Seabee/UnitListPages/NCB/020%20NCB.pdf`.
- ***Building the Navy's Bases in World War II***, vol. 2 (Bureau of Yards and Docks, 1947;
  HyperWar, `bases-NN`): what the battalion built, and where, often to the month only.
- ***Marines in the Central Solomons*** (Rentz, 1952; HyperWar): the 30 June 1943 landings at
  Oloana Bay (Wickham Anchorage, Vangunu) and Viru Harbor.
- **War diaries** (NARA RG 38, `rg38-<file unit>/pNNNN`) of the ships and commands that moved the
  battalion: Commander Amphibious Force South Pacific (May 1943, the Forward Echelon's six LSTs to
  Townsville), Transport Division Two (May-June 1943, Nouméa to Guadalcanal), Commander Task Group
  32.3 (June-July 1943, the Russells and the landings), Commander Task Force 31's operation and
  loading orders for the New Georgia landings, Commander Task Group 31.3 (September and December
  1943), and LST-824 and LST-898 (April 1945, Saipan to Okinawa). Found with a catalog search for the
  battalion's name (`"20th Construction Battalion"`, `"20th USN Construction"`, `"20th NCB"` and so on)
  and read on the scans. The history sheets' chronology (`ncbhist-020/p10`-`p12`) gives the rest of the
  sailings, without ships.

## Files

Hand-edited:

- `units.csv`: `unit`, `name`, `note` (an outline of the battalion, with its sources)
- `parts.csv`: the battalion's parts and when each existed: `unit`, `part`, `parent` (the part it
  split from), `from`, `to`, `note`. A part's position is its own rows while it existed and its
  parent's otherwise; a parent's rows dated after a part split off are the rest of it
- `stations.csv`: each place the battalion, or one part of it, was recorded, with its source
- `places.csv`: coordinates (`python3 tools/geocode_places.py records/seabees/places.csv` fills
  rows that have a `query`; hand-placed rows say where and why)

- `voyages.csv`: the crossings between two stations, and what is known of the ships: `unit`, `part`,
  `from_date` and `to_date` (the dates of the stations it joins: the page draws the legs between them),
  `sailed`, `arrived`, `from_place`, `to_place`, `ships` (as the record names them), `status`
  (`confirmed`: the ship's or the command's diary has the battalion aboard; `partial`: the equipment's
  craft are named, not the men's; `planned`: from a loading order, before it sailed; `ordered`: a
  diary orders the move; `named`: the history sheet names the ship; `not recorded`), `carried` (what
  the record says was embarked), `ref`, `note`
- `voyage_positions.csv`: positions a ship logged on the way (`unit` and `from_date` pick the voyage),
  `seq`, `date`, `time` (local), `zone` (the zone letter: `L` = GMT+11, `K` = GMT+10, `I` = GMT+9),
  `lat`, `lon` exactly as typed, `lat_fix`/`lon_fix` and `fix_note` for a typing slip, `on_track`
  (`no` to leave a position off the drawn track), `ref`. Only the flagship's or the ship's own position:
  a convoy's ships sailed together, so it stands for them all

Generated, never edited: `seabees.json`, the stations, parts' lines, voyages and weather for the kit's
`site/seabees.html` (`uv run tools/build_seabees.py`, which checks every row first; it must report 0 problems).

Generated (`python3 tools/fetch_station_weather.py seabees`):

- `weather.csv`: the weather on each day a battalion (or a part) was at a place: `unit`, `place`,
  `date` (local), ERA5 reanalysis at the place (`era5_tmax_c`, `era5_tmin_c`, `era5_precip_mm`,
  `era5_wind_max_kn`), and, where a weather station within 150 km recorded that day in NOAA's
  Integrated Surface Database, the station (`isd_station`, `isd_name`, `isd_km` from the place),
  its number of observations, maximum and minimum temperature, mean and highest wind, and how
  many observations reported precipitation falling (`isd_precip_reports`). `source` cites both.
  Days in transit get no row. Many of the stations are the war's own airfields (Kobler Field,
  Saipan; Sopanitogha, Guadalcanal; Ie Shima); New Georgia, Woodlark and Kiriwina had none whose
  records survive in the database, so their 1943 rows are ERA5 alone

## stations.csv columns

| Column | Meaning |
|---|---|
| `unit` | Key into `units.csv` |
| `part` | Which part of the battalion the row is about: `battalion` (all of it), `first wave` and `second wave` (the two sailings of 1942), `Forward Echelon` and `Rear Echelon` (the halves of May 1943 – June 1944, later the 1st and 2nd Sections), and within the Rear Echelon `Oloana Bay group`, `Viru company` and `Bau unit`; `first echelon 1945` and `second echelon 1945` (Saipan to Okinawa, April-May 1945) |
| `date` | The date the source gives for the row, ISO. For a muster-roll entry, the date of the entry (a transfer, a forwarding sheet); it shows the battalion there that day, not when it arrived |
| `station` | The source's words, as typed or printed, abridged with `...` |
| `place` | Key into `places.csv`; empty when the row has no position |
| `source` | `muster` (the rolls), `wardiary` (a ship's or a command's war diary), `ncbhist` (the Historical Information sheet and the museum's chronology), `bases` (*Building the Navy's Bases*), `mcsol` (*Marines in the Central Solomons*) |
| `ref` | The citation: `rg24-<file unit>/pNNNN`, `ncbhist-NNN/pN`, `bases-NN`, or a URL; several separated by `;` |
| `last_day` | `yes` when the row's date is the last day at the place (the day it sailed, or a place seen in passing): the stay doesn't run on to the next row |
| `assumed` | What the row assumes, if anything: `date` (the source gives only the month; the row is put on the 15th) or `place` (the source names a mail address, an island or a group, or several places; the note says where the point is drawn and why) |
| `note` | Readings, numbers, and how the row was placed |

The two halves of 1943 have their own rows, and so do the Rear Echelon's two groups of 30 June
1943, which landed 25 miles apart: about 400 men with the Army at Oloana Bay, about 140 at Viru
Harbor. The rolls list the whole Rear Echelon together (headed "Detachment" and "Second Section")
and don't say who was in which group.

## Not here yet

- The ocean transports of October and November 1942 (San Francisco and San Pedro to Nouméa),
  September 1944 (Banika to San Francisco) and February 1945 (San Francisco to Saipan), and the
  second echelon's ship to Okinawa in May 1945: no record found online names them. The battalion's
  cruise book, *Log of the 20th U.S. Naval Construction Battalion, First Cruise, 1942-1944*
  (Baton Rouge: Army & Navy Publishing Co., [1945?]; Navy Department Library, New York Public
  Library), may.
- The other two of the four LSTs of April 1945.
- The 79th's 1943–44 in Alaska, and its camp on Okinawa.
