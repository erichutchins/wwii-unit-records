---
convoy: TAKA-206
name_ja: タカ二〇六
plain: "a six-ship Keelung–Naha convoy with four escorts, met by three boats of one pack"   # what it was, in a line, ours
from: Keelung
to: Naha
via: []
sailed: 1944-11-22
arrived: ""
size: 6
cargo: ""
attacked_by: [ss-385-bang/4, ss-395-redfish/2, ss-235-shad/8]
sources:
  - jacar:C08030607900 p32   # W-15's battle report: task, escort convoy タカ二〇六 from Keelung to Naha, sailing the 22nd; four escorts
  - jacar:C08030607900 p33   # convoy table: six ships, type letter, speed, displacement; sailing plan, Keelung 0800 on the 22nd
  - jacar:C08030607900 p47   # signal log: Taiken, Sannin and Eikai Maru sheltered at Funauki
route: [keelung, w-etw, naha]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1944-11-22 0800 I, place: keelung, event: sailed, words: "the sailing plan: Keelung 0800 on the 22nd", source: jacar:C08030607900 p33, basis: reported}
ships:
  - ship: Manazuru
    role: escort
    number: '1'
    from: 1944-11-22
    source: jacar:C08030607900
    page: p32
    basis: reported
    note: Escort No. 1, written 真鶴, in W-15's battle report, 一 計画 (ロ) 船団編成並ニ護衛艦艇
    sil: chidori
    sil_basis: 'class, assumed: the plate omits Manazuru'
  - ship: Seki Maru
    role: escort
    number: '2'
    from: 1944-11-22
    source: jacar:C08030607900
    page: p32
    basis: reported
    note: Escort No. 2, written 関丸, in W-15's battle report, 一 計画 (ロ) 船団編成並ニ護衛艦艇
    sil: gunboat
  - ship: No. 16 Shonan Maru
    role: escort
    number: '3'
    from: 1944-11-22
    source: jacar:C08030607900
    page: p32
    basis: reported
    note: Escort No. 3, written 第十六昭南丸, in W-15's battle report, 一 計画 (ロ) 船団編成並ニ護衛艦艇
    sil: gunboat
  - ship: W-15
    role: escort
    number: '4'
    from: 1944-11-22
    source: jacar:C08030607900
    page: p32
    basis: reported
    note: Escort No. 4, written 第十五號掃海艇, in W-15's battle report, 一 計画 (ロ) 船団編成並ニ護衛艦艇
    sil: no13-minesweeper
    sil_basis: 'class, assumed: the plate (ONI 41-42, leaf 253) names the No. 13 class, six ships, and Nos. 17 and 18, not No. 15'
  - ship: Taiken Maru
    role: merchant
    number: '1'
    from: 1944-11-22
    source: jacar:C08030607900
    page: p33
    basis: reported
    note: >-
      No. 1, written 大建丸; 船種 (type) C, top speed 8 kt, displacement blank (as written) in W-15's convoy table.
      Type letters A and C are not explained on the page; sheltered at Funauki on the 23rd (signal log p47, BANG
      patrol 4 J04)
    sil: cargo
  - ship: Hozan Maru
    role: merchant
    number: '2'
    from: 1944-11-22
    fate: torpedoed 1944-11-22 2339 I (BANG patrol 4 J02); sunk 2337 I, named by W-15's signal (J07) and the Imperial Navy's November summary (J09)
    source: jacar:C08030607900
    page: p33
    basis: reported
    note: >-
      No. 2, written 鳳山丸; 船種 (type) C, top speed 10 kt, displacement 二三四五 (as written) in W-15's convoy table.
      Type letters A and C are not explained on the page
    sil: cargo
  - ship: Sannin Maru
    role: merchant
    number: '3'
    from: 1944-11-22
    source: jacar:C08030607900
    page: p33
    basis: reported
    note: >-
      No. 3, written 三仁丸; 船種 (type) A, top speed 8.5 kt, displacement 二五〇〇 (as written) in W-15's convoy table.
      Type letters A and C are not explained on the page; sheltered at Funauki on the 23rd (signal log p47, BANG
      patrol 4 J04)
    sil: cargo
  - ship: Amakusa Maru
    role: merchant
    number: '4'
    from: 1944-11-22
    fate: torpedoed and sunk 1944-11-22 at 24-20N 122-40E, her own movement sheet (jacar:C08050106900 p17; BANG patrol 4 J10)
    source: jacar:C08030607900
    page: p33
    basis: reported
    note: >-
      No. 4, written 天草丸; 船種 (type) C, top speed 10 kt, displacement 二三四五 (as written) in W-15's convoy table.
      Type letters A and C are not explained on the page
    sil: cargo
  - ship: Eikai Maru
    role: merchant
    number: '5'
    from: 1944-11-22
    source: jacar:C08030607900
    page: p33
    basis: reported
    note: >-
      No. 5, written 映海丸; 船種 (type) A, top speed 10 kt, displacement 一〇〇〇 (as written) in W-15's convoy table.
      Type letters A and C are not explained on the page; sheltered at Funauki on the 23rd (signal log p47, BANG
      patrol 4 J04)
    sil: cargo
  - ship: Sakae Maru
    role: merchant
    number: '6'
    from: 1944-11-22
    fate: searched for on the 23rd (J04); torpedoed and sunk 1944-11-24 at 24-34N 122-3?E, her own movement sheet (jacar:C08050033500 p32; BANG patrol 4 J11)
    source: jacar:C08030607900
    page: p33
    basis: reported
    note: >-
      No. 6, written 栄丸; 船種 (type) A, top speed 9 kt, displacement 二八七八 (as written) in W-15's convoy table. Type
      letters A and C are not explained on the page. Her movement sheet (榮丸, 2,878 tons, ship number 28554) gives the
      24th in both its header and its remark; no attack in the kit falls that day
    sil: cargo
---

Keelung to Naha, sailing at 0800 on 22 November 1944 with six ships and four escorts (W-15's battle report,
p32–33). Three were sunk (Hozan and Amakusa Maru that night, Sakae Maru on the 24th by her own sheet); the other three sheltered at Funauki
(Iriomote) on the 23rd. BANG, REDFISH and SHAD all attacked it (engagement `bang-patrol-4`).

**Cargo: not recorded** in W-15's report. The table gives each ship a type letter (A or C, not explained on the
page), a top speed and a displacement.
