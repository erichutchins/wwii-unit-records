# Minesweeper No. 15 (W-15): war diaries, September and November 1944

`positions.csv` has the same columns as `patrol-N/positions.csv`, transcribed from her own war diaries on JACAR
(National Archives of Japan; the image is at `https://www.jacar.archives.go.jp/das/image/<code>`, cached by
`tools/jacar.py fetch`). Times are zone I (−9), as the diaries keep them. A position written for an event (a ship
torpedoed, a ship sunk) is the event's, not hers, and is `on_track=no`; a port's position is a standard one where the
diary names the port and gives none.

| Months | JACAR | Pages read |
|---|---|---|
| Sep 1944 (TAKA-909, Keelung to Naha) | C08030607800 | p49, p53 |
| Nov 1944 (TAKA-206, the night of 22-23 November) | C08030607900 | p40-42, p47 |

Between her fixes she logged each order of helm, course and speed by name and each depth-charge attack:
`log.yml`, the night of 22-23 November (pp40-42). The engagement build reckons her path from it (records/SCHEMA.md, "A
ship's log"). Her speeds by name have no figure in knots from a record: `speeds` in ship.yml takes the escorts'
doctrine's 12 and 16 knots (ntmj-s24:p11), assumed. Two readings are in doubt and carry `?` with a `time_fix`: the
rescue times (0?05, 0?15, 0?00) and which line 0452 stands over (the 0450 entry's note). Her class's silhouette is
`no13-minesweeper` (ONI 41-42).

## Her night against the escorts' doctrine

The Naval Technical Mission's report S-24 (February 1946) gives the Japanese escorts' anti-submarine doctrine as their
officers described it after the war. Her log follows it line by line (the matching is ours, inferred):

- **The contact report.** "Immediately upon picking up an echo, contact was reported; in daylight, by flag hoist; at
  night, by Very pistol" (ntmj-s24:p11). At 2240 she sighted No. 1 ship Manazuru's red signal-pistol flare, written
  浮上潜水艦, surfaced submarine (p40).
- **The run in.** "Head for contact and slow to twelve knots … At 800 meters increase speed to 16 knots", then drop
  (p11). After her first attack (2346, three charges at 30 m, course S 80° E) and the sonar contact at 40° to
  starboard, 600 m, she put the helm to starboard (0001, N 20° W), went to battle speed 1 (0003) and attacked again
  (0005, two charges).
- **Lost contact.** "Continue on the attack course for approximately 1000 meters, go to 12 knots and reverse course to
  the right, returning to the area of attack" (p13). At 0009 she went to standard speed on S 30° E, "assessing the
  result, then continuing to search and sweep" (p41). Her 0001 turn was to the right.
- **The search.** A single ship "steamed chords of an expanding spiral … predicated on a submarine target speed of
  3 knots", usually for no more than twenty-four hours; with several escorts "the probable submarine area was divided
  into sectors by the senior escort captain and each escort searched its own area" (pp13-15). From 0600 she altered
  course every 30 to 105 minutes (N 10° W, S 55° E, S 45° W, W, N 30° W, E, S 30° W), and at 1224 began the sweep and
  search ordered by Manazuru, the senior escort (p42).
- **The patterns.** Her two attacks of three and two charges are small beside the doctrine's: "Small patterns were
  used on doubtful contacts. Doctrine called for maximum patterns to be dropped on contacts classified definitely as
  submarines" (p11). Her log calls the contact after the first attack "something like a submarine" (潜水艦ラシキモノ).
