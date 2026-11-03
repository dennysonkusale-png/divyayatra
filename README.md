# DivyaYatra — Sacred Shrines Explorer

A single-file web app for the **12 Jyotirlingas** and the **52 Shakti Peethas** of the Indian
subcontinent: history and mythology, the nearest railway station with its distance, step-by-step
air / train / road routes, the best season to travel, where to stay, and one-tap map links.

Open `index.html` in any browser. No build step, no server, no npm install.

## What is inside

| | |
|---|---|
| Shrines | 64 (12 Jyotirlingas + 52 Shakti Peethas) |
| Coverage | 30 states & regions across 5 countries |
| Per shrine | history, deity, relic of Sati, Bhairava, nearest railway, air/train/road routes, season, festivals, three tiers of accommodation, coordinates |
| File | one `index.html`, ~211 KB |

## Features

- **Search** across shrine name, town, state, country, deity, relic and Bhairava
- **Filter tabs** — All 64 / 12 Jyotirlingas / 52 Shakti Peethas, with live counts
- **Detail modal** with an embedded OpenStreetMap panel, coordinates and a copy button
- **Map hand-off** to Google Maps, Apple Maps and OpenStreetMap at exact coordinates
- **Accommodation panel** — trust guest house, dharamshala and hotel tiers, with live search links
- **Dark / light theme** with localStorage memory, respecting the OS preference on first visit
- Responsive from 360 px up, keyboard accessible (`Esc` closes, `/` focuses search), lazy-loaded images

## Data notes

- Coordinates come from Wikipedia geodata. Most point at the temple itself; a few shrines that are
  not separately geotagged sit at town or valley level.
- The 52 Peethas follow the widely circulated Pithanirnaya lists, consolidated to one entry per
  site. Traditions count 51, 52, 64 or even 108, and eight of these lie outside present-day India.
- Railway distances are approximate road distances from station to temple gate.
- Photographs are served from Wikimedia Commons; where no free photograph of a shrine exists, a
  designed tile stands in.

## Editing

Everything lives in `index.html`:

- `SHRINES` — the dataset (one object per shrine)
- `IMG` — image URLs, one line each
- `COORDS` — `[latitude, longitude]` per shrine; every map link reads from here
- `PITHA_META` — relic, Bhairava and country for each Peetha

## Credits

Photographs: Wikimedia Commons contributors. Map links: Google, Apple and OpenStreetMap.
Built as a static, dependency-light page using Tailwind CSS (CDN), FontAwesome (CDN) and
vanilla JavaScript.

Licensed under the MIT License.
