# USS BANG (SS-385): six war patrols

Every position BANG reported in her six WWII war patrol reports, transcribed
from the National Archives scans (cited by page; titles in `../../citations.json`).

| Patrol | Dates | Area | Source folder (catalog ID) | Fixes |
|---|---|---|---|---|
| 1 | 29 Mar – 14 May 1944 | Luzon Strait | [74802746](https://catalog.archives.gov/id/74802746) | 56 |
| 2 | 6 Jun – 2 Aug 1944 | Marianas lifeguard, Luzon Strait | [74802784](https://catalog.archives.gov/id/74802784) | 88 |
| 3 | 27 Aug – 29 Sep 1944 | Bonins, east of Formosa | [74802831](https://catalog.archives.gov/id/74802831) | 32 |
| 4 | 25 Oct – 5 Dec 1944 | East of Formosa (via Saipan) | [74802868](https://catalog.archives.gov/id/74802868) pp. 2–37 | 46 |
| 5 | 2 Jan – 24 Feb 1945 | East China & Yellow Seas | [74802868](https://catalog.archives.gov/id/74802868) pp. 38–65 | 38 |
| 6 | 25 Mar – 18 May 1945 | Luzon Strait, Formosa lifeguard | [74802934](https://catalog.archives.gov/id/74802934) | 55 |

Columns are defined in [the records README](../../README.md).

## Corrections to the originals

`tools/check_track.py` flags any leg BANG couldn't have sailed (over 20.5 kt
plus 30 nm of navigational slack). Every flagged leg has been resolved, either
by a correction with a stated reason or by taking that one fix off the track:

- **P1** 24 Apr BT latitude 28-56N → 20-56N; a "3 May" BT reading → 2 May
- **P2** 10 Jun BT time 2317 → 0317; 25 Jun BT longitude 141-40E → 121-40E; six fixes off-track
- **P3** 24 Sep BT date → 23 Sep (typed with the local date)
- **P5** 15 Feb radar fix off-track (70 nm from three agreeing aircraft fixes)

## Weather, moon and the earthquake

- **Weather** is ERA5, a modern reconstruction of past weather. It has hourly
  values back to 1940 but rests on few 1940s observations in the western
  Pacific, so trust its broad patterns (monsoon, fronts, typhoons) more than
  exact winds. The captains' own weather notes are marked separately on the
  dive profile.
- **Sun and moon** are computed in the page from the boat's position. Checked
  against the reports: moonset 0222 on 30 Apr 1944 (report: 0222), 0443 on
  4 Jul 1944 (report: 0445), and moon down on the "moonless" night of 18 Apr 1944.
- **The 2 May 1945 earthquake** (Patrol 6, 0800 zone I = 2300 GCT 1 May): no
  event in the USGS/ISC-GEM or ISC bulletins within 1,500 km of the boat from
  28 Apr to 5 May 1945. Those catalogues are only complete for about M6+ in
  that era, and Taiwan's seismograph network nearly stopped recording from
  March 1945 to January 1946, so a moderate offshore quake could go unrecorded.
  The nearest catalogued events are M6.1 west of Yonaguni (10 Apr 1945) and
  M6.5 off Hualien (1 Aug 1945).

## The Japanese side

The other side of BANG's attacks, from Japanese wartime records (JACAR,
`tools/jacar.py`) and, where no primary record has been found yet, from
combinedfleet.com. Transcribed the same way as the patrol reports: as
written, with the page, and with an English translation beside the original.

## What it shows for Patrol 1

| Attack (BANG, GMT) | Japanese record (GMT) | Apart | Source |
|---|---|---|---|
| 1: 29 Apr 1256 | Takegawa Maru torpedoed 1301, sank 1340 | +5 min, 7.6 nm | Nittatsu Maru's own log |
| 2, 3: 29 Apr 1753, 1756 (10 torpedoes, all "Miss") | Nittatsu Maru: "five torpedoes, three exploded near the ship's bottom, no damage", 1800 | +4 to +7 min | same |
| 4: 29 Apr 1918 | Nittatsu Maru hit 1919, sank about 5 min later | +1 min, 5.0 nm | same |
| 5: 3 May 1732 | Kinrei Maru sunk 1606 | −86 min, 8.8 nm | combinedfleet.com (secondary) |

- The four primary matches agree to within minutes once both clocks are
  converted to GMT. That supports the zone assumptions on both sides.
- Attack 5: see "The wolfpack" below. The three boats' reports settle the
  order of the 3–4 May attacks; who sank which ship still needs a Japanese
  primary record.
- Claims vs. losses: BANG judged Nittatsu Maru a 10,400-ton transport; the
  Japanese tables give 2,859 GRT. BANG's Attack 5 claim of a destroyer is
  not in the Japanese loss list for May (J11).
- Nittatsu Maru turned back alone to rescue Takegawa Maru's survivors
  (56 by 2350, the last by 0050) "as moonset was near". BANG's report gives moonset at 0222 K (0122 I).

## What it shows for Patrols 2–4

| Attack (BANG) | Japanese record | Apart | Source |
|---|---|---|---|
| P2 Attack 2, 29 Jun 1508 I (three salvos, two ships claimed sunk, one probably) | HI-67: oilers Miri Maru and Sarawak Maru torpedoed, minor damage, 1515 at 17-13N 118-22E | +7 min, 2.4 nm | 1st Surface Escort Division war diary, June chart |
| P3 Attacks 1–2, 9 Sep 1616–32 K | Convoy No. 3905: Tokiwasan Maru and Shoryu Maru sunk, 28-58N 137-45E | 5.6 nm | combinedfleet.com (secondary) |
| P3 Attack 3, 19 Sep 0915 K | TAKA-909: No. 2 Tosei Maru sunk at 24-54N 122-23E; escorts claim the submarine | 8.0 nm (no time) | 4th Surface Escort Division war diary, daily summary |
| P4 Attack 1, 23 Nov 0032 K | TAKA-206: a ship sunk 2337 I at 24-21N 122-38E; Hozan Maru seen torpedoed 2339 I | +5 min, 3.7 nm | W-15's battle report |

- Patrol 2: neither oiler sank. Both reached Manila (combinedfleet.com), so
  BANG's two "sunk" and FRUPAC's "2 AK sunk, 1 AK prob. sunk" were claims.
  Sheet 2(b)'s "large hole under bridge" matches Miri Maru, "hit under the
  bridge". The seaplane tender Notoro on the same day's FRUPAC map was
  FLASHER's target off Borneo, not in HI-67.
- Patrol 3: the escorts of TAKA-909 recorded "one enemy submarine sunk".
  Nothing in the 4th Escort diary for BANG's Attacks 5–6 (2315 I, 20 Sep).
- Patrol 4: the US Navy chronology credits Hozan Maru to REDFISH, but she was
  hit 5–7 minutes after BANG fired at "one medium AK" and saw it disappear.
  REDFISH's report would settle it. Of the six ships, three were sunk and
  three sheltered at Funauki.

## BANG's other pack-mates

Transcribed from their own reports in the same layout, each passing
`check_track.py` with 0 too-fast legs. Corrections and doubtful readings are
in each file's `fix_note` and `note` columns.

| Boat | Folder | Report | Positions | With BANG |
|---|---|---|---|---|
| SEAHORSE (SS-304), Patrol 5 | `boats/ss-304-seahorse/patrol-5/` | [74845019](https://catalog.archives.gov/id/74845019) | 49 | BANG Patrol 2 (S. D. Cutter); zone H on station; attacked the 4 July convoy first (2354–2355 H, 3 Jul) |
| GROWLER (SS-215), Patrol 9 | `boats/ss-215-growler/patrol-9/` | [74818866](https://catalog.archives.gov/id/74818866) | 65 | BANG Patrol 2 until 30 Jun; uses half-hour zones KL (−10½) and IK (−9½), added to `check_track.py`; one attack, 29 Jun 0228 I |
| REDFISH (SS-395), Patrol 2 | `boats/ss-395-redfish/patrol-2/` | [74837267](https://catalog.archives.gov/id/74837267), [74837338](https://catalog.archives.gov/id/74837338) | 96 | Pack commander (Cdr L. D. McGregor), BANG Patrol 4. Zone K on station, I from 1 Dec |
| SHAD (SS-235), Patrol 8 | `boats/ss-235-shad/patrol-8/` | [74848165](https://catalog.archives.gov/id/74848165) | 29 | BANG Patrol 4; zone K throughout; one salvo, fired by mistake, 22 Nov 2338 K |
| SPADEFISH (SS-411), Patrol 3 | `boats/ss-411-spadefish/patrol-3/` | [74850282](https://catalog.archives.gov/id/74850282) | 31 | BANG Patrol 5 (Wolfpack 23); six attacks 28 Jan – 6 Feb 1945 |
| ATULE (SS-403), Patrol 2 | `boats/ss-403-atule/patrol-2/` | [74802211](https://catalog.archives.gov/id/74802211) | 88 | BANG Patrol 5; covered BANG's area from 8 Feb |
| POMPON (SS-267), Patrol 7 | `boats/ss-267-pompon/patrol-7/` | [74834293](https://catalog.archives.gov/id/74834293) pp. 35–61 | 43 | BANG Patrol 5 on paper; sailed a day later, left the area 31 Jan, never mentions BANG |
| BURRFISH (SS-312), Patrol 6 | `boats/ss-312-burrfish/patrol-6/` | [74809762](https://catalog.archives.gov/id/74809762) | 66 | BANG Patrol 6, until BANG left formation on 29 Mar; no torpedo attacks, no rescues |

SNOOK (SS-279), the third boat of BANG's Patrol 6 group, has no report for
that patrol: she left formation the first night "to return to port"
(BURRFISH p03). Her last report in the series is Patrol 8 (74850126).

`patrol-6/positions.csv` now includes BANG's Section U radar-intercept
positions for 18–25 April 1945 (p35–36); the 21 April 2200 entry (typed
125-14E) contradicts the narrative and is off the track, and the 24 April
0545 latitude typed with "E" is fixed to N.

## The wolfpack: PARCHE and TINOSA

BANG's partners on this patrol are transcribed from their own reports, in the
multi-boat layout planned in `guides/FLEET.md`:

| Boat | Folder | Report | Positions | Notes |
|---|---|---|---|---|
| PARCHE (SS-384), Patrol 1 | `boats/ss-384-parche/patrol-1/` | [74828582](https://catalog.archives.gov/id/74828582) | 64 | Pack commander Capt. G. E. Peterson aboard. Zone I on station. The density-layer table gives dates but no times, so `check_track.py` skips its 10 positions (kept in the CSV) |
| TINOSA (SS-283), Patrol 6 | `boats/ss-283-tinosa/patrol-6/` | [74856363](https://catalog.archives.gov/id/74856363) | 44 | Zone **H** (−8) on station, not I. No density-layer positions, so the track rests on narrative fixes and the contact tables |

Only `positions.csv` so far (no depths or layers). Both pass `check_track.py`
with 0 too-fast legs. Fixes taken off the track: PARCHE's aircraft contacts
1–2 (13 Apr) and 14–17 (30 Apr), and two rows of TINOSA's attack summary
table that contradict her own narrative (Attack 1 longitude, Attack 2 time
and position). `tools/pack_timeline.py` merges the three boats and the
Japanese records on one GMT clock (`pack_timeline.csv`), and `battle.html`
draws them (`guides/BATTLES.md`).

**29–30 April, TAMA-17.** BANG attacked alone at night (Attacks 1–4). Next
morning PARCHE (1010 I, 0110 GCT; 4 fired, no hits seen) and TINOSA (0919 H,
0119 GCT; 6 fired at five overlapping ships, claimed one AK sunk and two
damaged) attacked nine minutes apart; TINOSA watched escorts depth-charge
PARCHE. The Japanese April loss list has no TAMA-17 loss after Nittatsu
Maru, and the convoy's other ships reached Manila on 2 May, so TINOSA's
claimed sinking is not supported.

**3–4 May, TE-04.** TINOSA found the convoy at 0552 H on 3 May and trailed it,
reporting hourly. The order of attacks, all in GCT on 3 May:

| GCT | Boat | Attack | Claimed | Japanese side (combinedfleet.com, secondary) |
|---|---|---|---|---|
| 1509 | TINOSA | 2: 6 fired at a tanker and an AK | AO sunk, AK probably sunk | Toyohi Maru sunk 1508, "by TINOSA" |
| 1606 | PARCHE | 2: 4 + 2 fired | two AKs sunk | Kinrei Maru sunk 1606 "by BANG"; Daibu Maru 1613 "by TINOSA" |
| 1627 | PARCHE | 3: 4 fired | one AK or AP sunk | |
| 1732 | BANG | 5 | AK and DD | Shoryu and Daiyoku Marus "about" 1800, "by PARCHE" |
| 1849 | TINOSA | 3: 4 stern tubes | AK sunk ("merely disintegrated") | |
| 2009 | TINOSA | 4 | unknown, 2 explosions | |
| 0050 (4 May) | TINOSA | 5 | unknown, 2 explosions | |

PARCHE heard TINOSA's opening attack ("distant explosions; one of the other
boats evidently attacking", 0016 I), and BANG's sheet says the convoy had
already been scattered by PARCHE and TINOSA. So the boats' own reports put
the order as TINOSA, PARCHE, BANG, then TINOSA again. The secondary source's
sinking times fit that order, but its attributions don't: no boat attacked at
0113 I (TINOSA was deep under depth charges from 2320 to 0134 H), and its
0106 I for Kinrei Maru, which JANAC credits to BANG, is the minute PARCHE
fired. Which boat sank Kinrei Maru needs a Japanese primary record (her own
movement log, or TE-04's escort reports), not yet found.

## Records used

| Reference | Record | Pages used |
|---|---|---|
| [C08050103200](https://www.jacar.archives.go.jp/das/image/C08050103200) | Designated-ship movement tables, vol. 4 (タ–ワ), part 5: **Nittatsu Maru's movement log**, 1 Nov 1943 – 30 Apr 1944, by her master | p19 (header), p23–25 |
| [C08030140600](https://www.jacar.archives.go.jp/das/image/C08030140600) | 1st Surface Escort Division war diary (extract), April 1944 | p4 (narrative), p15 (escort movements), p30 (losses table) |
| [C08030140700](https://www.jacar.archives.go.jp/das/image/C08030140700) | Same, May 1944 | p26 (losses table) |
| [C08030512800](https://www.jacar.archives.go.jp/das/image/C08030512800) | Takao Guard District war diary, part 3 (radio log, 23–30 Apr 1944) | p24–27 |
| [C08030141000](https://www.jacar.archives.go.jp/das/image/C08030141000) | 1st Surface Escort Division war diary (extract), June–July 1944 | p33 (June losses), p34 (HI-67 chart) |
| [C08030141500](https://www.jacar.archives.go.jp/das/image/C08030141500) | Same, September 1944 | p43 (losses; none of BANG's) |
| [C08030144100](https://www.jacar.archives.go.jp/das/image/C08030144100) | 4th Surface Escort Division / Okinawa Base Force war diary, September 1944 | p12 (daily summary, 19 Sep) |
| [C08030607900](https://www.jacar.archives.go.jp/das/image/C08030607900) | Minesweeper W-15 war diary and battle reports, part 2 | p32–35 (TAKA-206 plan, ships, formation), p40–41 (log), p47 (signals) |

Not found yet: a log for Takegawa Maru (not in the タ–ワ volume) or Kinrei
Maru (キ, another volume); TE-04's escort records; convoy No. 3905's records
(Yokosuka, 9 Sep); anything for BANG's 20 Sep attacks; and a primary record
of Amakusa and Sakae Maru's sinking.

## US radio intelligence

Six maps name BANG in the catalog (29 Jun, 9, 19 and 20 Sep, 23 Nov 1944;
19 Jan 1945); the patrol 1 maps and 14 Jun and 4 Jul 1944 were read by date.
Nothing was found for patrol 5's attack (10 Feb 1945) or on the 29 Jan 1945
map.

### What the FRUPAC maps show

| Attack (BANG) | FRUPAC note (time read as zone I) | Apart |
|---|---|---|
| P1 Attack 1, 29 Apr 2256 K | "Yashima Maru att. by torp 2215/29", 19.4N 118.7E | +19 min, ~3 nm |
| P2 Attack 2, 29 Jun 1508 I | "TO RP ATT 29/1500"; "Sarawak Maru TO'd 1515/29" | −8, +7 min |
| P3 Attacks 1–2, 9 Sep 1616–32 K | "Tokinasan Maru & Shooryuu Maru torp & sunk 1520/09" | +4 min |
| P3 Attack 3, 19 Sep 0915 K | "BANG (191240) sank 1 AK & prob sank another 0815/19" | 0 min |
| P3 Attack 5, 21 Sep 0015 K | "BANG (201730) sank 1 AO & 1 AK & dam. 1. 2315/20" | 0 min |
| P4 Attack 7, 23 Nov 0314 K | "TORP. TRACK (BLANK) 0210/23", 24.2N 122.9E | −4 min, ~1 nm |

- Patrol 1: the time and place of Takegawa Maru's sinking, but the name
  Yashima Maru. On 30 April, Wales Maru (6,586 tons) reported a submarine
  at 1026 and 1730 I where BANG was trailing the TAMA-17 survivors; BANG
  dived for a plane at 1830 K (1730 I).
- Patrol 1, Attack 5 (TE-04): the 4 May map has torpedo attacks at 0019–0130 I
  about 12–23 nm away and nothing at BANG's 0232 I, consistent with TINOSA and
  PARCHE attacking first.
- Patrol 2: the 29 June convoy is "1 CVS, 5 Esc., 10 AK/AP" (the catalog names
  the seaplane tender Notoro), and the 4 July "SURFACED 1236/04" falls
  7 minutes after BANG dived for a plane at that longitude.
- Patrol 5: "USS BANG (190455) TRAWLER 1035/19" at BANG's Ship 1 position.
