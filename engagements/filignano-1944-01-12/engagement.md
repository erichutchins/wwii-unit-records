---
title: 'Filignano and Selvone, 12 January 1944: the raid at 1500'
short: Filignano · 12 January 1944
theater: mediterranean
against: [de]   # the French Expeditionary Corps' attack is context on the batteries' side
participants:
  - id: battery-f
    name: Battery F, 67th CA (AA)
    of: us
    kind: army
    unit: 67ca-f
  - id: battery-g
    name: Battery G, 67th CA (AA)
    of: us
    kind: army
    unit: 67ca-g
---

Two batteries of the 2nd Battalion, 67th Coast Artillery (AA), 2.5 km apart in the hills north of Venafro, fired on the
same German raid at 1500 on 12 January 1944, the day the French Expeditionary Corps opened its attack toward Sant'Elia
and Atina on the Fifth Army's right. Battery F at Selvone logged "12 ME-109 bombing mission, 2 planes destroyed";
Battery G at Filignano, "12 FW 190's, dive bombing ... Two destroyed". Beside them, the German XIV Panzer Corps' reports
of the same day. Hand-edited; every entry cites its page in `ref`. Fields as in
`records/README.md` ("An engagement"); `of` is each actor's nationality (`us`, `fr`, `de`).

- `events.yml`: the batteries' engagements and the German reports of the day, in the records' words.
- `positions.csv`: the two batteries' stations (placed at the villages; the gun positions aren't given). The German
  reports' places are points of the January 1944 Bezugspunktkarte, decoded with `tools/bezugspunkt.py` (`basis`
  `derived`; `guides/BEZUGSPUNKTE.md`): the French attack's front from M 46 to C 11, the points lost at noon, Acquafondata
  occupied, and the Allied fighter-bombers' target M 28 (Vallerotonda).
- `claims.yml`: whether the batteries' claims are matched by a German loss (none found so far), and which unit flew.

Context, not identification: the German army reports don't report the Luftwaffe's sorties or losses, and the Luftwaffe's
own loss returns have not been seen. The batteries' stations and engagements are also in `../../army/stations.csv` and
`../../army/actions.csv` (units `67ca-f`, `67ca-g`).
