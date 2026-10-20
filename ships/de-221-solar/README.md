# USS Solar (DE-221): war diaries, September 1944 – October 1945

`positions.csv` has the same columns as `patrol-N/positions.csv`, transcribed from the ship's monthly war
diaries (NARA RG 38, "World War II War Diaries, Other Operational Records and Histories"; scans download to the
kit's cache as `nara/rg367-<id>/`):

| Months | Catalog item | Pages |
|---|---|---|
| Sep – Oct 1944 | [78684020](https://catalog.archives.gov/id/78684020) | 8 |
| Nov 1944 | [78709413](https://catalog.archives.gov/id/78709413) | 5 |
| Dec 1944 – Jan 1945 | [139825595](https://catalog.archives.gov/id/139825595) | 3 |
| Feb 1945 | [139905513](https://catalog.archives.gov/id/139905513) | 4 |
| Mar 1945 | [633401458](https://catalog.archives.gov/id/633401458) | 3 |
| Apr 1945 | [139992648](https://catalog.archives.gov/id/139992648) | 4 |
| May 1945 | [633449597](https://catalog.archives.gov/id/633449597) | 4 |
| Jun 1945 | [77464063](https://catalog.archives.gov/id/77464063) | 2 |
| Jul 1945 | [77498013](https://catalog.archives.gov/id/77498013) | 1 |
| Aug 1945 | [77513304](https://catalog.archives.gov/id/77513304) | 1 |
| Sep 1945 | [77526853](https://catalog.archives.gov/id/77526853) | 3 |
| Oct 1945 | [77595243](https://catalog.archives.gov/id/77595243) | 4 |

Her earlier diaries (15 Feb 1944 – Aug 1944: 633401453, 78423064, 78471665, 78503825, 78594588, 134359696) and a
one-page war history (77691503) are in the same series and not transcribed yet. No diary after October 1945 is in
the catalog.

What the diaries show: the end of convoy GUS-50 (Mers-el-Kebir to Hampton Roads, then Boston, 1-19 Sep 1944);
UGS-57 out and GUS-57 home (11 Oct - 30 Nov 1944; COMTASKFOR 64's flagship from Palermo to the Atlantic, 3-12 Nov);
training ships out of Norfolk (Dec 1944 - Jan 1945); UGS-72 out (two ships of the convoy, *Regent Lion* and
*Michael J. Stone*, "struck by torpedo or mine" entering the Strait of Gibraltar on 17 Feb 1945; SOLAR escorted
*Michael J. Stone* into Gibraltar Bay) and GUS-74 home; UGS-84 out and GUS-86 home (2 Apr - 14 May 1945, at sea on
8 May); then submarine-school and training duty at New London, Portsmouth and Casco Bay, a Boston availability,
refresher training at Guantanamo (Sep 1945), schoolship at NTC Miami and Navy Day at Baltimore (Oct 1945).

- `source` is `diary` (the 0800 / 1200 / 2000 positions of each day's paragraph 3), `narrative` (ports, berths
  and anchorages, at the diary's times), `event` (a logged event with a time and no position: placed by
  `check_track.py` between the fixes either side, `assumed`) or `ship` (the diary's own position for something
  that was not SOLAR: the two ships hit on 17 Feb 1945 and the floating mine she sank on 15 Feb 1945; off the track).
- **Ports are not positioned in the diaries.** Each `narrative` row carries a standard harbour position, and its
  `fix_note` says so. The diary's own positions for its berths are used where it gives them (South Boston, Casco
  Bay, New York Navy Yard).
- **Zones are assumed.** The diaries type no zone letter. Each row is given the nautical zone of its own longitude
  (A, Z, N to R); rows without a position take the zone of the row before them. A ship in port may in fact have kept
  local war time, which can shift a port row by an hour.
- Corrections: 19 Sep 1944 0800 is typed in degrees-minutes-seconds (converted); the 26 Oct 1944 positions repeat
  the 24 Oct rows word for word (off the track); 11 Sep 1945 0800 has the latitude typed again for the longitude
  (off the track); 20 Oct 1945 0800 latitude 23-37N read as 25-37N (the typed value is 135 nm from the Miami pier she
  reached at 1200); the Fort Pond Bay anchorage typed "2351 28 March" overlaps the diary's own New London mooring
  and is read as 29 March.
- A few 0800–1200 legs at sea run 18–21 kn, faster than the convoy (7 May and 10 Apr 1945; 18 Oct 1945 into
  Havana). They are kept as typed: inside the speed screen, and nothing on the page says which row is wrong.
- The speed screen is 23 kn (her war history's top speed) plus 30 nm (`max_kts` in `ship.yml`). No silhouette yet:
  the Buckley-class plate (ONI 222-US) has not been traced.

View it at `site/patrols.html?ship=solar`. Regenerate with `uv run tools/check_track.py solar --geojson`.
