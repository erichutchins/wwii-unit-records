---
convoy: TAKA-909
name_ja: タカ九〇九
plain: "a convoy of ten ships from Keelung for Kagoshima, with a Naha section, under six escorts"   # what it was, in a line, ours
from: Keelung
to: Kagoshima
via: []
sailed: ""
arrived: ""
size: "10 ships, 34,049 tons"
cargo: ""
attacked_by: [ss-385-bang/3]
sources:
  - jacar:C08030144100 p05   # 4th Surface Escort Division / Okinawa Base Force, Sept 1944, table of convoys given air cover: 19th, タカ九〇九, 10 ships, 34,049 t, six escorts, 基隆─鹿児島 / 那覇─鹿児島
  - jacar:C08030144100 p12   # 4th Surface Escort Division / Okinawa Base Force, Sept 1944, column 19: escorts, attack at N24-54 E122-23, 第二東勢丸 sunk
  - rg367-74802831/p10       # BANG's contact at 0615 K on 19 Sept: 8 merchantmen incl. an AO, 5+ escorts
route: [keelung, w-etw, w-kbay, kagoshima]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
ships:
  - ship: CD-30
    role: escort
    source: jacar:C08030144100
    page: p12
    basis: reported
    note: >-
      Kaibokan. Written 海防三〇 among the escorts of タカ九〇九船団 in the 4th Surface Escort Division / Okinawa Base Force
      diary, September 1944, daily summary, column 19
    sil: kaibokan2
    sil_basis: class
  - ship: W-15
    role: escort
    source: jacar:C08030144100
    page: p12
    basis: reported
    note: >-
      Minesweeper. Written 掃一五 among the escorts of タカ九〇九船団 in the 4th Surface Escort Division / Okinawa Base
      Force diary, September 1944, daily summary, column 19
    sil: no13-minesweeper
    sil_basis: 'class, assumed: the plate (ONI 41-42, leaf 253) names the No. 13 class, six ships, and Nos. 17 and 18, not No. 15'
  - ship: No. 3 Takunan Maru
    role: escort
    source: jacar:C08030144100
    page: p12
    basis: reported
    note: >-
      Auxiliary. Written 三拓南丸 among the escorts of タカ九〇九船団 in the 4th Surface Escort Division / Okinawa Base Force
      diary, September 1944, daily summary, column 19
    sil: gunboat
  - ship: Shichiri Maru
    role: escort
    source: jacar:C08030144100
    page: p12
    basis: reported
    note: >-
      Auxiliary. Written 七利丸 among the escorts of タカ九〇九船団 in the 4th Surface Escort Division / Okinawa Base Force
      diary, September 1944, daily summary, column 19
    sil: gunboat
  - ship: Taian Maru
    role: escort
    source: jacar:C08030144100
    page: p12
    basis: reported
    note: >-
      Auxiliary. Written 太安丸 among the escorts of タカ九〇九船団 in the 4th Surface Escort Division / Okinawa Base Force
      diary, September 1944, daily summary, column 19
    sil: gunboat
  - ship: No. 3 Taihei Maru
    role: escort
    source: jacar:C08030144100
    page: p12
    basis: reported
    note: >-
      Auxiliary. Written 三号太平丸 among the escorts of タカ九〇九船団 in the 4th Surface Escort Division / Okinawa Base
      Force diary, September 1944, daily summary, column 19
    sil: gunboat
  - ship: No. 2 Tosei Maru
    role: merchant
    to: 1944-09-19
    fate: sunk 1944-09-19 (BANG patrol 3 J02)
    source: jacar:C08030144100
    page: p12
    basis: reported
    note: 第二東勢丸沈没 under 被害 (damage) for the attack on タカ九〇九船団, column 19. 507-ton tanker per DANFS (secondary)
    sil: tanker
---

Attacked by BANG on 19 September 1944 off the north-east coast of Formosa. The Okinawa diary names six escorts
and the one ship lost, No. 2 Tosei Maru, and says CD-30 and Taian Maru with army aircraft attacked the submarine
and claimed it sunk. BANG surfaced that night after about 80 depth charges.

**Route and size** from the 4th Surface Escort Division's table of convoys given air cover (jacar:C08030144100
p05, read on the image 5 Nov 2026): on the 19th, TAKA-909, ten ships of 34,049 tons, escorted by CD-30, W-15, No. 3
Takunan Maru, Shichiri Maru, Taian Maru and No. 3 Taihei Maru, routed Keelung to Kagoshima and Naha to Kagoshima.
So it sailed from Keelung, not Takao as the convoy code had suggested. Its sailing time and cargo are not recorded.
The waypoints off Formosa's east coast and Kagoshima Bay are assumed. BANG counted eight merchantmen, one an oiler.

No other US boat's attack on TAKA-909 has been found: the diary's columns for the 18th–21st have only this
attack and, on the 20th, an attack on the depot ship Jingei far to the east (N27-12.5 E127-10.0; not BANG's).

To find: TAKA-909's sailing time from Keelung and its ships' names (its escorts' own September diaries).
