---
title: Neuburg an der Donau, 26 April 1945
short: Neuburg · 26 April 1945
theater: europe
clock: B
# the 12th Army Group's front at noon that day (records/fronts/)
fronts: [12ag-1945-04-26]
# the map's framings: the fight was 10 km across, too small for a framing on the entries' positions, padded for a sea fight
views:
  sector: {name: "The 45th Division's ground north of Neuburg, about 30 km across", box: [[10.9, 48.67], [11.3, 48.86]]}
  mission: {name: "The bombers' target, Lechfeld; JV 44's field at Riem; Neuburg, about 90 km apart", box: [[10.7, 48.05], [11.8, 48.88]]}
  fight: {name: "Bergen and Neuburg, about 17 km across", box: [[11.06, 48.665], [11.26, 48.83]]}
steps:
  s1: {view: sector, when: "April; 26 April, 1010–1015"}
  mission: {view: mission, when: "26 April: the target, and JV 44's take-off at 1130"}
  s2: {view: fight, when: "26 April, 1145–1200"}
  s3: {view: sector, when: "26 April, 1325–2143"}
participants:
  - id: 106aaa-d
    name: Battery D, 106th AAA AW Bn
    of: us
    kind: army
    unit: 106aaa-d
    basis: inferred
    note: 'the battalion fired; Battery D was defending the 189th that month (Where was Battery D?, below)'
  - id: 189fa
    name: 189th Field Artillery Bn
    of: us
    kind: army
    unit: 189fa
    note: watched from Bergen
  - id: 17bg
    name: 17th Bomb Group (M), B-26s
    of: us
    kind: air group
    sil: b26
    note: 'its 34th, 37th and 432nd Squadrons each lost a B-26 at Neuburg (Missing Air Crew Reports 14162-14164, from Dijon, 1st TACAF; the target Lechfeld)'
  - id: jv44
    name: Jagdverband 44, Me 262s
    of: de
    kind: air group
    sil: me262
    note: 'Galland''s six jets from Munich-Riem (his own account, Die Ersten und die Letzten; JV 44''s records are still to find)'
---

Six Me 262 jets of JV 44, led by Adolf Galland on his last mission, attack a formation of the 17th Bomb Group's B-26s
over the Danube at Neuburg, as the 45th Infantry Division crosses the river below. Three records that never mention
each other describe the same five minutes: the 106th AAA AW Battalion's history (its batteries fired on the jets), the
189th Field Artillery Battalion's history (it watched from Bergen, just north-west of the town), and the three Missing
Air Crew Reports. The German side is Galland's own account, written in 1953; JV 44's records are still to find.

Clocks: the Army's B time and German summer time were both UTC+2. The MACRs' times are as typed.

The aircraft's paths are drawn from `routes.yml`: the bombers' courses as their Missing Air Crew Reports type them,
the formation's way in and home as the 432nd Squadron's sketch draws it (the reading of its two lines is ours, from
the crews' statements), and the jets' lines from Riem and at 1725, inferred. The 45th Division's G-2 periodic report
for the day gives the jets' height and the second jet's course, and puts the two crashes south-east of T5026, a 1 km square of the
Army's map grid, by Bergen [[cite:ok45th-5343/p06]].

Still to find:

- The 17th Bomb Group's records for the day: its route as planned, whether it bombed Lechfeld, and a second target one
  account names, the ammunition dump at Schrobenhausen, 21 km south-south-east of Neuburg (on the courses the forms type
  there, and about five minutes' flying: it would fit the co-pilot's "five minutes before reaching the target"). The Air
  Force Historical Research Agency holds them on microfilm, none online: the group's April 1945 history with its war
  diary (IRIS 78024, reel B0082, frames 1270-1296) and its squadrons' April histories, the 34th (IRIS 43919, reel A0548),
  the 37th (IRIS 43975, reel A0549), the 95th (IRIS 44876, reel A0572) and the 432nd (IRIS 46759, reel A0614). The
  First Tactical Air Force's history (IRIS 240253) says nearly all its operations records were destroyed. The group's
  April history also has a jet attack on 24 April, a fight of its own: JV 44 attacked B-26s near Donauwörth that day and
  lost Lützow (Baker, 1996).
- The escort's combat reports: Finnegan's probable on Galland and Captain Robert Clark's claim for a second jet, in the
  50th Fighter Group's April 1945 history (IRIS 80137, reel B0144, frame 1631). They would put the P-47s on the map.
- The fourth B-26, which crash-landed (Ethell), and the six damaged: perhaps the 17th's, perhaps the 42nd Bomb Wing's
  other groups' (the 320th, and a French group).
- JV 44's records and the Luftwaffe's loss returns: which jets were hit, and whether a pilot bailed out (Ethell) or the
  jet landed (Galland).
- The 106th's three "AAA Action Report[s]" of the day, sent at 2225B to the 23d AAA Group, the 45th Division and its
  artillery [[cite:ok45th-17541/p27]]: not in the museum's collection, so the 23d AAA Group's or the division's files
  (NARA RG 407).

## The fight in the air

Galland led six jets from Munich-Riem: "Sechs Düsen-Jäger des J.V. 44 führte ich gegen einen Marauder-Verband ... In
der Gegend von Neuburg an der Donau sichtete ich den Verband" (I led six jets of JV 44 against a Marauder formation ...
I sighted it in the district of Neuburg on the Danube) [[cite:galland-1953/n385]] [[cite:galland-1953/n386]]. They met it nearly head-on, passed
over and wheeled round to attack from behind ([Ethell and Price, 1979, p. 54](https://archive.org/details/germanjetsincomb0000ethe)),
as the 37th Squadron's gunners saw No. 25 attacked, "in low from 5 o'clock rear" [[cite:rg92-91150835/p04]]. Galland's
rockets did not fire; with his cannon, "Eine Marauder der letzten Kette fliegt brennend und explodierend auseinander.
Jetzt greife ich einen weiteren Bomber der voranfliegenden Formation an. Er ist schwer getroffen" (a Marauder of the
last flight flies apart, burning and exploding; now I attack another bomber of the leading formation; it is heavily
hit) [[cite:galland-1953/n386]]. Kaplan has the first "falling through the formation and colliding with another B-26"
([Kaplan, 2007, pp. 49-50](https://archive.org/details/fighteracesofluf0000kapl)). Of the three Missing Air Crew Reports,
only No. 25's describes fire, and Baugher's serial list gives No. 25 to Galland: so his first victim was most likely
No. 25, which came down in the woods at Rohrenfels (ours, an inference).

Above the bombers, Lieutenant James Finnegan of the 50th Fighter Group was leading the P-47s' top cover: he saw two jets
come up through the formation and two bombers explode, dived on one as it banked left, and fired one three-second burst
(Kaplan). Galland, banking steeply left to see whether his second bomber would fall, was hit: knee, instrument panel,
both engines. He took his attacker for a Mustang, came down at Riem under a P-47 strafing attack and ran for a bomb
crater [[cite:galland-1953/n386]] [[cite:galland-1953/n387]]. Finnegan claimed a probable; in the 1970s a student matched it to Galland from the
escort's combat reports, and the two men met in 1979 (Kaplan). Captain Robert Clark of the 50th claimed a second jet,
its pilot bailing out (Ethell); Galland says the jet the Americans counted was Leutnant Neumann's, which landed at Riem
"voller Treffer" (full of hits) with its pilot unhurt [[cite:galland-1953/n388]].

JV 44 reported five certain kills [[cite:galland-1953/n388]]; Ethell has three B-26s down at once and a fourth so badly
damaged it crash-landed. Galland's next paragraph is the ground below: "Der Gegner hatte die Donau, von Norden
vordringend, bereits an mehreren Stellen überschritten" (the enemy, pushing from the north, had already crossed the
Danube at several places) [[cite:galland-1953/n388]]: the 45th Division's crossings that day.

## The ground under the fight

The B-26s were attacked over a river crossing. On 26 April the 45th Infantry Division crossed the Danube at Neuburg:
its command post opened at Rennertshofen at 1010, the 179th Infantry crossed by Ried and fought into the south of
Neuburg by evening, and the 157th crossed at Marxheim's blown bridge under 20 mm, mortar and artillery fire
[[cite:ok45th-10366/p22]] [[cite:ok45th-10366/p23]] [[cite:ok45th-10366/p24]] [[cite:ok45th-10366/p25]]. The 189th
Field Artillery, which Battery D defended, fired from Bergen on vehicles and guns south of the river through the
afternoon [[cite:ok45th-10366/p24]]. At 1325, an hour and a half after the jets, the 179th reported three German flak
wagons (anti-aircraft guns on carriages) in two map grid squares at the south edge of Neuburg [[cite:ok45th-10366/p23]]; a prisoner taken that evening said the
town was held by one company of the 91st Grenadier Replacement Battalion, about 100 men [[cite:ok45th-10366/p25]]. The
front on the map is the 12th Army Group's for noon that day, traced: it runs north of Bergen and Wellheim, where the
189th had been since 1015, so at this scale the sheet is behind the day, as the sheets can be (`fronts/README.md`);
the division's own reports have the crossing under way through the afternoon.

## Outcome

Three B-26s of the 17th Bomb Group were lost to enemy aircraft over Neuburg between 1145 and 1152, one each from the
34th, 432nd and 37th Squadrons, each with its Missing Air Crew Report [[cite:rg92-91150810/p02]]
[[cite:rg92-91150796/p02]] [[cite:rg92-91150835/p02]]; a published account adds a fourth that crash-landed. The 106th
AAA AW Battalion's history has its Batteries C and D engaging six Me 262s from 1145B to 1147B "without result"
[[cite:ok45th-17560/p06]]; the 189th Field Artillery Battalion's, watching from Bergen, has four jets, three bombers shot
down and "one of the German aircraft was downed" [[cite:ok45th-14862/p10]]. Galland's jet was hit by a P-47 of the
escort and crash-landed at Riem, his last mission of the war [[cite:galland-1953/n387]]; whose fire, if any, brought down
a second, no record read says.

## Sources

The folder's files, for anyone reading the records themselves:

`claims.yml` uses one more `weight`, `secondary`: a published account, not yet checked against the record it draws on.
