---
convoy: HI-69
name_ja: ヒ六九
plain: "a fourteen-ship convoy from Moji to Manila escorted by the carrier Shinyo, July 1944"   # what it was, in a line, ours
from: Moji
to: Manila
via: []
sailed: ""
arrived: 1944-07-20
size: 14
cargo: ""
attacked_by: [ss-217-guardfish/8]
sources:
  - jacar:C08030141100 p28     # 1st Surface Escort war diary, July 1944, chart 別表第二 (Malaya direct route): (ヒ69), 14 ships, escorts, the 18th's marks, Manila on the 20th
  - jacar:C08030141100 p10     # the same diary's narrative (ロ): Tenei Maru and Harima Maru torpedoed about 0800 on the 18th; Kai-17 torpedoed and damaged
route: [moji, w-genkai, w-goto, w-ecs, w-ntw, w-nwtip, w-strait-n, w-strait, w-bashi, w-luzw, w-zamb, w-bataan, w-corr, manila]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1944-07-18 0850 I, place: "", event: attacked, words: "18日0850 N21-58 E119-50 (a mark without words; the narrative has the stragglers torpedoed about 0800)", source: jacar:C08030141100 p28, basis: reported}
  - {at: 1944-07-18 1055 I, place: "", event: attacked, words: "18日1055 N21-36 E119-58 海17（小破）", source: jacar:C08030141100 p28, basis: reported}
  - {at: 1944-07-20, place: manila, event: arrived, words: "the chart: the line reaches （マニラ） on the 20th (a mark at 20日0530 N15-42 E118-37 on the way)", source: jacar:C08030141100 p28, basis: reported}
ships:
  - ship: Shinyo
    role: escort
    source: jacar:C08030141100
    page: p28
    basis: reported
    note: Written 神鷹 in the escorts' cell of (ヒ69) on the chart, beside 香椎, 千振, 佐渡 and two kaibokan (海)
  - ship: Kashii
    role: escort
    source: jacar:C08030141100
    page: p28
    basis: reported
    note: Written 香椎 in the escorts' cell of (ヒ69)
  - ship: Chiburi
    role: escort
    source: jacar:C08030141100
    page: p28
    basis: reported
    note: Written 千振 in the escorts' cell of (ヒ69)
  - ship: Sado
    role: escort
    source: jacar:C08030141100
    page: p28
    basis: reported
    note: Written 佐渡 in the escorts' cell of (ヒ69)
  - ship: Kai-17
    role: escort
    source: jacar:C08030141100
    page: p10
    basis: reported
    fate: torpedoed and damaged 1944-07-18 1055 I at 21-36N 119-58E (chart, p28; 小破 there, 中破 in the narrative)
    note: >-
      Written 海十七 in the narrative: holding down the submarine astern of the convoy, sent to the stragglers, and
      torpedoed because she ran straight at high speed. One of the two 海 in the chart's escorts' cell, whose numbers
      are not settled there
  - ship: Tenei Maru
    role: merchant
    source: jacar:C08030141100
    page: p10
    basis: reported
    fate: torpedoed about 0800 I on 1944-07-18 while straggling (the narrative); not in the July loss list (p27)
    note: Written 天栄丸
  - ship: Harima Maru
    role: merchant
    source: jacar:C08030141100
    page: p10
    basis: reported
    fate: torpedoed about 0800 I on 1944-07-18 while straggling (the narrative); not in the July loss list (p27)
    note: Written 播磨丸
---

HI-69 appears in the 1st Surface Escort Division's July 1944 chart for the Malaya direct route (別表第二) as a
14-ship convoy from Moji to Manila. Its escorts were 香椎, 千振, 佐渡, two kaibokan and the escort carrier Shinyo
(神鷹), with the operations party (九). The chart gives the convoy no date of sailing; it reached Manila on the 20th.
At about 0800 on the 18th, Tenei Maru and Harima Maru were torpedoed while they were catching up with the convoy.
Kai-17 was sent to them from astern of the convoy. She ran straight at high speed and was torpedoed and damaged too.
The chart marks her at 1055, at 21-36N 119-58E (the narrative, p10).

GUARDFISH attacked a fast southbound convoy with two carriers at 1822 I that evening, at 20-27N 119-11E. That is
where a 15-knot convoy bound for Manila would have been. This record has no loss or damage at that hour (Attack 5;
claims.yml).

**Not yet found**: the date HI-69 left Moji, its ships' names, whose attack the morning's was, and Shinyo's or
Kashii's own record of the 18th.
