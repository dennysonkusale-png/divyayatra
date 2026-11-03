# DivyaYatra — Sacred Shrines Explorer

A single-file web app for the **12 Jyotirlingas** and the **52 Shakti Peethas** of the Indian
subcontinent: history and mythology, the nearest railway station with its distance, step-by-step
air / train / road routes, the best season to travel, where to stay, and one-tap map links.

Open `index.html` in any browser. No build step, no server, no npm install.

**Live:** https://dennysonkusale-png.github.io/divyayatra/

## What is inside

| | |
|---|---|
| Shrines | 64 (12 Jyotirlingas + 52 Shakti Peethas) |
| Coverage | 30 states & regions across 5 countries |
| Languages | English, हिन्दी, मराठी, संस्कृतम् |
| Per shrine | history, deity, relic of Sati, Bhairava, nearest railway, air/train/road routes, season, festivals, three tiers of accommodation, coordinates |
| File | one `index.html`, ~310 KB |

## Languages

The header carries a language switcher (EN / हिन्दी / मराठी / संस्कृतम्). The choice is remembered
in `localStorage`, and on a first visit the app follows the browser's language if it is one of the
four. Switching re-renders the grid and any open dialog in place.

Translated today: every interface string, all 64 shrine names, all 64 one-line descriptions, and
search works in the selected script. The long-form history and route paragraphs remain in English,
and the detail view says so in the active language.

### Adding a language

The architecture is data-driven — a new language needs no code change:

1. Add an entry to `LANGS` (`{ code, native, english }`).
2. Add `L10N[code] = { ui: {...}, shrines: { <id>: { name, short } } }` with the same keys as
   `UI_EN` (English source of truth) and the same shrine ids.
3. Missing keys fall back to English automatically, so a partial translation is safe to ship.

## Features

- **Search** across shrine name, town, state, country, deity, relic and Bhairava — in any script
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
- `UI_EN` / `L10N` — interface strings and per-language shrine names and summaries

## Credits

Photographs: Wikimedia Commons contributors. Map links: Google, Apple and OpenStreetMap.
Built as a static, dependency-light page using Tailwind CSS (CDN), FontAwesome (CDN) and
vanilla JavaScript.

Licensed under the MIT License.
