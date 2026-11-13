---
convoy: NAKA-303
name_ja: ナカ三〇三
plain: "a three-ship Naha–Kagoshima convoy with five escorts, attacked by TILEFISH in the Tokara Islands"   # what it was, in a line, ours
from: Naha
to: Kagoshima
via: []
sailed: 1945-03-03
arrived: ""
size: 3
cargo: ""
attacked_by: [ss-307-tilefish/5]
sources:
  - jacar:C08030608100 p3   # W-15's Battle Report No. 7: task (Sasebo signal 031131, escort NAKA-303 from Naha on 3 March for Kagoshima); convoy and escorts
  - jacar:C08030608100 p9   # its narrative: the attack of 5 March 1945, at Akusekijima 000° 5 miles
  - jacar:C08030608100 p17  # Taian Maru's signal, 1353: the convoy sent on to Kagoshima with Chitose Maru and No. 3 Taihei Maru
  - jacar:C08030608100 p18  # the Western Sea Escort Force, 1652: CD-44 and No. 2 Shinto Maru to join it near Kuchinoshima
  - jacar:C08030608100 p30  # its sketch of W-15's position when torpedoed, by bearings on Tairajima, Suwanosejima, Akusekijima
route: [naha, w-tokara, w-kuchino, w-kbay, kagoshima]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1945-03-03, place: naha, event: sailed, words: "昭和二十年三月三日那覇発鹿児島ニ向フナカ三〇三船団ノ護衛ニ任ズ (to escort convoy NAKA-303, leaving Naha on 3 March 1945 for Kagoshima)", source: jacar:C08030608100 p3, basis: reported}
  - {at: 1945-03-05 1652 I, place: w-kuchino, event: passed, words: "船團ノ位置口之島附近 (the convoy's position, near Kuchinoshima): the Western Sea Escort Force's order to CD-44 and No. 2 Shinto Maru to join and escort NAKA-303, originated 1652, sent 1724", source: jacar:C08030608100 p18, basis: reported, approx: true}
ships:
  - ship: W-15
    role: escort
    number: '1'
    from: 1945-03-03
    to: 1945-03-05
    source: jacar:C08030608100
    page: p3
    basis: reported
    fate: torpedoed 5 March, towed and beached
    note: Escort No. 1, written 第十五號掃海艇, in her own Battle Report No. 7, 船団編成並ニ護衛艦艇 (the report's writer)
    sil: no13-minesweeper
    sil_basis: 'class, assumed: the plate (ONI 41-42, leaf 253) names the No. 13 class, six ships, and Nos. 17 and 18, not No. 15'
  - ship: Taian Maru
    role: escort
    number: '2'
    from: 1945-03-03
    to: 1945-03-05
    source: jacar:C08030608100
    page: p10
    basis: reported
    note: >-
      Escort No. 2, written 大安丸; the table's first character is faint (p3), the narrative writes it plainly (p10),
      when W-15 hands her the command of the convoy after she is hit. By her own signal of 1353 she stayed to guard W-15
      at Kiriishi anchorage and sent the convoy on to Kagoshima under Chitose Maru and No. 3 Taihei Maru (p17)
  - ship: Chitose Maru
    role: escort
    number: '3'
    from: 1945-03-03
    source: jacar:C08030608100
    page: p3
    basis: reported
    note: Escort No. 3, written in kana, ちとせ丸
  - ship: No. 51 Banshu Maru
    role: escort
    number: '4'
    from: 1945-03-03
    source: jacar:C08030608100
    page: p3
    basis: reported
    to: 1945-03-05
    note: >-
      Escort No. 4, written 第五十一播州丸. Left the convoy on 5 March to tow W-15 (Taian Maru's signal of 1353, p17)
  - ship: No. 3 Taihei Maru
    role: escort
    number: '5'
    from: 1945-03-03
    source: jacar:C08030608100
    page: p3
    basis: reported
    note: >-
      Escort No. 5, written 第二號大平丸 in the table (p3). Two signals write No. 3: Taian Maru's of 1353 on 5 March,
      sending the convoy on with her (第?大平丸, the figure faint, more like 三 than 二, p17), and No. 51 Banshu Maru's
      of the 6th, meeting 第三號太平丸 near Cape Sata (p19, plain); so do the escort force's order of the 7th (p20) and every
      line of the escorts' signal log of 5 March (pp22-23, 三號大平丸). Named No. 3 on their evidence; the table's 第二號
      stays as written here
  - ship: Hangchow Maru
    role: merchant
    number: '1'
    from: 1945-03-03
    source: jacar:C08030608100
    page: p3
    basis: reported
    note: >-
      Ship No. 1 by the table (type A, maximum speed 8.0 kt), written 杭州丸; the narrative (p9) calls her No. 2 ship
      (二番船杭州丸), the ship TILEFISH fired at. Her displacement on the table is not read
  - ship: Chokai Maru
    role: merchant
    number: '2'
    from: 1945-03-03
    source: jacar:C08030608100
    page: p3
    basis: reported
    note: Ship No. 2 by the table (type A, maximum speed 7.5 kt), written 鳥海丸
  - ship: Kashima Maru
    role: merchant
    number: '3'
    from: 1945-03-03
    source: jacar:C08030608100
    page: p3
    basis: reported
    note: Ship No. 3 by the table (type B, maximum speed 7.0 kt), written 鹿島丸
---

NAKA-303 (ナカ三〇三) left Naha on 3 March 1945 for Kagoshima: three ships, Hangchow, Chokai and Kashima Maru, with
five escorts led by Minesweeper No. 15 (W-15), whose Battle Report No. 7 is the convoy's record here
(jacar:C08030608100 p3). On 5 March, passing north through the Tokara Islands, it was attacked by TILEFISH, who fired
at Hangchow Maru and hit W-15 instead (p9; TILEFISH's Patrol 5, Attack 2).

The table numbers the ships 1 to 3 and the narrative calls Hangchow Maru "No. 2 ship"; the order of the column at sea
isn't settled by these pages. Its arrival at Kagoshima is not in the pages read.
