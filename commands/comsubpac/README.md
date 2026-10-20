# COMSUBPAC war diary: Task Force Seventeen, October 1944

The war diary of Commander Submarine Force, Pacific Fleet, for October 1944
([NARA catalog 139761402](https://catalog.archives.gov/id/139761402), "COMSUBFORPAC - War Diary,
10/1-31/44", record group 38, 18 pages). It is headed "Report for Commander Task Force Seventeen
(Commander Submarine Force, Pacific Fleet)", signed by Vice Admiral C. A. Lockwood, Jr. and his chief
of staff, and sent on 5 November 1944 (serial 00916).

The diary came to us by way of [SarpedonSociety/patrol-map](https://github.com/SarpedonSociety/patrol-map),
whose `sources/status/war-diary/` holds its transcriptions of the same diary's Disposition of Forces
listings, April 1943 to June 1944, and the way it reads them.

Page 3 is the task organization and the Report of Changes. Pages 4, 10 and 18 are the Disposition of
Forces on 1, 15 and 31 October. The other pages, 5 to 17, are the daily log. All four files are
transcribed from the scans and checked against them, line by line.

## Files

- `disposition.csv`: the three Disposition of Forces listings, submarines only (the tenders,
  LITCHFIELD, SEAGULL and the rescue vessels at the head of each listing are not transcribed).
  One row per boat per listing.
  - `section`: the heading the boat is listed under, as typed. On 1 October the refit headings are
    "Under refit Midway", "Under refit Majuro" and "Under refit Saipan"; on 15 and 31 October they read
    "Under refit at ...".
  - `boat`: as typed. `name`: the same, with the diary's two spellings of four boats made one
    (SEADEVIL, SEAFOX, SEACAT, SEADOG are written SEA DEVIL, SEA FOX, SEA CAT, SEA DOG, as the diary
    also types them), to follow a boat from one listing to the next.
  - `unit`: the task unit number, for boats "Enroute patrol stations, on patrol, or enroute from patrol
    stations". The 17.11 to 17.24 groups are the coordinated attack groups (wolf packs).
  - `note`: for "Miscellaneous operations", the words after the name; otherwise what the page shows.
- `task_organization.csv`: what each task group number meant (G 17.1 Empire Patrol Group, and so on).
- `changes.csv`: the Report of Changes: boats reporting for duty and passing between CTF 17 and CTF 71.
- `log.csv`: the daily log, one row per entry, in the order typed.
  - `date`: the day heading the entry is typed under. `lwt`, `gct`: the two time columns, as typed.
  - `gct_date`: worked out, not typed. The headings are L.W.T. dates: the entries run in L.W.T. order,
    and on all but three lines GCT is L.W.T. plus 9 hours 30 minutes (the zone the diary was kept in).
    So an entry whose GCT is earlier in the day than its L.W.T. (L.W.T. 1430 or later) is on the next
    GCT day. Blank for the one entry whose two times can't both be right (SKATE, 27 October).
  - `boats`: each boat named with a task unit number in the entry, and the number (`REDFISH 17.18.1;
    BANG 17.18.2`), taken from the text.
  - `note`: where the entry disagrees with itself or with the rest of the diary.

## Things to know

- **The departure from Midway on 25 October.** "0330 1800 REDFISH (17.18.1), BANG (17.18.2), and SHAD
  (17.18.3) departed Midway for patrol", under the 25 October heading: 1800 L.W.T. on 25 October, 0330
  GCT on 26 October. BANG's report has 25 October 1530 (Y), the same moment; SHAD's has 1550 and
  REDFISH's 1630.
- **Unit numbers typed for the wrong boat.** SARGO is typed 17.1.7 (BLACKFIN's number) three times,
  FLYING FISH 17.1.15 once, PIPEFISH 17.23.2 once, BARBEL 17.1.42 once, CABRILLA 17.3.22 once and
  SANDLANCE 17.3.7 once. All are kept as typed and noted. In the 1 October listing GABILAN and SEALION
  are both 17.17.2.
- **CAVALLA, 7 October.** The log has her passing to the operational control of CTF 17; the Report of
  Changes has CTF 71, and she is gone from the 15 October listing.
- **SNAPPER, 31 October,** is listed both under refit at Pearl Harbor and at patrol station 17.1.6.
- The log names a few people as the diary does: the aviators rescued by STERLET, SAWFISH, SAURY,
  TRIGGER and BONEFISH, and POMFRET's relief commanding officer.
- One reader. Not checked by a second.

## Cites

Each row cites its page, `rg38-139761402/pNN`: the catalog's object page, which is also the number
written in the corner of each sheet. The scans download to the kit's cache as `nara/rg367-139761402/`
(the kit's folder name for every National Archives item, whatever its record group).
