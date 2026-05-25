# mishna-berurah

Simple single-file web app for learning **Shulchan Arukh, Orach Chayim** with **Mishnah Berurah** side-by-side.

## What it does

- Loads a selected **siman** from Shulchan Arukh, Orach Chayim.
- Shows each Shulchan Arukh **seif** on the left pane.
- Shows the related Mishnah Berurah text on the right pane.

## Mishnah Berurah mapping behavior

For each selected Shulchan Arukh seif, the app queries Sefaria links:

- Endpoint: `https://www.sefaria.org/api/links/Shulchan%20Arukh%2C%20Orach%20Chayim.{siman}.{seif}`
- Filters links to `Mishnah Berurah`
- Collects all linked Mishnah Berurah seifim (including ranges)
- Renders all linked seifim in the right pane

Example:

- **Shulchan Arukh, Orach Chayim 1:1** can map to **Mishnah Berurah 1:1-8**
- The app displays all of those Mishnah Berurah seifim together.

If links are unavailable for a seif, the app falls back to the same-number Mishnah Berurah seif when present.
