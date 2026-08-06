# Chokepoint Resilience Dashboard

An interactive tool built alongside a master's thesis on maritime oil and gas
chokepoint vulnerability: *"Building Strategic Resilience in Global Oil and
Gas Supply Chains: A Multi-Hazard Vulnerability Assessment of Critical
Maritime Energy Chokepoints."*

## What it does

Select an origin (exporter) and destination (importer) country, and the tool
shows which of five maritime chokepoints the shipment would realistically
pass through, plotted on a real world map, along with a hazard profile and
literature-grounded resilience recommendations for each chokepoint on the
route.

## Status / what's real vs. illustrative

- **Real, verified data**: chokepoint transit volumes (EIA, 2026), hazard
  descriptions, and recommendations are grounded in the thesis's literature
  review (see Chapter 2).
- **Curated, not live**: country-to-chokepoint routing is a hand-built rule
  table for ~15 major countries, not a live shipping/geocoding API. See the
  `routeRules` object in `index.html`.
- **Qualitative, not scored**: hazard levels are High/Medium/Low judgements
  from the literature, not a computed numerical index.

## Files

- `index.html` — the entire app (HTML/CSS/JS + D3.js map, loaded via CDN).
  No build step, no dependencies to install.

## Running it locally

Just open `index.html` in a browser. Requires an internet connection (loads
D3.js and world map data from a CDN for the map).

## Deploying

Push this repo to GitHub, then enable **Settings → Pages → Deploy from
branch → main / root**. GitHub will serve `index.html` automatically.

## Next steps / ideas for improvement

- Expand the country list (see `countries` array in `index.html`)
- Add more nuanced routing rules (e.g. seasonal Panama Canal alternatives)
- Verify the remaining "reasonably confident but not individually
  web-verified" claims in the recommendation text (Lloyd's Joint War
  Committee listings, EU 20th sanctions package specifics, Suez Canal
  Authority tug investment) before relying on them academically
- Consider whether a static/offline-safe schematic map is preferable to the
  live D3 world map for presentation contexts without reliable internet
