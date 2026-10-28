# Roads

The roads of 1942 as the OSS drew them, at about 1:3,000,000: for context, not navigation.

- `oss967-primary.geojson` (generated): the primary roads ("Primary Roads", the heavy line in the
  legend) of OSS Map No. 967, *Algeria and Tunisia: Principal Highways and Landing Places*,
  22 August 1942 (SOURCES.yml `oss-967`), as LineStrings with properties `source` ("oss-967"),
  `class` ("primary") and `fit_km` (the map fit's leave-one-out rms error, in km).
- `oss967-gcps.csv` (hand-checked): the 33 towns the scan is fitted to. `x`, `y`: the centre of the
  town's ring on the full-size scan (11249 x 6589), `read` says whether the ring was found by the
  tool or by eye; `lat`, `lon`: the town today, from OSM Nominatim (`query`), the same as
  `army/places.csv` where that has it.

How it was made (`tools/trace_roads.py`, which says how to rerun it): the map's printed 1° ticks
don't agree with its drawing (fitted to them, the towns land 11–36 km off), so the scan is fitted to
its towns with a 2nd-order polynomial: 3.2 km rms, 3.9 km leave-one-out, worst 12 km (Mascara).
Primary roads are about twice as wide as secondary roads, the coast and the lettering; a
morphological opening keeps them, and they are thinned to centre lines. A road's position is good
to a few km (the fit plus the line's own width, about 1.5 km at this scale); the map is a sketch
of the network, and a road that bends inside a few km is drawn smooth.

The road moves in `army/routes.csv` whose note cites OSS Map 967 follow these roads (secondary
roads where no primary road joins the towns): the reports give only the towns and the miles, so
those routes are assumed, and each note compares the traced length with the report's.
