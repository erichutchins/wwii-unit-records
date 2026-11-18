# Air: raids, airfields and aircraft

The other side of a unit's war in the air, kept apart from any one unit's records. Every row cites its page.

- `raids.csv`: each raid on a target the family's units defended, as the raiding side's own record gives it, one row a
  raid: `date` and `night` (`yes` where the record says night: "the night of 24 June" is the night of 24/25; blank
  where it doesn't say), `target`,
  `side` (`de`, `it`), `force` and `result` and `losses` as the record words them, `units` and `from_field` where a
  source names them (most records don't), `basis`, `page`, `note`. So far: Bizerte, June-September 1943, from the
  German Naval Staff's war diary (`skl:`), which gives numbers and results but rarely units or airfields.
- `airfields.csv`: a unit at a field over an interval: `field` (a key, repeated for each unit there), `name`, `lon`,
  `lat`, `side`, `units`, `from`, `to`, `role`, `basis`, `page`, `note`. Positions are the airfield's, not a
  dispersal's; where a source names a complex of fields and not the one used, the note says which mark is assumed.
- `aircraft.yml`: each type as the Allies' recognition manuals described it at the time (FM 30-30, April 1943; the
  Army-Navy Journal of Recognition), keyed as `../silhouettes/silhouettes.yml`.

A raid's units and a unit's airfield are often from secondary sources so far (`basis: secondary`, `wikipedia:`, whose
articles cite de Zeng et al. and the squadrons' record books): what to read to replace them is in each note.
Fields may also be the two ends of an engagement's mission flown over the units: Dijon (the 17th Bomb Group's B-26s,
as its Missing Air Crew Reports type it) and Munich-Riem (JV 44's Me 262s) for Neuburg, 26 April 1945
(`engagements/neuburg-1945-04-26`), each dated to the day its record gives.

Which airfield a given raid flew from is a lead unless a record says so; a book or page that draws a raid's direction
draws it from a field as illustration, and says so.
