# HHC XO Tracker — 192nd Engineer Battalion

A mobile-first web app for tracking HHC personnel accountability and due-outs, built from the
company's existing tracker spreadsheet.

## Running it

No build step. Serve the folder over any static server and open `HHC XO Tracker.dc.html`:

```
python3 -m http.server 8000
# then visit http://localhost:8000/HHC%20XO%20Tracker.dc.html
```

Opening the file directly from disk also works in most browsers.

## What's in it

| Path | What it is |
| --- | --- |
| `HHC XO Tracker.dc.html` | The app — template + logic in one streaming component file |
| `roster-data.js` | Seed data (`window.HHC_DATA`): 85 personnel across 9 sections, 38 due-outs |
| `support.js` | Component runtime |
| `_ds/industry-…/` | Industry design system — tokens (`styles.css`) and component bundle |
| `uploads/` | The source spreadsheet the seed data was extracted from |

## Features

- **Task organization tree** — BN Command → HHC HQ → seven sections, pan and zoom, collapse all.
- **Attendance** — tap a status pill to cycle PRES / SUTA / OST / AWOL / PROF / APPT / SICK / OTHR.
- **Soldier records** — tap a name for DODID, MOS, phone, email, home of record, profile,
  clearance, weapon/serial, next of kin and notes.
- **Add / remove personnel** — per section, or delete a record company-wide.
- **Mission rosters** — create separate tabs (e.g. Annual Training) from a subset of the company,
  each with its own independent statuses.
- **Due-out tracking** — filter by Late / Open / Closed, adjust percent complete, assign an owner.

State persists to `localStorage` under the key `hhc-xo-v1`.

## Data notes

- Personal fields (DODID, phone, email, home of record, next of kin) are empty in the seed data —
  they were not present in the source spreadsheet. Fill them in the app.
- Security clearance eligibility imported where the spreadsheet's Security Clearance tab had it.
- Several due-out cells were date-corrupted in the spreadsheet export (`1/1` had become a date
  serial); those show "Not reported" at 0%.
