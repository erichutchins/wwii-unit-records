---
convoy: TAMA-17
name_ja: タマ一七
from: Takao
to: Manila
via: []
sailed: 1944-04-28
arrived: ""
size: ""
cargo: "coal (Nittatsu Maru, 250 t for Manila); the rest not recorded"
attacked_by: [ss-385-bang/1]
sources:
  - jacar:C08030140600 p15   # escort division table: Harukaze departs Takao 1300 with タマ一七; Asakaze joins from Manila
  - jacar:C08050103200 p23   # Nittatsu Maru's movement log: coal 250 t to be landed at Manila; Takegawa Maru sunk
route: [takao, w-bashi, w-luzw, w-zamb, w-bataan, w-corr, manila]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1944-04-28 1300 I, place: takao, event: sailed, source: jacar:C08030140600 p15, basis: reported}
  - {at: 1944-04-29, event: joined, words: Asakaze joins from Manila, source: jacar:C08030140600 p15, basis: reported}
ships:
  - ship: Nittatsu Maru
    role: merchant; designated rescue ship
    from: 1944-04-28
    to: 1944-04-30
    cargo: coal
    cargo_t: '250'
    cargo_for: Manila
    fate: sunk 1944-04-30 0419 I, 19-06N 119-10E (japanese.yml J08)
    source: jacar:C08050103200
    page: p23
    basis: reported
    note: >-
      Her master's movement log. 24 Apr: arrived Takao from Tsoying, 積荷石炭二五〇屯（マニラ揚） (loaded coal 250 t, to be
      landed at Manila); 28 Apr: departed Takao; 29 Apr: at sea. 2,859 GRT in the escort division's loss list
      (J10). The log names her and Taketoyo Maru the convoy's rescue ships (p23-24)
    sil: cargo
  - ship: Takegawa Maru
    role: merchant
    number: '10'
    to: 1944-04-29
    fate: sunk 1944-04-29 2240 I (japanese.yml J03, J04)
    source: jacar:C08050103200
    page: p23
    basis: reported
    note: >-
      第十番船 (No. 10 ship) in Nittatsu Maru's log. Cargo not recorded there. She presumably sailed with the convoy
      from Takao on the 28th (J01); not recorded for her, so left blank. 1,930 GRT (J10)
    sil: cargo
  - ship: Taketoyo Maru
    role: merchant; designated rescue ship
    source: jacar:C08050103200
    page: p23
    basis: reported
    note: >-
      救助擔任船トシテ武豊丸ト共ニ指定 (designated rescue ship together with Taketoyo Maru), Nittatsu Maru's log. Not in
      combinedfleet.com's list of the convoy (engagement luzon-strait-1944)
    sil: cargo
  - ship: Harukaze
    role: escort
    from: 1944-04-28
    source: jacar:C08030140600
    page: p15
    basis: reported
    note: >-
      Destroyer. Departed Takao 1300 escorting TAMA-17 (J01); depth-charged BANG after Attack 1 and escorted
      Nittatsu Maru after the rescue (J06)
    sil: kamikaze
    sil_basis: class
  - ship: Asakaze
    role: escort
    from: 1944-04-29
    source: jacar:C08030140600
    page: p15
    basis: reported
    note: Destroyer. Sailed from Manila alone and joined en route on the 29th (J02)
    sil: kamikaze
    sil_basis: 'class, assumed: the plate lists Kamikaze, Harukaze, Hatakaze'
  - ship: W-17
    role: escort
    from: 1944-04-28
    source: jacar:C08030140600
    page: p15
    basis: reported
    note: >-
      掃十七 (Minesweeper No. 17), 1st Surface Escort Division movements table: (圧制潜敵)(七一マタ) from 高雄 (Takao), the
      departure time read as 1300 on the 28th, like Harukaze's; the line runs on through the 30th. Row name on p13
      (the table's first half), the 20th of 22 rows
    sil: no13-minesweeper
    sil_basis: 'class, assumed: the plate (ONI 41-42, leaf 253) gives Nos. 17 and 18 as 218 ft overall; drawn at the class''s 236 ft 9 in'
  - ship: Chojusan Maru
    role: escort
    from: 1944-04-28
    source: jacar:C08030140600
    page: p15
    basis: reported
    note: >-
      長壽山丸 (Chōjusan Maru) as the row name is written on p13, the 19th of 22 rows; combinedfleet.com has
      Chohakusan Maru (長白山丸) as the convoy's auxiliary gunboat. Same table: (七一マタ) from a time read as 1300 on the
      28th, no place written that day (the row's last place, about the 20th, is 高, Takao); the line runs on
      through the 30th
    sil: gunboat
  - ship: Kennichi Maru
    role: merchant
    source: combinedfleet:Nittatsu_t
    basis: secondary
    note: In TAMA-17 from Takao on 28 April, per combinedfleet.com's record of Nittatsu Maru
  - ship: Kurogane Maru
    role: merchant
    source: combinedfleet:Nittatsu_t
    basis: secondary
    note: In TAMA-17 from Takao on 28 April, per combinedfleet.com's record of Nittatsu Maru
  - ship: Belgium Maru
    role: merchant
    source: combinedfleet:Nittatsu_t
    basis: secondary
    note: In TAMA-17 from Takao on 28 April, per combinedfleet.com's record of Nittatsu Maru
  - ship: Peking Maru
    role: merchant
    source: combinedfleet:Nittatsu_t
    basis: secondary
    note: In TAMA-17 from Takao on 28 April, per combinedfleet.com's record of Nittatsu Maru
  - ship: Shiroganesan Maru
    role: merchant
    source: combinedfleet:Nittatsu_t
    basis: secondary
    note: In TAMA-17 from Takao on 28 April, per combinedfleet.com's record of Nittatsu Maru
  - ship: Tsushima Maru
    role: merchant
    source: combinedfleet:Nittatsu_t
    basis: secondary
    note: In TAMA-17 from Takao on 28 April, per combinedfleet.com's record of Nittatsu Maru
  - ship: San Luis Maru
    role: merchant
    source: combinedfleet:Nittatsu_t
    basis: secondary
    note: In TAMA-17 from Takao on 28 April, per combinedfleet.com's record of Nittatsu Maru
  - ship: Wales Maru
    role: merchant
    source: combinedfleet:Nittatsu_t
    basis: secondary
    note: In TAMA-17 from Takao on 28 April, per combinedfleet.com's record of Nittatsu Maru
  - ship: Yamahagi Maru
    role: merchant
    source: combinedfleet:Nittatsu_t
    basis: secondary
    note: In TAMA-17 from Takao on 28 April, per combinedfleet.com's record of Nittatsu Maru
  - ship: Shirotae Maru
    role: merchant
    source: combinedfleet:Nittatsu_t
    basis: secondary
    note: In TAMA-17 from Takao on 28 April, per combinedfleet.com's record of Nittatsu Maru
---

Takao to Manila, sailed 1300 on 28 April 1944 (the escort division's table). Only one ship's cargo is
recorded: Nittatsu Maru loaded 250 t of coal at Takao to be landed at Manila (her master's log, p23). The
other ships' cargoes and the convoy's arrival are not in the records read.
BANG attacked it on 29–30 April; PARCHE and TINOSA were in the same fight against two convoys (engagement `luzon-strait-1944`, which says which boat attacked which).

The retired battle page listed thirteen merchant ships from combinedfleet.com. Ten are on combinedfleet's page for
Nittatsu Maru (28 April: Kennichi, Kurogane, Belgium, Peking, Shiroganesan, Takegawa, Tsushima, San Luis, Wales,
Yamahagi and Shirotae Maru, escorted by Harukaze, W-17 and the auxiliary gunboat Chohakusan Maru; Asakaze joined on
the 29th), and are in `ships:` as secondary. Its Nissan Maru, and the Yashima and Hakka Maru that "other lists add",
are on no page found, so they are left out. combinedfleet's Chohakusan Maru is the escort division table's Chojusan
Maru (as read).
