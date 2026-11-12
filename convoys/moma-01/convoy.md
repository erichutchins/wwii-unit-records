---
convoy: MOMA-01
name_ja: モマ01
plain: "a convoy for Manila that lost the troop transport Nichiran Maru east of northern Luzon on 12 July 1944"   # what it was, in a line, ours
from: Takao
to: Manila
via: []
sailed: 1944-07-09
arrived: ""
size: ""
cargo: "Nichiran Maru carried Army troops (陸軍部隊輸送); the rest not recorded"
attacked_by: [ss-308-apogon/4, ss-389-piranha/1]
sources:
  - jacar:C08030141100 p33     # 1st Surface Escort war diary, July 1944, chart 別表第七 (Philippines north route): the line headed モマ01, Takao the 9th to Manila about the 15th; Nichiran Maru sunk 12th 0745
  - jacar:C16120659800 p5      # the Imperial Navy's July 1944 summary, the 12th: Nichiran Maru (Army-requisitioned, 6503 t, Army troops) torpedoed and sunk, 0935
route: []   # the chart draws no track; the attacks were east of northern Luzon (APOGON 19-11N 122-38E, PIRANHA 18-33N 122-53E), off the lanes in reference/lanes/lanes.yml
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1944-07-09, place: takao, event: sailed, words: "the chart: the line headed モマ01 leaves 高雄 on the 9th (read from the day columns)", source: jacar:C08030141100 p33, basis: reported, approx: true}
  - {at: 1944-07-12 0745 I, place: "", event: attacked, words: "12日0745 N18-?9 E122-?0 日蘭丸（沈没）", source: jacar:C08030141100 p33, basis: reported}
  - {at: 1944-07-15, place: manila, event: arrived, words: "the chart: the line reaches マニラ about the 15th (read from the day columns)", source: jacar:C08030141100 p33, basis: reported, approx: true}
ships:
  - ship: Nichiran Maru
    role: transport
    to: 1944-07-12
    fate: sunk 1944-07-12 0745 I at 18-?9N 122-?0E (the chart; 0935 in the summary, jacar:C16120659800 p5)
    source: jacar:C08030141100
    page: p33
    basis: reported
    note: >-
      Written 日蘭丸（沈没） on the chart's モマ01 line; 陸軍部隊輸送ノ日蘭丸（A徴傭6503t） in the summary. Read Nichiran
      after JANAC (secondary), which credits PIRANHA (janac:6/p29)
---

MOMA-01 is a line on the 1st Surface Escort Division's July 1944 chart of the Philippines north route (別表第七),
headed モマ01: it leaves Takao on the 9th and reaches Manila about the 15th. Its escort and ship-count cells are
blank. ("モマ" reads as Moji–Manila by the division's naming, モ for 門司 and マ for マニラ (inferred); the chart shows
only its Takao–Manila leg.) Its one mark is Nichiran Maru, an Army transport carrying troops, sunk at 0745 on the 12th
at 18-?9N 122-?0E (the second figures of the minutes are lost in the binding); the Imperial Navy's summary times her loss at
0935, north-west of Luzon as written ("N西方"), though the boats' positions put the convoy east of northern Luzon.

APOGON attacked it at 0304 I on the 12th at 19-11N 122-38E (three hits heard, then rammed by one of the convoy), and
PIRANHA at 0656 I at 18-33N 122-53E (Nichiran Maru, by JANAC, secondary). That this was the convoy both boats attacked
is inferred: the chart has no other line at sea there that morning, and the convoy's course (180, 13-14 kt) and the
two positions agree. GUARDFISH and THRESHER tracked it but did not fire.

**Not yet found**: the convoy's ships and escorts, its sailing from Moji, Nichiran Maru's own movement log, and any
record of the ship that rammed APOGON or of damage from APOGON's three hits.
