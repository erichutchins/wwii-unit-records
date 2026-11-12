---
convoy: No. 3905
name_ja: ""
plain: "a small Yokosuka–Haha-jima convoy on the Bonins run, its route and ships from a secondary source"   # what it was, in a line, ours
from: Yokosuka (secondary)
to: Haha-jima (secondary)
via: [Tateyama (secondary)]
sailed: 1944-09-06 (secondary)
arrived: ""
size: ""
cargo: ""
attacked_by: [ss-385-bang/3]
sources:
  - combinedfleet:yasojima_t        # secondary: route, escorts Yasojima, Hachijo, CD-4, CD-12; Shoryu and Tokiwasan Maru
  - rg38-74802831/p10              # BANG's contact at 1305 K on 9 Sept: 1 AO, 2 AK, 2 escorts
  - jacar:C08030363600 p3           # Yokosuka Guard Squadron, Sept 1944: 昌隆丸 常盤山丸 sunk 9th 1520, 265° 10 nm from Sumisu-jima
  - jacar:C08030363600 p5           # the same diary's escort grid (read with low confidence)
route: [yokosuka, tateyama, w-izu, w-bonin, haha-jima]   # through reference/lanes/lanes.yml; assumed waypoints are drawn dotted
ships:
  - ship: Shoryu Maru
    role: merchant
    to: 1944-09-09
    fate: sunk 1944-09-09 1520 I (BANG patrol 3 J03)
    source: jacar:C08030363600
    page: p3
    basis: inferred
    note: >-
      昌隆丸. The diary names her sunk with 常盤山丸 but not the convoy; the convoy is combinedfleet's (yasojima_t,
      secondary)
    sil: type-d-mod
    sil_basis: 'class, assumed: matched by tonnage, DANFS''s 1,916-ton Shoryu Maru (BANG patrol 3 claims.yml) against SHORYU MARU 1,916 GT in the plate''s list for Types D and D (Modified) (ONI 208-J Supplement 3, p. 8); the drawing is D (Modified)'
  - ship: Tokiwasan Maru
    role: merchant
    to: 1944-09-09
    fate: sunk 1944-09-09 1520 I (BANG patrol 3 J03)
    source: jacar:C08030363600
    page: p3
    basis: inferred
    note: >-
      常盤山丸. The diary names her sunk with 昌隆丸 but not the convoy; the convoy is combinedfleet's (yasojima_t,
      secondary)
    sil: tokiwasan-maru
    sil_basis: own
  - ship: Yasojima
    role: escort
    source: combinedfleet:yasojima_t
    basis: secondary
    note: >-
      Named as escort by combinedfleet. The Yokosuka Guard Squadron's escort grid (jacar:C08030363600 p5) writes
      父島 (Chichi-jima) across about days 8–11 in her row, which fits; read with low confidence (skewed scan)
    sil: escort
  - ship: Hachijo
    role: escort
    source: combinedfleet:yasojima_t
    basis: secondary
    note: Named as escort by combinedfleet; not found yet in the September grid
    sil: shimushu
    sil_basis: class
  - ship: CD-4
    role: escort
    source: combinedfleet:yasojima_t
    basis: secondary
    note: >-
      Named as escort by combinedfleet. The September grid (p5) has her at Yokosuka to about day 8 and Tateyama
      about days 9–10, which does not fit; read with low confidence
    sil: kaibokan2
    sil_basis: class
  - ship: CD-12
    role: escort
    source: combinedfleet:yasojima_t
    basis: secondary
    note: >-
      Named as escort by combinedfleet. The September grid (p5) has her at Yokosuka early in the month, an arrow
      leaving about day 7–8, and Chichi-jima about days 12–13; read with low confidence
    sil: kaibokan2
    sil_basis: class
---

The Japanese record of the loss is the Yokosuka Guard Squadron's September diary (p3): 昌隆丸 (Shoryu Maru) and
常盤山丸 (Tokiwasan Maru) torpedoed and sunk at 1520 on the 9th, four minutes after BANG's first salvo (1616 K =
1516 I). It gives the place as 265° 10 nm from Sumisu-jima, which is about 188 nm north-east of BANG's attack
position; BANG's position agrees with the postwar one combinedfleet gives (28-58N 137-45E). The diary doesn't
name the convoy.

The route and escorts are combinedfleet.com's (secondary). It has the convoy leave Yokosuka on 6 September for
Haha-jima, reach Tateyama on the 7th, and leave Tateyama "at 1520" on the 9th, then be attacked "at about 1600"
at 28-58N 137-45E. That can't be right: Tateyama is about 360 nm north of that position, and 1520 on the 9th is
the diary's time of the sinking. The Tateyama sailing was probably the 7th or 8th (inferred, to check).
The escort grid (p5) fits Yasojima (父島 across about days 8–11) but has CD-4 at Yokosuka and Tateyama until
about the 10th; all read with low confidence from a skewed scan.

**Cargo: not recorded.** BANG saw one oiler (AO) and two freighters.
