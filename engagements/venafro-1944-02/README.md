# Shelled on the Winter Line: the 67th CA (AA)'s batteries by Venafro and Acquafondata, February 1944

Two batteries of the 2nd Battalion, 67th Coast Artillery (AA) (from 20 March 1944 the 894th AAA AW Bn), giving
antiaircraft protection to the field artillery in the hills between Venafro and Cassino, and what the German XIV
Panzer Corps reported about its fire on the same days. Battery E was at Lucenteforte, by Venafro, with half its guns
detached near Sant'Elia from 10 to 23 Feb; it had men wounded on 14 and 16 Feb. Battery H moved up near Acquafondata on
12 Feb; its gun positions were shelled at 1500 on 21 Feb. Hand-edited; every row cites its page in `ref`. Columns as in
[`haynsworth-1945-04-06`](../haynsworth-1945-04-06/README.md), with `side` one of `allied`, `axis`, `geo`.

- `timeline.csv`: the batteries' moves and casualties, and the German reports of the same days, in the record's words.
  `placed` = `seq` when the record gives no time.
- `positions.csv`: the batteries' stations as the forms name them (placed at the place name: the gun positions aren't
  given) and the German reports' places. The German reports give places as points of their reference-point map, the
  Bezugspunktkarte (`XXIII 117`); these are decoded with `tools/bezugspunkt.py` (`guides/BEZUGSPUNKTE.md`), `basis`
  `derived`.
- `claims.csv`: the questions the records leave open (whether the fire on Vallerotonda was what hit Battery H; where
  Battery E's men were hit).

Context, not identification: no German report of these days names Venafro, Lucenteforte or Acquafondata, or an
antiaircraft battery, so a German entry is "the same day and nearly the same place" at most. The batteries' stations
are in `../../army/stations.csv` (units `67ca-e`, `67ca-h`), their casualties in `../../army/actions.csv`. The German
frames: NARA T-314 roll 544 (XIV Panzer Corps' Taktische Meldungen, Feb 1944) and T-312 roll 90 (the Bezugspunktkarte).
