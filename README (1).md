# HHC XO Tracker

A mobile-first web app for tracking company personnel accountability, task organization,
convoy manifests, due outs and a unit calendar. Runs entirely in the browser — no server,
no accounts, no data leaves the device.

## Running it

No build step. Serve the folder over any static server and open `HHC XO Tracker.dc.html`:

```
python3 -m http.server 8000
```

Then visit http://localhost:8000/HHC%20XO%20Tracker.dc.html

## Starting out

The app starts completely blank — no personnel, no sections. Build a roster with
**+ SECTION**, then **+ ADD SOLDIER** inside each section. Nothing is seeded and no
sample data ships with the repo.

## Data and privacy

All data lives in the browser's localStorage on the device you use. It is never uploaded.

- **Export / import** (toolbar) writes a dated `.json` snapshot containing everything:
  people, sections, rosters, convoys with chalks and vehicles, due outs, the calendar,
  card colors and row order. Import replaces everything on the device.
- **Start blank on this device** clears local data so a different company can begin fresh.
  Export first if the old data is still needed.

Keep exported `.json` files off public storage — they contain full personnel records.

## Features

- **Task org** — pan/zoom org tree, sections, per-soldier status and location, strength rollup
- **Convoys** — chalks, vehicles, driver/A-driver/pax seating, OIC/NCOIC, CSV manifest export
- **Location** — accountability by location
- **Calendar** — month/week/day views, multi-day events as spanning bars, colors, notes
- **Due outs** — tasks with owners, percent complete, standing evaluation trackers

## Files

| File | Purpose |
| --- | --- |
| `HHC XO Tracker.dc.html` | The app — markup and all logic |
| `support.js` | Runtime that mounts the component |
| `_ds/industry-…/` | Design system: stylesheet, tokens, components |
