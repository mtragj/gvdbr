# 2026 Rides — Follow-up TODO

Tracking the open items after importing the 2026 rides from the SignUpGenius dump
(`2026-rides.txt`) into `_posts/rides/`. The structured data (dates, times,
locations, distances, trail lists) is in place and the site builds clean; the
items below still need human input.

## 1. GJ Desert is a brand-new riding region
The site only has region pages/tiles for **North Desert**, **Rabbit Valley**, and
**Bangs Canyon**. The two GJ Desert rides are tagged with a `gj_desert` category,
so they appear on the **difficulty** listing pages and have working detail pages,
but there is **no region landing page** — they are not reachable from the
"Riding Regions" tiles on `/rides/`.

- [ ] Decide: add a dedicated GJ Desert region page, or fold these rides into an existing region.
- [ ] If adding a region, mirror the existing pattern:
  - `_layouts/rides_gj_desert.html`
  - `_includes/_rides_gj_desert.html` + `_includes/_sidebar_rides_gj_desert.html`
  - region tile + "Explore Region" link in `rides/index.html`
  - region images under `images/ride_areas/`

## 2. GJ Desert rides have no map / location link
The dump only provided the location name ("27-1/4 Road MX Track"), no coordinates,
so `directions:` was left blank on both GJ rides. The map embed is correctly
omitted, but the sidebar "Where" line renders as an empty `<a href="">` link.

- [ ] Add a Google Maps URL to `directions:` on:
  - `2026-10-17-trail-ride-gj-desert-carpenter.md`
  - `2026-10-16-trail-ride-gj-desert-skinny-ridge-tour.md`
- [ ] Use a URL in the `/@lat,lng` or `/search/lat,lng` format so the sidebar map embed renders (a plain text search URL will NOT parse to coords).

## 3. Skinny Ridge Tour is Friday-only
The sidebar template (`_includes/_sidebar_ride.html`) only renders `Sat` and `Sun`.
For the Friday tour, the time was placed in the `notes:` field
("Friday Oct 16th, 2026, 3:00–5:00 pm") with Sat/Sun showing N/A. It also had no
difficulty in the dump, so it was set to `Tour (All Levels)` with no difficulty
category — meaning it currently only surfaces via the (not-yet-existing) GJ region.

- [ ] Decide whether to add a proper `fri:` field to the ride sidebar template, or keep the notes-field workaround.
- [ ] Confirm difficulty/category handling for this ride so it's discoverable.

## 4. Leaders are all `TBD`
The dump contained no leader names. Every updated and new ride has `leader: TBD`.

- [ ] Fill in ride leaders once assigned.

## 5. Reused 2025 body prose needs a review pass
For matched rides, the 2025 post body, map links, and terrain notes were retained
and only the structured fields were updated. Some prose still references the old
staging point, mileage, or route. Known examples:

- [ ] **Bangs Canyon – Intermediate, Windmill Loop**: body still describes the 2025 Third-Flats 24-mi route, not the new 22-mi Windmill loop from Bangs Canyon Trailhead.
- [ ] **Bangs Canyon – Advanced**: now starts at Third Flats Trailhead (was Bangs Canyon Trailhead in the 2025 body prose).
- [ ] Review every matched ride's body for stale distance/staging/route details.

## 6. New-ride descriptions are first drafts
The 5 brand-new rides (Horse Mesa, Sarlaac Skywalker, Kokopelli 4x4, Knolls
Overlook, GJ Carpenter, Skinny Ridge Tour) have brief bodies written from the
dump's short trail list. Verify accuracy, especially:

- [ ] Whether the Kokopelli 4x4 and Knolls Overlook routes actually cross into Utah (the "Ride Utah" note was added by precedent from 2025 Rabbit Valley rides).
- [ ] Photos/captions — new rides reuse existing images; swap in ride-specific images if available.

## 7. Source files
- [ ] `2026-rides.txt` (raw dump) and this TODO can be removed once the above is resolved.
