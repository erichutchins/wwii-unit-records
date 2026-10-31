---
convoy: HI-67
name_ja: ヒ67
from: Moji
to: Singapore (昭南)
via: [Manila]
sailed: 1944-06-20
arrived: 1944-07-09
size: 12
cargo: ""
attacked_by: [ss-385-bang/2]
sources:
  - jacar:C08030141000 p34   # June chart: 12 ships, escorts, track to (マニラ), BANG's torpedo mark
  - jacar:C08030141100 p28   # July chart: (ヒ67) Manila to 昭南, 7 ships, 3-9 July
  - combinedfleet:Miri_t     # secondary: sailed Moji 1930 on 20 June, the ships' names
route: [moji, w-genkai, w-goto, w-ecs, w-ntw, w-nwtip, w-strait-n, w-strait, w-bashi, w-luzw, w-zamb, w-bataan, w-corr, manila, w-corr, w-scs1, w-scs2, w-scs3, singapore]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
voyage:                     # stops and known points, Tokyo time (I), each cited
  - {at: 1944-06-20 1930 I, place: moji, event: sailed, source: combinedfleet:Miri_t, basis: secondary}
  - {at: 1944-06-22, event: joined, words: Kurahashi joins from Sasebo; the escort chart's track begins, source: jacar:C08030141000 p34, basis: reported}
  - {at: 1944-06-30, place: manila, event: arrived, words: about the 30th (the chart's track ends at マニラ), source: jacar:C08030141000 p34, basis: reported, approx: true}
  - {at: 1944-07-03, place: manila, event: sailed, words: leaves Manila with 7 ships, source: jacar:C08030141100 p28, basis: reported}
  - {at: 1944-07-09, place: singapore, event: arrived, words: reaches 昭南 (Singapore), source: jacar:C08030141100 p28, basis: reported}
ships:
  - ship: Shirataka
    role: escort
    to: 1944-07-09
    source: jacar:C08030141000
    page: p34
    basis: reported
    note: >-
      Minelayer. Written 白鷹 in the escort column of 1st Surface Escort Division war diary, June 1944, chart 別表第二
      (convoy escort, Malay direct route), column ヒ67: escorts written in two lines as 白鷹 倉橋 平戸 海五 海三(十三?) 駆?(8) P
      朝顔 呉竹 海二; 12 ships (船団隻数 12). Also in the July chart's (ヒ67) column, written 白鷹 平戸 倉橋 with 海十三, Manila to
      Shonan, 7 ships (jacar:C08030141100 p28); arrival at 昭南 (Singapore) on the 9th from the chart's track
    sil: shirataka
    sil_basis: own
  - ship: Kurahashi
    role: escort
    to: 1944-07-09
    source: jacar:C08030141000
    page: p34
    basis: reported
    note: >-
      Kaibokan. Written 倉橋 in the escort column of 1st Surface Escort Division war diary, June 1944, chart 別表第二
      (convoy escort, Malay direct route), column ヒ67: escorts written in two lines as 白鷹 倉橋 平戸 海五 海三(十三?) 駆?(8) P
      朝顔 呉竹 海二; 12 ships (船団隻数 12). Also in the July chart's (ヒ67) column, written 白鷹 平戸 倉橋 with 海十三, Manila to
      Shonan, 7 ships (jacar:C08030141100 p28); arrival at 昭南 (Singapore) on the 9th from the chart's track
    sil: mikura
    sil_basis: class
  - ship: Hirado
    role: escort
    to: 1944-07-09
    source: jacar:C08030141000
    page: p34
    basis: reported
    note: >-
      Kaibokan. Written 平戸 in the escort column of 1st Surface Escort Division war diary, June 1944, chart 別表第二
      (convoy escort, Malay direct route), column ヒ67: escorts written in two lines as 白鷹 倉橋 平戸 海五 海三(十三?) 駆?(8) P
      朝顔 呉竹 海二; 12 ships (船団隻数 12). Also in the July chart's (ヒ67) column, written 白鷹 平戸 倉橋 with 海十三, Manila to
      Shonan, 7 ships (jacar:C08030141100 p28); arrival at 昭南 (Singapore) on the 9th from the chart's track
    sil: shimushu
    sil_basis: 'class, assumed: the plate names Etorofu and Hachijo, not Hirado'
  - ship: CD-5
    role: escort
    to: 1944-07-03
    source: jacar:C08030141000
    page: p34
    basis: reported
    note: >-
      Kaibokan. Written 海五 in the escort column of 1st Surface Escort Division war diary, June 1944, chart 別表第二
      (convoy escort, Malay direct route), column ヒ67: escorts written in two lines as 白鷹 倉橋 平戸 海五 海三(十三?) 駆?(8) P
      朝顔 呉竹 海二; 12 ships (船団隻数 12). Not in the July (ヒ67) column (jacar:C08030141100 p28): so left HI-67 at Manila
      (inferred)
    sil: kaibokan1
    sil_basis: class
  - ship: CD-13
    role: escort
    source: jacar:C08030141000
    page: p34
    basis: reported
    note: >-
      Kaibokan. Written 海三 in the June chart (jacar:C08030141000 p34), where the 十 is not clear; written 海十三 (十 is
      a short stroke between 海 and 三: 十三 probable) in the July chart of the same diary, column (ヒ67), Manila to
      Shonan (jacar:C08030141100 p28)
    sil: kaibokan1
    sil_basis: class
  - ship: CH-61
    role: escort
    source: combinedfleet:Shirataka_t
    basis: secondary
    note: >-
      Subchaser. Named by combinedfleet.com (secondary). The chart's sixth escort is written 駆 over an unclear
      figure with (8): possibly 駆潜 (subchaser), not read with confidence (jacar:C08030141000 p34)
    sil: escort
  - ship: Asagao
    role: escort
    to: 1944-07-03
    source: jacar:C08030141000
    page: p34
    basis: reported
    note: >-
      Destroyer. Written 朝顔 after a mark P in the escort column of 1st Surface Escort Division war diary, June
      1944, chart 別表第二 (convoy escort, Malay direct route), column ヒ67: escorts written in two lines as 白鷹 倉橋 平戸
      海五 海三(十三?) 駆?(8) P 朝顔 呉竹 海二; 12 ships (船団隻数 12). combinedfleet.com has these three joining at sea on or
      about 26 June (Miri_t) or 30 June (Kurahashi_t); the mark may show ships that joined later (inferred); or,
      like the flag over (8) in the July chart's 運航指揮班 row, it may be a command or group marker. Not in the July
      (ヒ67) column; written 呉竹 朝顔 海二 as escorts of convoy マ?04 (read マ204 or マユ04), 6 ships, leaving Manila on the
      3rd for 楡林 (Yulin), chart 別表第十 (Hainan southeast route) (jacar:C08030141100 p36); combinedfleet calls it
      MAYU-04 (Kuretake_t)
    sil: wakatake
    sil_basis: class
  - ship: Kuretake
    role: escort
    to: 1944-07-03
    source: jacar:C08030141000
    page: p34
    basis: reported
    note: >-
      Destroyer. Written 呉竹 after a mark P in the escort column of 1st Surface Escort Division war diary, June
      1944, chart 別表第二 (convoy escort, Malay direct route), column ヒ67: escorts written in two lines as 白鷹 倉橋 平戸
      海五 海三(十三?) 駆?(8) P 朝顔 呉竹 海二; 12 ships (船団隻数 12). combinedfleet.com has these three joining at sea on or
      about 26 June (Miri_t) or 30 June (Kurahashi_t); the mark may show ships that joined later (inferred); or,
      like the flag over (8) in the July chart's 運航指揮班 row, it may be a command or group marker. Not in the July
      (ヒ67) column; written 呉竹 朝顔 海二 as escorts of convoy マ?04 (read マ204 or マユ04), 6 ships, leaving Manila on the
      3rd for 楡林 (Yulin), chart 別表第十 (Hainan southeast route) (jacar:C08030141100 p36); combinedfleet calls it
      MAYU-04 (Kuretake_t)
    sil: wakatake
    sil_basis: 'class, assumed: the plate lists Kuri, Kaki, Tsuga, Hasu, Asagao'
  - ship: CD-2
    role: escort
    to: 1944-07-03
    source: jacar:C08030141000
    page: p34
    basis: reported
    note: >-
      Kaibokan. Written 海二 after a mark P in the escort column of 1st Surface Escort Division war diary, June
      1944, chart 別表第二 (convoy escort, Malay direct route), column ヒ67: escorts written in two lines as 白鷹 倉橋 平戸
      海五 海三(十三?) 駆?(8) P 朝顔 呉竹 海二; 12 ships (船団隻数 12). combinedfleet.com has these three joining at sea on or
      about 26 June (Miri_t) or 30 June (Kurahashi_t); the mark may show ships that joined later (inferred); or,
      like the flag over (8) in the July chart's 運航指揮班 row, it may be a command or group marker. Not in the July
      (ヒ67) column; written 呉竹 朝顔 海二 as escorts of convoy マ?04 (read マ204 or マユ04), 6 ships, leaving Manila on the
      3rd for 楡林 (Yulin), chart 別表第十 (Hainan southeast route) (jacar:C08030141100 p36); combinedfleet calls it
      MAYU-04 (Kuretake_t)
    sil: kaibokan2
    sil_basis: class
  - ship: Manju Maru
    role: merchant; transport
    source: combinedfleet:Miri_t
    basis: secondary
    note: >-
      Named by combinedfleet.com (secondary; Miri_t, Sarawak_t, Shirataka_t agree). The escort chart gives the
      convoy as 12 ships but names only the two hit (jacar:C08030141000 p34)
    sil: cargo
  - ship: Nankai Maru
    role: merchant; transport
    source: combinedfleet:Miri_t
    basis: secondary
    note: >-
      Named by combinedfleet.com (secondary; Miri_t, Sarawak_t, Shirataka_t agree). The escort chart gives the
      convoy as 12 ships but names only the two hit (jacar:C08030141000 p34)
    sil: cargo
  - ship: Kinugasa Maru
    role: merchant; transport
    source: combinedfleet:Miri_t
    basis: secondary
    note: >-
      Named by combinedfleet.com (secondary; Miri_t, Sarawak_t, Shirataka_t agree). The escort chart gives the
      convoy as 12 ships but names only the two hit (jacar:C08030141000 p34)
    sil: cargo
  - ship: Asaka Maru
    role: merchant; transport
    source: combinedfleet:Miri_t
    basis: secondary
    note: >-
      Named by combinedfleet.com (secondary; Miri_t, Sarawak_t, Shirataka_t agree). The escort chart gives the
      convoy as 12 ships but names only the two hit (jacar:C08030141000 p34)
    sil: cargo
  - ship: Asahisan Maru
    role: merchant; transport
    source: combinedfleet:Miri_t
    basis: secondary
    note: >-
      Named by combinedfleet.com (secondary; Miri_t, Sarawak_t, Shirataka_t agree). The escort chart gives the
      convoy as 12 ships but names only the two hit (jacar:C08030141000 p34)
    sil: cargo
  - ship: Gokoku Maru
    role: merchant; transport
    source: combinedfleet:Miri_t
    basis: secondary
    note: >-
      Named by combinedfleet.com (secondary; Miri_t, Sarawak_t, Shirataka_t agree). The escort chart gives the
      convoy as 12 ships but names only the two hit (jacar:C08030141000 p34)
    sil: cargo
  - ship: Hakozaki Maru
    role: merchant; transport
    source: combinedfleet:Miri_t
    basis: secondary
    note: >-
      Named by combinedfleet.com (secondary; Miri_t, Sarawak_t, Shirataka_t agree). The escort chart gives the
      convoy as 12 ships but names only the two hit (jacar:C08030141000 p34)
    sil: cargo
  - ship: Otorisan Maru
    role: merchant; oiler
    source: combinedfleet:Miri_t
    basis: secondary
    note: >-
      Named by combinedfleet.com (secondary; Miri_t, Sarawak_t, Shirataka_t agree). The escort chart gives the
      convoy as 12 ships but names only the two hit (jacar:C08030141000 p34)
    sil: tanker
  - ship: Shinei Maru
    role: merchant; oiler
    source: combinedfleet:Miri_t
    basis: secondary
    note: >-
      Named by combinedfleet.com (secondary; Miri_t, Sarawak_t, Shirataka_t agree). The escort chart gives the
      convoy as 12 ships but names only the two hit (jacar:C08030141000 p34)
    sil: tanker
  - ship: Nichinan Maru No. 2
    role: merchant; oiler
    source: combinedfleet:Miri_t
    basis: secondary
    note: >-
      Named by combinedfleet.com (secondary; Miri_t, Sarawak_t, Shirataka_t agree). The escort chart gives the
      convoy as 12 ships but names only the two hit (jacar:C08030141000 p34)
    sil: tanker
  - ship: Miri Maru
    role: merchant; oiler
    to: 1944-06-30
    fate: >-
      torpedoed 1944-06-29 1515 I, 17-13N 118-22E, minor damage; reached Manila (BANG patrol 2 japanese.yml J01)
    source: jacar:C08030141000
    page: p34
    basis: reported
    note: >-
      Written みりい丸 さらわく丸 (小破) beside the torpedo mark on the ヒ67 track, which ends at (マニラ). Detached at Manila
      (combinedfleet:Miri_t)
    sil: tanker
  - ship: Sarawak Maru
    role: merchant; oiler
    to: 1944-06-30
    fate: >-
      torpedoed 1944-06-29 1515 I, 17-13N 118-22E, minor damage; reached Manila (BANG patrol 2 japanese.yml J01)
    source: jacar:C08030141000
    page: p34
    basis: reported
    note: >-
      Written みりい丸 さらわく丸 (小破) beside the torpedo mark on the ヒ67 track, which ends at (マニラ). Detached at Manila
      (combinedfleet:Miri_t)
    sil: tanker
---

Moji to Singapore by way of Manila, June–July 1944. The escort division's June chart starts the track in the
22 June column (Kurahashi joined from Sasebo that day: combinedfleet:Kurahashi_t, secondary); the sailing date of 20 June is combinedfleet.com's
(secondary). The July chart has the convoy leave Manila on the 3rd with 7 ships and reach 昭南 on the 9th.

**Cargo: not recorded** in any record read. The southbound HI convoys took oilers to Singapore to load
(inferred, not from a record of this convoy). Miri Maru's designated-ship log (jacar:C08050103600 p21–25)
ends on 10 June 1944, when the Navy took her over, so it stops before this voyage. Gokoku, Asahisan, Miri
and Sarawak Maru left the convoy at Manila (combinedfleet, secondary).
