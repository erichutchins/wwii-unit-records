---
convoy: TAMA-21C
name_ja: タマ二一C
plain: "a twenty-ship Takao–Manila convoy that lost six ships in the Luzon Strait on 16-17 July 1944"   # what it was, in a line, ours
from: Takao
to: Manila
via: []
sailed: 1944-07-14
arrived: ""
size: 20
cargo: "Seattle Maru carried 4,300 troops (部隊4300名); the rest not recorded"
attacked_by: [ss-389-piranha/1, ss-217-guardfish/8, ss-200-thresher/13]
sources:
  - jacar:C08030141100 p33     # 1st Surface Escort war diary, July 1944, chart 別表第七 (Philippines north route): タマ21C, 20 ships, escorts, the attack span and the six sunk
  - jacar:C08030141100 p10     # the same diary's narrative (ハ): Seattle Maru sunk the morning of the 16th; five more before dawn on the 17th
  - jacar:C08030141100 p27     # the same diary's July loss list, with gross tons
  - jacar:C16120659800 p5      # the Imperial Navy's July 1944 summary, the 16th: the Takao-Manila convoy (8 escorts, 21 transports), Seattle Maru at 1030, one more at midnight
route: [takao, w-bashi, w-luzw, w-bataan, w-corr, manila]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1944-07-14, place: takao, event: sailed, words: "the chart: タマ21C's line leaves 高雄 on the 14th (read from the day columns)", source: jacar:C08030141100 p33, basis: reported, approx: true}
  - {at: 1944-07-16 0945 I, place: "", event: attacked, words: "自16日0945 N19-17 E120-15 (the attacks begin; Seattle Maru sank at 1030, the summary)", source: jacar:C08030141100 p33, basis: reported}
  - {at: 1944-07-17 0345 I, place: "", event: attacked, words: "至17日0345 N18-53 E119-44 (the attacks end); しやとる、日山、祥山、満泰、西寧、仁山（沈没）", source: jacar:C08030141100 p33, basis: reported}
  - {at: 1944-07-19, place: manila, event: arrived, words: "the chart: the line reaches マニラ about the 19th (read from the day columns)", source: jacar:C08030141100 p33, basis: reported, approx: true}
ships:
  - ship: Seattle Maru
    role: merchant
    to: 1944-07-16
    fate: sunk 1944-07-16 1030 I north of Luzon (the summary, jacar:C16120659800 p5)
    source: jacar:C08030141100
    page: p33
    basis: reported
    note: >-
      Written しやとる丸 among the six sunk on the chart; Army-requisitioned, 5773 tons, 4,300 troops (the summary,
      C16120659800 p5). PIRANHA's by JANAC (secondary; janac:6/p29)
  - ship: Mantai Maru
    role: merchant
    to: 1944-07-17
    fate: sunk before dawn on 17 July 1944 (the diary; no hour for her). JANAC credits GUARDFISH, 16 July (janac:6/p18)
    source: jacar:C08030141100
    page: p33
    basis: reported
    note: Written 満泰 on the chart; 満泰丸 (5863) in the loss list (p27)
  - ship: Jinzan Maru
    role: merchant
    to: 1944-07-17
    fate: sunk before dawn on 17 July 1944 (the diary; no hour for her). JANAC credits GUARDFISH, 16 July (janac:6/p18)
    source: jacar:C08030141100
    page: p33
    basis: reported
    note: Written 仁山 on the chart; 仁山丸 (5215) in the loss list (p27)
  - ship: Hiyama Maru
    role: merchant
    to: 1944-07-17
    fate: sunk before dawn on 17 July 1944 (the diary; no hour for her). JANAC credits GUARDFISH, 17 July (janac:6/p18)
    source: jacar:C08030141100
    page: p33
    basis: reported
    note: Written 日山 on the chart; 日山丸 (2800) in the loss list (p27). The reading Hiyama is JANAC's (secondary)
  - ship: Sainei Maru
    role: merchant
    to: 1944-07-17
    fate: sunk before dawn on 17 July 1944 (the diary; no hour for her). JANAC credits THRESHER (janac:6/p50)
    source: jacar:C08030141100
    page: p33
    basis: reported
    note: Written 西寧 on the chart; 西寧丸 (4916) in the loss list (p27)
  - ship: Shozan Maru
    role: merchant
    to: 1944-07-17
    fate: sunk before dawn on 17 July 1944 (the diary; no hour for her). JANAC credits THRESHER (janac:6/p50)
    source: jacar:C08030141100
    page: p33
    basis: reported
    note: Written 祥山 on the chart; 祥山丸 (2856) in the loss list (p27)
---

TAMA-21C, a Takao–Manila convoy, appears in the 1st Surface Escort Division's July 1944 chart (別表第七) as 20 ships
with the operations party (一) and seven escorts. The escorts' cell is partly legible: 海一, 海二, 草垣, 掃?三?, 前?島,
円島, 駆?六二. The Navy's summary gives the convoy as 8 escorts and 21 transports (C16120659800 p5). The convoy left
Takao on the 14th. The first attack came on the morning of the 16th, and Seattle Maru sank at 1030 with 4,300 troops
on board. Because of her sinking the convoy sailed in two parts, the ships rescuing her and the convoy
("沈没ノ為之ガ救助船団ト二分航行中", re-read at 500 dpi; neither part's ships are given). Before dawn on the 17th an enemy submarine that had followed the
convoy sank five more ships (the narrative, p10). The chart puts the attacks between 19-17N 120-15E (16th, 0945) and
18-53N 119-44E (17th, 0345). The convoy reached Manila about the 19th. Afterwards the division ordered a meeting to
study the attack and sent a staff officer to Manila.

PIRANHA's attack on the 16th (0944 I, Attack 2) opened the chart's span a minute before its 0945 start. GUARDFISH
attacked a ten-ship body on the night of 16-17 July (Attacks 1-4, 2342 to 0303 I, about 18-20N 119-45E), and THRESHER
a six-ship group (1 AO, 3 AK, 2 escorts) about 50 miles to the north (Attacks 1-3, 0029 to 0344 I, 18-55N 119-44E
to 19-04N 119-26E). The two bodies are taken for the narrative's two parts (inferred). The chart's span ends at 0345
I at 18-53N 119-44E: one minute after THRESHER's last firing and 2 nm from her first attack's position, so its end is
THRESHER's. The Japanese record names the six ships sunk but gives
none of them an hour, so it can't say which boat sank which ship. JANAC's credits are given with each ship.

**Not yet found**: the twenty ships' other names, the escorts' cell read in full, each lost ship's own movement log
(the designated-ship movement tables), and which part of the split convoy each lost ship was in.
