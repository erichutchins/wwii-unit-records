---
convoy: MI-11
name_ja: ミ一一
plain: "a sixteen-ship convoy carrying Army units and other transport, Takao to Manila, attacked off north-west Luzon on 31 July 1944"   # what it was, in a line, ours
from: Takao
to: Manila
via: []
sailed: 1944-07-29
arrived: ""
size: 16
cargo: "Army units and other transport (陸軍部隊其ノ他輸送), as the Navy's monthly summary puts it"
attacked_by: [ss-384-parche/2, ss-280-steelhead/6]
sources:
  - jacar:C16120659800 p9      # the Navy's July 1944 summary, 31st: the 16-ship convoy (6 escorts) from Takao on the 29th, attacked from about 0330; ships sunk and damaged
  - jacar:C08030141100 p15     # 1st Surface Escort war diary, July 1944, chart 麾下艦船部隊ノ行動 (其ノ一): the escorts' row names
  - jacar:C08030141100 p16     # the same chart, days 10-22: (ミ一一) with Shiokaze and Shimushu from the 13th, to Takao on the 21st
  - jacar:C08030141100 p17     # the same chart, days 20-31: Shimushu and Kazan Maru sail from Takao with (ミ一一) at 0500 on the 29th
  - jacar:C16120644000 p33     # the 2nd Demobilization Bureau's copy of the same summary, the 31st: the same entry, the fourth sunk ship written 光栄丸, and a submarine-hunting group formed
  - jacar:C08030141100 p6      # the same diary's narrative: a convoy ミ一? attacked off Cape Bolinao; Harukaze and Kai-26 sent to hunt and rescue (which convoy, and when, uncertain)
route: [takao, w-bashi, w-luzw, w-bataan, w-corr, manila]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1944-07-13 0600 I, place: "", event: sailed, words: "the chart: Shiokaze and Shimushu (Shimushu from Sasebo) take up (ミ一一) at 0600 on the 13th; the first leg's port of departure is not written for the convoy", source: jacar:C08030141100 p16, basis: reported}
  - {at: 1944-07-21, place: takao, event: arrived, words: "the chart: both escorts reach Takao on the 21st (the times, about 1245 and 1800, are small and not yet re-read)", source: jacar:C08030141100 p16, basis: reported}
  - {at: 1944-07-29 0500 I, place: takao, event: sailed, words: "the chart: 高雄 〇五〇〇 ＝（ミ一一）＝ for Shimushu and Kazan Maru; the summary: 29日高雄ヲ出港シマニラニ向ケ航行中", source: jacar:C08030141100 p17, basis: reported}
  - {at: 1944-07-31 0330 I, place: "", event: attacked, words: "0330頃連続敵潜ノ襲撃ヲ受ク (attacked by submarines one after another from about 0330); no position given. The 1st Surface Escort's narrative has a convoy attacked off Cape Bolinao (「ボリナオ」岬沖), but the convoy's number written ミ一? (the second figure not seen), and Cape Bolinao (about 16-20N) is some 150 nm south of the boats' attack positions (about 19N), so this may be another convoy, or a later attack on MI-11 on its way south from Pangui Bay", source: jacar:C16120659800 p9, basis: reported}
  - {at: 1944-07-31, place: "", event: sheltered, words: "船団ハ一時パングイ湾（ルソン島北西端）ニ避退 (the convoy withdrew for a time to Pangui Bay, the north-west tip of Luzon)", source: jacar:C16120659800 p9, basis: reported}
ships:
  - ship: Shimushu
    role: escort
    from: 1944-07-13
    source: jacar:C08030141100
    page: p16
    basis: reported
    note: >-
      Written 占守 (row 13 of the chart; the row names are on p15). Sasebo to Takao with (ミ一一) from 0600 on the 13th
      (p16); single to San Fernando and back to Takao with タマ二五/タエ九〇 on the 28th; sails again with (ミ一一) at
      0500 on the 29th (p17). The day columns are read from the column rules
    sil: shimushu
    sil_basis: 'class, assumed'
  - ship: Shiokaze
    role: escort
    from: 1944-07-13
    to: 1944-07-21
    source: jacar:C08030141100
    page: p16
    basis: reported
    note: >-
      Written 汐風 (row 4 of the chart). With (ミ一一) from 0600 on the 13th to Takao on the 21st (p16); not shown with
      the convoy after Takao (p17)
  - ship: Kazan Maru
    role: escort
    from: 1944-07-29
    source: jacar:C08030141100
    page: p17
    basis: reported
    note: >-
      Written 華山丸 (row 19 of the chart). Reaches Takao marked （ミ一一）單 and sails with (ミ一一) at 0500 on the 29th.
      Only two of the six escorts the summary counts are in the 1st Surface Escort's chart; the other four are not yet
      found
    sil: gunboat
  - ship: Harukaze
    role: escort
    from: 1944-07-31
    source: jacar:C08030141100
    page: p6
    basis: reported
    note: >-
      Written 春風. Sent with 海二六 (Kaibokan No. 26) to hunt the submarines and rescue, after a convoy was attacked off
      Cape Bolinao (the diary's narrative). Whether that was this attack is uncertain: the convoy's number written ミ一? (the second figure not seen), and Cape Bolinao (about 16-20N) is some 150 nm south of the boats' attack positions (about 19N), so this may be another convoy, or a later attack on MI-11 on its way south from Pangui Bay; not part of the
      convoy's escort
  - ship: Yoshino Maru
    role: merchant
    fate: sunk 1944-07-31 (the summary)
    source: jacar:C16120659800
    page: p9
    basis: reported
    note: Written 吉野丸, first of the four sunk in the Navy's July summary; no time or position given there
    sil: cargo
  - ship: Manko Maru
    role: merchant
    fate: sunk 1944-07-31 (the summary)
    source: jacar:C16120659800
    page: p9
    basis: reported
    note: Written 萬光丸 in the Navy's July summary
    sil: cargo
  - ship: Fuso Maru
    role: merchant
    fate: sunk 1944-07-31 (the summary)
    source: jacar:C16120659800
    page: p9
    basis: reported
    note: Written 扶桑丸 in the Navy's July summary
    sil: cargo
  - ship: Koei Maru
    role: merchant
    fate: sunk 1944-07-31 (the summary)
    source: jacar:C16120644000
    page: p33
    basis: reported
    note: >-
      The fourth sunk. On the July summary's page (C16120659800 p9) the name is in cursive below the others and not
      read (??丸); in the 2nd Demobilization Bureau's copy of the same summary it is written 光栄丸, the first
      character formed like the 光 of 萬光丸 beside it. A copy of the same text, so one record, not two; JANAC has
      Koei Maru (tanker, 10,238 tons) for the night. No time or position in either
  - ship: No. 1 Ogura Maru
    role: merchant
    fate: torpedoed and damaged 1944-07-31 (the summary)
    source: jacar:C16120659800
    page: p9
    basis: reported
    note: Written 第一小倉丸, under 被雷損傷 (torpedoed, damaged) in the Navy's July summary
    sil: tanker
    sil_basis: 'assumed from the name (the Ogura Maru were oilers); the summary does not say'
  - ship: Dakar Maru
    role: merchant
    fate: torpedoed and damaged 1944-07-31 (the summary)
    source: jacar:C16120659800
    page: p9
    basis: reported
    note: Written ダカア丸, under 被雷損傷 (torpedoed, damaged) in the Navy's July summary
    sil: cargo
---

Takao to Manila, sailing at 0500 on 29 July 1944 with sixteen ships and six escorts. The ships carried Army units
and other transport (the Navy's monthly summary for July, p9). From about 0330 on the 31st (Tokyo time) submarines
attacked one after another; the summary gives no position. Four ships were sunk
(Yoshino, Manko, Fuso and Koei Maru: the fourth name is cursive on the July page and written plainly 光栄丸 in
the 2nd Demobilization Bureau's copy of the summary, p33) and two were torpedoed and damaged (No. 1 Ogura
Maru, Dakar Maru). The convoy withdrew for a time to Pangui Bay at the north-west tip of Luzon. PARCHE and STEELHEAD
attacked it that night, at about 19N 121E by their own reckoning. (The 1st Surface Escort's diary has a convoy
"ミ一?" attacked off Cape Bolinao, some 150 nm further south; which convoy and which night are not yet settled.)

The convoy had come south to Takao before that: the 1st Surface Escort's chart has Shiokaze and Shimushu taking up
(ミ一一) at 0600 on 13 July (Shimushu from Sasebo) and reaching Takao on the 21st, where it waited until the 29th.

The copy also notes, beside the entry, a submarine-hunting group of six formed (the type letter not read) and, below
it, that since enemy submarines began to range over the Luzon Strait the results hoped for had not been achieved.

**Searched and not found** (5 Nov 2026): the six ships' names in the JACAR catalogue; the 4th Shipping Transport
Command's Manila branch diaries, which on JACAR end in December 1943; the 31st Special Base Force's diary for July
(the file holds September 1944 onward); No. 1 Ogura Maru or Dakar Maru in the Navy's August summary (C16120659900,
a first read).

**Not yet found**: the other four escorts, the sixteen ships' names, the convoy's arrival at Manila, and each lost
ship's own movement log (the hour and position of her loss).
