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
attacked_by: [ss-364-hammerhead/1, ss-384-parche/2, ss-280-steelhead/6]
sources:
  - jacar:C16120659800 p9      # the Navy's July 1944 summary, 31st: the 16-ship convoy (6 escorts) from Takao on the 29th, attacked from about 0330; ships sunk and damaged
  - jacar:C08030141100 p15     # 1st Surface Escort war diary, July 1944, chart 麾下艦船部隊ノ行動 (其ノ一): the escorts' row names
  - jacar:C08030141100 p16     # the same chart, days 10-22: (ミ一一) with Shiokaze and Shimushu from the 13th, to Takao on the 21st
  - jacar:C08030141100 p17     # the same chart, days 20-31: Shimushu and Kazan Maru sail from Takao with (ミ一一) at 0500 on the 29th
  - jacar:C16120644000 p33     # the 2nd Demobilization Bureau's copy of the same summary, the 31st: the same entry, the fourth sunk ship written 光栄丸, and a submarine-hunting group formed
  - jacar:C08030141100 p27     # the same diary, 別表第一 (convoy statistics): MI-11 met submarines twice in July; the loss list with tonnage; No. 1 Ogura Maru and Dakar Maru slightly damaged (小破)
  - jacar:C08030141400 p19     # 1st Surface Escort war diary, August 1944, chart (其ノ二), days 1-10: Kazan Maru escorts the torpedoed No. 1 Ogura Maru to Santa Cruz and Corregidor; Shimushu on MI-11 rescue; Harukaze joins MI-11; both then at Manila
  - jacar:C08030141400 p11     # the same August diary's narrative: the submarine-hunting group of six (three pairs) formed on 28 July
  - jacar:C08030141400 p20     # the August chart, days 11-25: Shimushu at Miri (ミリ) and away with (ミ一二)
  - jacar:C08030211100 p3      # 21st Minesweeper Division war diary, August 1944, days 1-2: survivors; Dakar Maru adrift, taken in to Calayan Island
  - jacar:C08030141100 p6      # the same diary's narrative: a convoy ミ一? attacked off Cape Bolinao; Harukaze and Kai-26 sent to hunt and rescue (which convoy, and when, uncertain)
route: [takao, w-bashi, w-luzw, w-bataan, w-corr, manila]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1944-07-13 0600 I, place: "", event: sailed, words: "the chart: Shiokaze and Shimushu (Shimushu from Sasebo) take up (ミ一一) at 0600 on the 13th; the first leg's port of departure is not written for the convoy", source: jacar:C08030141100 p16, basis: reported}
  - {at: 1944-07-21, place: takao, event: arrived, words: "the chart: both escorts reach Takao on the 21st (the times, about 1245 and 1800, are small and not yet re-read)", source: jacar:C08030141100 p16, basis: reported}
  - {at: 1944-07-29 0500 I, place: takao, event: sailed, words: "the chart: 高雄 〇五〇〇 ＝（ミ一一）＝ for Shimushu and Kazan Maru; the summary: 29日高雄ヲ出港シマニラニ向ケ航行中", source: jacar:C08030141100 p17, basis: reported}
  - {at: 1944-07-31 0330 I, place: "", event: attacked, words: "0330頃連続敵潜ノ襲撃ヲ受ク (attacked by submarines one after another from about 0330); no position given. The 1st Surface Escort's narrative has a convoy attacked off Cape Bolinao (「ボリナオ」岬沖), but the convoy's number written ミ一? (the second figure not seen), and Cape Bolinao (about 16-20N) is some 150 nm south of the boats' attack positions (about 19N), so this may be another convoy, or a later attack on MI-11 on its way south from Pangui Bay", source: jacar:C16120659800 p9, basis: reported}
  - {at: 1944-07-30, place: "", event: attacked, words: "the escort division's July statistics count MI-11 as meeting submarines twice (ミ11(2)), undated; HAMMERHEAD attacked it on the 30th (0531-0537 I by her report), and the summary has no loss that day", source: jacar:C08030141100 p27, basis: derived}
  - {at: 1944-07-31, place: "", event: sheltered, words: "船団ハ一時パングイ湾（ルソン島北西端）ニ避退 (the convoy withdrew for a time to Pangui Bay, the north-west tip of Luzon)", source: jacar:C16120659800 p9, basis: reported}
  - {at: 1944-08-01, place: "", event: rescue, words: "the 21st Minesweeper Division's diary: Minesweepers 38 and 39 (of the hunting group) with survivors at Pangui Bay; 39 moves survivors to sailing vessels and guards Dakar Maru and Fukuju Maru; 38 sails from Pangui Bay at 1325 for the place of Dakar Maru's rescue", source: jacar:C08030211100 p3, basis: reported}
  - {at: 1944-08-02 1320 I, place: "", event: rescue, words: "だかあ丸漂流位置ニ到着 (Minesweeper 39 arrives at Dakar Maru's drifting position); at 1340 Dakar Maru and Fukuju Maru in to the anchorage at Calayan Island, the minesweeper patrolling off it; the drifting position is not written", source: jacar:C08030211100 p3, basis: reported}
  - {at: 1944-08-03, place: manila, event: arrived, words: "the August chart: Shimushu (on ミ一一救助, MI-11 rescue, from the 1st) and Harukaze (with ミ一一 from the 1st) both read マニラ from about the 3rd; the day read from the column rules, the stamps' times not read; the convoy's own arrival not written", source: jacar:C08030141400 p19, basis: derived, approx: true}
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
      0500 on the 29th (p17). The day columns are read from the column rules. In August's chart (C08030141400 p19)
      on "(ミ一一救助)", MI-11 rescue, from the 1st to about the 3rd, then at Manila
    sil: shimushu
    sil_basis: 'class, assumed'
  - ship: Shimushu (onward)
    role: escort
    from: 1944-08-07
    source: jacar:C08030141400
    page: p19
    basis: reported
    note: >-
      The August chart's later （ミ一一） in Shimushu's row: she sails from Manila with (ミ一一) about the 7th-8th and
      is at Miri (ミリ) from about the 12th (p19-p20), then sails north with (ミ一二), MI-12, about the 16th (p20).
      So MI-11 went on from Manila to Miri, as the MI convoys did; which of its ships went on is not written. The days
      are read from the column rules; the stamps' times are not read
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
      found. In August's chart (C08030141400 p19) she stays with (ミ一一) into the 1st, then escorts "(第一小倉丸 被雷船)",
      the torpedoed No. 1 Ogura Maru, shelters at Santa Cruz (サンタクルスニ避泊) about the 4th and brings her on to
      Corregidor (コレヒドール) about the 5th-6th
    sil: gunboat
  - ship: Harukaze
    role: escort
    from: 1944-07-31
    source: jacar:C08030141100
    page: p6
    basis: reported
    note: >-
      Written 春風. Sent with 海二六 (Kaibokan No. 26) to hunt the submarines and rescue, after a convoy was attacked off
      Cape Bolinao (the diary's narrative). In August's chart (C08030141400 p19) her row reads (單), then (ミ一一) from
      the 1st, then Manila from about the 3rd: so she joined the convoy for its last leg. Whether that was this attack is uncertain: the convoy's number written ミ一? (the second figure not seen), and Cape Bolinao (about 16-20N) is some 150 nm south of the boats' attack positions (about 19N), so this may be another convoy, or a later attack on MI-11 on its way south from Pangui Bay; not part of the
      convoy's escort
  - ship: Yoshino Maru
    role: merchant
    fate: sunk 1944-07-31 (the summary)
    source: jacar:C16120659800
    page: p9
    basis: reported
    note: >-
      Written 吉野丸, first of the four sunk in the Navy's July summary; no time or position given there. 8990 tons in
      the 1st Surface Escort's July loss list (C08030141100 p27)
    sil: cargo
  - ship: Manko Maru
    role: merchant
    fate: sunk 1944-07-31 (the summary)
    source: jacar:C16120659800
    page: p9
    basis: reported
    note: Written 萬光丸 in the Navy's July summary; 万光丸 (4471 tons) in the 1st Surface Escort's July loss list (C08030141100 p27)
    sil: cargo
  - ship: Fuso Maru
    role: merchant
    fate: sunk 1944-07-31 (the summary)
    source: jacar:C16120659800
    page: p9
    basis: reported
    note: Written 扶桑丸 in the Navy's July summary; 81?5 tons (the third figure not certain) in the 1st Surface Escort's July loss list (C08030141100 p27)
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
      Koei Maru (tanker, 10,238 tons) for the night. The 1st Surface Escort's July loss list (C08030141100 p27) also
      writes 光栄丸, at 1,0000 (10,000) tons. No time or position in any of them
  - ship: No. 1 Ogura Maru
    role: merchant
    fate: torpedoed and damaged 1944-07-31 (the summary); slightly damaged (小破), escorted to Corregidor about 5-6 August
    source: jacar:C16120659800
    page: p9
    basis: reported
    note: >-
      Written 第一小倉丸, under 被雷損傷 (torpedoed, damaged) in the Navy's July summary; 小破 (slightly damaged) in the 1st
      Surface Escort's July loss list (C08030141100 p27). Its August chart (C08030141400 p19) has Kazan Maru escorting
      her, "the torpedoed ship", to shelter at Santa Cruz and on to Corregidor, so she stayed afloat
    sil: tanker
    sil_basis: 'assumed from the name (the Ogura Maru were oilers); the summary does not say'
  - ship: Dakar Maru
    role: merchant
    fate: torpedoed and damaged 1944-07-31 (the summary); adrift on 2 August and taken in to Calayan Island (21st Minesweeper Division)
    source: jacar:C16120659800
    page: p9
    basis: reported
    note: >-
      Written ダカア丸, under 被雷損傷 (torpedoed, damaged) in the Navy's July summary; だかあ丸, 小破 (slightly damaged), in
      the 1st Surface Escort's July loss list (C08030141100 p27). JANAC has her sunk; both Japanese lists have her
      damaged. The 21st Minesweeper Division's August diary (C08030211100 p3) settles it for 2 August: Minesweeper 39
      reached her "drifting position" (漂流位置) at 1320 and saw her, with Fukuju Maru (福寿丸), in to the anchorage at
      Calayan Island at 1340; Minesweeper 38 had sailed from Pangui Bay at 1325 on the 1st to rescue her. Afloat, not
      sunk; her movements after Calayan are not yet found
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

The hunting group of six was the 1st Surface Escort's, formed on 28 July in three pairs (Minesweepers 38 and 39;
Asakaze and Yashiro; Kusagaki and Matsuwa; August diary p11). Minesweepers 38 and 39 were at Pangui Bay with
survivors on 1 August, and on the 2nd Minesweeper 39 found Dakar Maru adrift and saw her in to Calayan Island
(the 21st Minesweeper Division's August diary, p3): she was damaged, not sunk, as JANAC has her. Shimushu took the
convoy on from Manila to Miri about 7-12 August (the August chart, pp. 19-20).

**Searched and not found** (5 Nov 2026): the six ships' names in the JACAR catalogue; the 4th Shipping Transport
Command's Manila branch diaries, which on JACAR end in December 1943; the 31st Special Base Force's diary for July
(the file holds September 1944 onward); No. 1 Ogura Maru or Dakar Maru in the Navy's August summary (C16120659900,
a first read).

The 1st Surface Escort's own tables (July diary p27, August diary p19) add: the convoy met submarines twice in July
(HAMMERHEAD's attack on the 30th, then the boats' on the 31st, though the table doesn't date them); the four sunk
with their tonnage (Koei Maru 10,000, Yoshino 8990, Fuso 81?5, Manko 4471); both damaged ships only slightly damaged
(小破); No. 1 Ogura Maru escorted by Kazan Maru to shelter at Santa Cruz and then to Corregidor about 4-6 August;
Shimushu on "MI-11 rescue" and Harukaze joining for the last leg, both at Manila from about 3 August.

**Not yet found**: the other escorts, the sixteen ships' names, the convoy's own arrival at Manila (about 3 August
from the escorts' rows), Dakar Maru's later movements, and each lost ship's own movement log (the hour and position
of her loss). Searched, no hits (5 Nov 2026): JACAR for Shimushu's, Kazan Maru's, Harukaze's, Yashiro's and Kusagaki's own war
diaries or action reports, July-September 1944. Not yet read: the 21st Minesweeper Division's July 1944 diary (perhaps
in C08030210300), which may have the night itself.
