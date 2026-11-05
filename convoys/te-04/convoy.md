---
convoy: TE-04
name_ja: テ04
plain: "a six-ship Yulin–Moji convoy by way of Keelung, carrying iron ore for Yawata"   # what it was, in a line, ours
from: Yulin (楡林)
to: Moji (門司)
via: [Keelung (基隆)]
sailed: 1944-04-30
arrived: ""
size: 6
cargo: "iron ore for Yawata (secondary)"
attacked_by: [ss-385-bang/1, ss-384-parche/1, ss-283-tinosa/6]
sources:
  - jacar:C08030140600 p33   # April chart 別表第四 (Hainan east route): テ04 leaves 楡林 on the 30th, 6 ships; escort cell cramped
  - jacar:C08030140700 p28   # May chart 別表第三 (Moji–Yulin): the テ04 track, two sinking marks, five ships sunk; survivors to (基隆), then Moji
  - jacar:C08030140700 p26   # May loss list: テ04(2), the five ships with GRT
  - combinedfleet:Daiyoku_t  # secondary: escorts, cargo
route: [yulin, w-hainan, w-scse, w-strait, w-strait-n, w-nwtip, keelung, w-ntw, w-ecs, w-goto, w-genkai, moji]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1944-04-30, place: yulin, event: sailed, words: leaves 楡林 with 6 ships, source: jacar:C08030140600 p33, basis: reported}
ships:
  - ship: Kinrei Maru
    role: merchant
    to: 1944-05-04
    fate: sunk 1944-05-04 0109 I at 20-42N 118-01E, her own log (PARCHE patrol 1 J08; jacar:C08050104500 p30)
    source: jacar:C08030140700
    page: p28
    basis: reported
    note: >-
      Written 金嶺丸 among the five 沈没 (sunk) beside the テ04 track on the May chart 別表第三 (Moji–Yulin) of the 1st
      Surface Escort Division diary; 5947 GRT in the same diary's May loss list (p26). Iron ore for Yawata per
      combinedfleet (secondary); not in this record
    sil: type-k-ore-carrier
    sil_basis: representative
  - ship: Shoryu Maru
    role: merchant
    to: 1944-05-04
    fate: sunk 1944-05-04 0353 I at 20-54N 118-08E, her own log (TINOSA patrol 6 J04; jacar:C08050104900 p4)
    source: jacar:C08030140700
    page: p28
    basis: reported
    note: >-
      Written 昌竜丸 among the five 沈没 (sunk) beside the テ04 track on the May chart 別表第三 (Moji–Yulin) of the 1st
      Surface Escort Division diary; 6475 GRT in the same diary's May loss list (p26). Iron ore for Yawata per
      combinedfleet (secondary); not in this record
    sil: type-k-ore-carrier
    sil_basis: representative
  - ship: Taiyoku Maru
    role: merchant
    to: 1944-05-04
    fate: sunk 1944-05-04 0237 I at 20-56N 118-04E, her own log (BANG patrol 1 J20; jacar:C08050105400 p10)
    source: jacar:C08030140700
    page: p28
    basis: reported
    note: >-
      Written 大翼丸 among the five 沈没 (sunk) beside the テ04 track on the May chart 別表第三 (Moji–Yulin) of the 1st
      Surface Escort Division diary; 5244 GRT in the same diary's May loss list (p26). Iron ore for Yawata per
      combinedfleet (secondary); not in this record
    sil: type-k-ore-carrier
    sil_basis: representative
  - ship: Toyohi Maru
    role: merchant
    to: 1944-05-04
    fate: sunk 1944-05-04 0008 I at 20-51N 118-03E, her own log (TINOSA patrol 6 J06; jacar:C08050105600 p53)
    source: jacar:C08030140700
    page: p28
    basis: reported
    note: >-
      Written 豊日丸 among the five 沈没 (sunk) beside the テ04 track on the May chart 別表第三 (Moji–Yulin) of the 1st
      Surface Escort Division diary; 6436 GRT in the same diary's May loss list (p26). Iron ore for Yawata per
      combinedfleet (secondary); not in this record
    sil: type-k-ore-carrier
    sil_basis: representative
  - ship: Daibu Maru
    role: merchant
    to: 1944-05-04
    fate: sunk 1944-05-03/04 (BANG patrol 1 J11, J14)
    source: jacar:C08030140700
    page: p28
    basis: reported
    note: >-
      Written 大武丸 among the five 沈没 (sunk) beside the テ04 track on the May chart 別表第三 (Moji–Yulin) of the 1st
      Surface Escort Division diary; 6440 GRT in the same diary's May loss list (p26). Iron ore for Yawata per
      combinedfleet (secondary); not in this record
    sil: type-k-ore-carrier
    sil_basis: representative
  - ship: CD-1
    role: escort
    source: combinedfleet:Daiyoku_t
    basis: secondary
    note: >-
      Named by combinedfleet. The April chart's escort cell for テ04 (jacar:C08030140600 p33) is cramped; its first
      characters may read 海一 (CD-1), not read with confidence
    sil: kaibokan1
    sil_basis: class
  - ship: Kazan Maru
    role: escort
    source: combinedfleet:Daiyoku_t
    basis: secondary
    note: Auxiliary gunboat. Named by combinedfleet only
    sil: gunboat
  - ship: Maeshima
    role: escort
    source: combinedfleet:Daiyoku_t
    basis: secondary
    note: Minelayer, joined 3 May. Named by combinedfleet only
    sil: escort
---

Yulin to Moji, leaving Yulin on 30 April 1944 with six ships (April chart). The May chart draws the northbound
track with two sinking marks and lists five ships sunk: 金嶺丸 昌竜丸 大翼丸 豊日丸 大武丸; the rest of the convoy is
drawn into (基隆) Keelung for supplies (補給) and on to Moji. Six ships less five sunk leaves one survivor (inferred).

The chart's time and position beside the marks are faint: read 「4日 22?9」 N2?-46 E118-?4, low confidence; not
paired with any one boat's attack. BANG, PARCHE and TINOSA attacked between the evening of the 3rd and the early
hours of the 4th (engagement `luzon-strait-1944`, which weighs who sank which).

**Cargo: iron ore for Yawata** per combinedfleet.com (secondary); not in the escort division's record. The escorts
are combinedfleet's; the April chart's escort cell can't be read with confidence.

The retired battle page listed a sixth ship, "Yulin", from combinedfleet.com; that is the port of departure, not a
ship, and is left out. The sixth ship (the survivor) is not named in the record.
