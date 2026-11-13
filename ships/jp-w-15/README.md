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

## 5 March 1945: without her echo ranging

Escorting NAKA-303 from Naha to Kagoshima, at 0833 she heard an explosion at 29-42N 129-30E and signalled that she
was "suppressing" (制圧中); at 1000 the escorts broke off their sweep, "having found nothing of the enemy" (p16). The escorts' signal log
(pp22-23) has the morning between: at 0800 she told the escorts her echo-ranging set's housing was leaking and needed
repair; Taian Maru (0837) and No. 3 Taihei Maru (0838) each signalled a deterrent drop (威嚇投射), charges thrown to keep
a submarine down rather than on a contact; Taihei Maru had swept with no contact (0841), and Taian Maru had seen a torpedo
track near No. 3 ship but judged it to have exploded of itself (0844). At
1044 TILEFISH's torpedo broke her stern. Battle Report No. 7's lessons give the reason the attack came in so close:
"Because both our ship and Taian Maru had their echo-ranging sets out of order and could not use them, the enemy
attacked extremely boldly" (本艇及太安丸ノ二隻ガ探信儀故障ニツキ使用セザルタメ極メテ大膽ニ敵ハ攻擊シ來リシ事,
jacar:C08030608100 pp13-14). The morning's sweep was made by hydrophone and lookouts, or by the three other escorts'
sets, if they had them (inferred; the report doesn't say).

After the beaching, the Western Sea Escort Force (西海護) ordered CD-44 and No. 2 Shinto Maru out at once to her
rescue (1203, p16), and CD-68 arrived off Kiriishi anchorage at 1330 on the 8th (p12). She was stripped of her weapons
and gear from the 6th to the 9th, the crew watching from ashore by night (p12).

Ten days later the report's summary (p25) gives no results against the enemy (戰果ナシ) and her damage as 中破,
moderate, with four petty officers and men killed and four wounded; JANAC lists her as sunk (janac:3/p23). Its lessons
(pp26-27) take the attack apart:

- With echo ranging out, the escorts should not make a long sweep: attack at once on a torpedo track, end the sweep
  quickly and close up on the convoy, and keep to false routes (p26, lesson 2).
- "The enemy submarine is very likely to come inside the convoy after firing; in this attack too it is judged to have
  attacked this ship while coming into the convoy" (p27, lesson 5).
- On the day before the attack, entering Ōshima, the convoy met an enemy B-24, and "we think the submarine may have
  been told of us"; she should have made large alterations and taken a false route without waiting for the slow Kashima
  Maru to join (p27, lesson 7).
- "That we were attacked while signalling the intention to take a false route, before carrying it out, is truly to be
  regretted, and came from the commander's want of decision" (p27, lesson 8): her signal of 0?17 (p22).
