# Navy: dated relationships of ships and battalions

`relations.csv` has the same columns as `../army/relations.csv` (one row a relationship and period, each with its
page): `unit`, `relation`, `other`, `other_name` (as the record types it, or in words where it types none),
`from`, `to` (`..` before a date: on or before; after: on or after; blank: not given), `basis` (`reported`,
`inferred`), `page`, `note`.

A ship or battalion had two chains at once, and both are here:

- **Operational**, `under_command`: the fleet, task force, task group and task unit the record says she was steaming
  or sailing with, or under whose operation order. These changed patrol by patrol and week by week. A submarine's
  coordinated attack group (a wolf pack) is a task group; where the report types no number, `other_name` describes it.
- **Administrative**: `part_of` a destroyer squadron or division; for a submarine, `reported_through`, the submarine
  division and squadron each patrol report was addressed via and endorsed by, from the report's date to her next
  departure (the refit that division's relief crew gave her). A submarine reported through the division at the base
  where her patrol ended, so this changes from patrol to patrol: it is not a standing assignment, and is not drawn
  as one.
- A Seabee battalion's regiment and brigade are the ones its monthly reports were routed via
  (`ncbhist-020`, the Seabee Museum's historical information file, a chronology of those reports); `attached_to`
  where the record says attached, or serving with a fleet. Its sections were often apart: the note says which.

Units: `ss-385-bang` (`../boats/ss-385-bang/`), `dd-700-haynsworth` (`../ships/dd-700-haynsworth/`), `20ncb`
(`../seabees/`).

Sources: the six war patrol reports (`rg38-74802746` to `rg38-74802934`), COMSUBPAC's war diary for October 1944
(`rg38-139761402`, `../commands/comsubpac/`), Haynsworth's war diaries (listed in `../ships/dd-700-haynsworth/README.md`),
and `ncbhist-020`. The scans were read from the cache, with Tesseract for the war diaries; numbers the OCR garbled
were read on the scan (noted where it mattered).
