---
name: journey-content-data
description: Add or edit travel-journal data, including titles, stops, records, photo metadata, catalog entries, and sourced route geometry. Use for journey content and route provenance changes; exclude theme styling and map-camera behavior.
---

# Journey Content Data

Trace the active catalog, journey data, and route loader before editing. Reuse the current schema and shared page renderer. Add a destination through data rather than a copied page.

## Content and identity

- Keep the displayed title separate from the geographic route label and stable URL slug. For a rename, check catalog cards, page headings, browser/share titles, accessibility labels, and translations. Preserve place names and route geometry unless the request includes them.
- Use supplied records for dates, arrival times, weather, first-person stories, mileage, and photo details. Leave unknown fields empty or explicitly awaiting content. A route outline does not establish that the trip happened.
- Preserve stop order and section identifiers. If the site supports sections between stops, reuse its existing configuration when showing or hiding them.
- Supply alt text and image dimensions through the existing photo component. Do not invent location, time, equipment, or ownership information.

## Route provenance

Distinguish planned road geometry from a recorded GPS track. Keep source, coordinate system, acquisition date when known, and any transformation notes. Coordinates and distances must come from supplied material or an identified source.

Verify that waypoints correspond to stops in order and legs join adjacent stops. For a schema with one leg per pair, waypoint count equals stop count and leg count equals stop count minus one. Keep uncertain connections distinguishable from verified travel; do not turn uncertain edges into a solid completed route.

## Zero-4 / Mountain Story adapter

Use this adapter only when these files exist. Journey entries are in `mountain-story/dist/journeys.js`; content and routes are in `dist/journeys/<slug>.json` and `dist/routes/<slug>.json`. The homepage has a second catalog at `kuangye-home/dist/journeys.js`. Check both catalogs and the active translation dictionaries for public naming changes.

`mountain-story/scripts/sync-home.cjs` copies catalog and theme files. Inspect both sides before using it so a content change does not overwrite unrelated homepage work. Legacy `trip-content.js` and `driving-route.js` are migration references; confirm the active loading chain before choosing edit targets.

Run relevant existing data/geometry tests and open the changed journey, including a direct chapter link. Report missing source material clearly. Publishing, GitHub upload, and access changes remain separate actions requiring the user's instruction.
