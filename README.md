# Growing Love 🌺

A self-contained, responsive relationship garden. Each calendar day since the configured start date adds one deterministic lily. No framework, server, database, external fonts, or runtime network requests are required.

## Setup

1. Open `index.html`.
2. Find the `GROWING LOVE CONFIG` block near the start of the script.
3. Set `relationshipStartDate` to the real first day together in `YYYY-MM-DD` format. The start date counts as Day 1.
4. Optionally edit `message`, `showElapsedClock`, `showStartDate`, the palette, species weights, rendering cap, and motion settings.
5. Open `index.html` in a browser, or enable GitHub Pages in **Settings → Pages → Deploy from a branch**, choosing the branch and `/(root)`. GitHub Pages publishes the root `index.html`.

## Configuration notes

- `relationshipStartDate`: one obvious source of truth for the relationship day count.
- `palette`: core atmospheric colors (the illustration's individual sky/flower colors are also defined in the rendering code).
- `species`: flower species, colors, and relative probability weights. Weights are relative, not percentages.
- `distribution`: deterministic meadow depth and maximum rendered flower count.
- `motion`: pointer parallax and the one-time new-day glow.
- `showElapsedClock`: optionally show a live elapsed clock.

The day number is calculated from local calendar dates converted to UTC date-only values, avoiding daylight-saving transitions. Flowers use day-based deterministic seeds, so their positions and species stay stable after reloads. The canvas limits rendering work on older devices; the exact day count remains correct even if the render cap is reached. Reduced-motion preferences disable animation and parallax.

## Verify

Use a valid start date in the past to verify the counter. For a start date equal to today, it displays Day 1. Tomorrow it displays Day 2. Invalid dates and future start dates are reported in the counter rather than silently showing a wrong count.
