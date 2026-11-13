---
convoy: No. 91
name_ja: 第九一船団
plain: "a four-ship Takao–Hong Kong convoy, known mostly from a secondary source"   # what it was, in a line, ours
from: Takao (secondary)
to: Hong Kong (secondary)
via: []
sailed: "1944-07-01 (inferred: its escort Kuri left Takao that day)"
arrived: "1944-07-05 (inferred: Kuri reached Hong Kong at 1540 I, Hatsukari at 1908 I)"
size: 4 (secondary)
cargo: "anti-aircraft guns and ammunition in Gyoun Maru (secondary); the rest not recorded"
attacked_by: [ss-304-seahorse/5, ss-385-bang/2]
sources:
  - jacar:C08030032900 p27   # narrative: 第九一船団 attacked SW of Pratas on the 4th; escorts Kuri, Hatsukari
  - industrialhistoryhk:29957  # secondary: BAAG summary for Gyoun Maru; a reader's comment on TA-406 and No. 91
  - jacar:C08030032900 p28   # submarine table: Kuri's three reports (Nitto Maru; no damage; Gyoyu, No. 28 Kyodo)
  - jacar:C08030032900 p42   # the fleet's chart of its ships' movements, July: Kuri at Takao on the 1st, at sea, Hong Kong 5th 1540; Hatsukari at sea from the 1st, Hong Kong 5th 1908
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1944-07-01, place: takao, event: sailed, words: "Kuri at Takao (高雄) on the 1st, then at sea; the time beside it, 一一??, partly read", source: jacar:C08030032900 p42, basis: inferred}
  - {at: 1944-07-05 1540 I, place: hong-kong, event: arrived, words: "Kuri's block at Hong Kong (香港) opens 一五四〇 on the 5th; Hatsukari's 一九〇八", source: jacar:C08030032900 p42, basis: inferred}
route: [takao, w-bashi, w-scse, w-s91, hong-kong]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
ships:
  - ship: Kuri
    role: escort
    source: jacar:C08030032900
    page: p27
    basis: reported
    note: >-
      Destroyer. Named as escort (護衛艦栗) of 第九一船団 on 4 July; sent the convoy's reports in the submarine table (p28)
    sil: wakatake
    sil_basis: class
  - ship: Hatsukari
    role: escort
    source: jacar:C08030032900
    page: p27
    basis: reported
    note: >-
      Torpedo boat. Named as escort (初雁) of 第九一船団 on 4 July; at 1055 reported a periscope sighted and attacked,
      oil brought up (p28)
    sil: chidori
    sil_basis: class
  - ship: Nitto Maru
    role: merchant
    to: 1944-07-04
    fate: sunk 1944-07-04 0100 I, 19-21N 115-50E (SEAHORSE patrol 5 J01)
    source: jacar:C08030032900
    page: p28
    basis: inferred
    note: >-
      日東丸. In the convoy by inference: Kuri reported her sinking, and the narrative (p27) puts 第九一船団 under attack
      that day
    sil: cargo
  - ship: Gyoyu Maru
    role: merchant
    to: 1944-07-04
    fate: sunk 1944-07-04 1345 I, 20-18N 115-02E (SEAHORSE patrol 5 J02)
    source: jacar:C08030032900
    page: p28
    basis: inferred
    note: 暁勇丸. In the convoy by inference, as Nitto Maru
    sil: cargo
  - ship: No. 28 Kyodo Maru
    role: merchant
    to: 1944-07-04
    fate: sunk 1944-07-04 1345 I, 20-18N 115-02E (SEAHORSE patrol 5 J02)
    source: jacar:C08030032900
    page: p28
    basis: inferred
    note: 第二八共同丸. In the convoy by inference, as Nitto Maru
    sil: cargo
  - ship: Gyoun Maru
    role: merchant
    to: 1944-07-05
    cargo: anti-aircraft guns, ammunition
    cargo_for: Hong Kong
    source: industrialhistoryhk:29957
    basis: secondary
    note: >-
      Also read Agekumo Maru; ex Ethel Moller, 912 GRT (the comment). The post summarises a BAAG report: arrived
      Hong Kong from Shanghai via Formosa, inward cargo anti-aircraft guns and ammunition, discharged 21-22 July
      to the Tsim Sha Tsui barracks; it dates the arrival 20 July. A reader's comment (P. Cundall, 4 Dec 2018, no
      source cited) puts her in TA-406 Shanghai to Takao and then No. 91 Takao to Hong Kong with Nitto, Kyodo No.
      28 and Gyoyu Maru, the only one of four to survive, arriving 5 July. Not yet in a Japanese record
    sil: cargo
---

Attacked southwest of Pratas Island (東沙島) on 4 July 1944; the diary estimated two or three submarines. SEAHORSE's
attacks pair with Kuri's two sinking reports by time and place; BANG's with Kuri's 0515 "no damage" report by
time alone (inferred). **Ports, cargo and the number of ships are not recorded** in the 2nd China Expeditionary
Fleet diary. "To Hong Kong" is inferred from the course on SEAHORSE's attack sheets (270, then 320–335) and the
escorts, which were Hong Kong's (Kuri and Hatsukari escort another convoy off 碣石湾 on 29 July, p26).
SEAHORSE counted five freighters and two destroyers with other escorts.

A secondary account fills in the route: a reader's comment on the Industrial History of Hong Kong post about
Gyoun Maru (industrialhistoryhk:29957, no source cited) says four ships came from Shanghai to Takao as TA-406 and
went on to Hong Kong as No. 91, and that Gyoun Maru alone survived, reaching Hong Kong on 5 July. The post's BAAG
summary has her inward cargo as anti-aircraft guns and ammunition (but an arrival date of 20 July). Four ships
agrees with three sunk and one surviving; SEAHORSE counted five freighters.

To find: a Japanese record of the sailing port (Takao, Manila or Yulin), and whether Nitto, Gyoyu or No. 28 Kyodo Maru has a
movement log with her cargo.
