# Engineering portfolio — Fátima Urrutia

Single-page portfolio site. `index.html` holds the markup, CSS and one small script; `images/` holds the photos. No build step, no dependencies, no framework. Fonts load from Google Fonts.

## Publishing it on GitHub Pages

1. On GitHub, create a new **public** repository named exactly:

   ```
   Fats004.github.io
   ```

   That name gives you `https://Fats004.github.io` as the address. Any other repo name works too, but the URL becomes `https://Fats004.github.io/repo-name/`.

2. Upload `index.html` **and the whole `images` folder** to the root of the repository. The web interface's **Add file → Upload files** accepts a dragged folder. Or from a terminal:

   ```bash
   git init
   git add index.html images README.md
   git commit -m "Add portfolio site"
   git branch -M main
   git remote add origin https://github.com/Fats004/Fats004.github.io.git
   git push -u origin main
   ```

3. In the repository, go to **Settings → Pages**. Under *Build and deployment*, set **Source** to `Deploy from a branch`, **Branch** to `main`, folder `/ (root)`. Save.

4. Wait one to two minutes, then open the URL. Later pushes go live within a minute.

If the images don't appear, the folder name or the file capitalisation is wrong — GitHub Pages is case-sensitive where Windows is not.

## What's on the page

**Selected work** — four full project sheets: HexaPod, QUETZAL-2 ADCS, the electrodynamic tether, and the conveyor sorting cell. Each has a document code, a spec table, body text, and one or two figures.

**Capabilities** — four grouped columns.

**Earlier work** — six cards from the portfolio deck plus the Webots line-following project: sumo robot, animatronic eyes, Pong console, clock/alarm, R2-D2, vision-based line following. The clock and animatronic eyes cards link to the GitHub repos found in the deck.

## Images

| File | Used for |
| --- | --- |
| `hexapod-hardware.jpg` | HexaPod, Fig. 1.1 |
| `hexapod-cad.jpg` | HexaPod, Fig. 1.2 |
| `quetzal2-exploded.jpg` | QUETZAL-2, Fig. 2.1 |
| `conveyor-cell.jpg` | Conveyor cell, Fig. 4.1 |
| `sumobot.jpg` | Sumo robot card (PCB render) |
| `sumobot-photo.jpg` | *unused* — the assembled chassis, if you prefer it over the PCB render |
| `animatronic-eyes.jpg`, `pong.jpg`, `clock.jpg`, `r2d2.jpg` | Earlier work cards |

All photos are pre-cropped to 4:3 and resized, so what you see in the folder is what renders. To swap one, replace the file with another 4:3 image of similar size and keep the filename.

The deck also contained video clips of the R2-D2 and the clock. They aren't on the page — GitHub Pages will serve an MP4 fine, but a video on a portfolio page is worth adding only if it shows motion that a photo can't.

## Things to verify before publishing

Reconstructed from earlier conversations and the deck, worth a check against your own notes:

- **HexaPod** — the battery is written as "lithium pack"; make it specific if you want it precise.
- **Conveyor cell** — the sheet says Siemens PLC / STL / SIMATIC Manager and an industrial control panel, but the photo shows the belt and the servo diverters, not the panel. If the panel is a separate photo, add it as Fig. 4.3. If this build is actually a different conveyor than the PLC one, the sheet needs rewriting.
- **Tether** — the deployer mass range and the 2U-to-3U consequence are stated as a risk, not a conclusion.
- **QUETZAL-2** — described as Guatemala's second nanosatellite and as a subsystem you lead. Check the phrasing against how the lab describes it publicly.
- **Sumo robot** — the deck says Bluetooth to an Xbox One controller; confirm the ESP32 part number if you want it in the spec.

## Adding a project

For a full sheet, copy any `<article class="sheet">` block and edit the code, the status, the `<h3>`, the `.role` line, the spec rows and the figures. For an earlier-work entry, copy an `<article class="card">` block — it needs a 4:3 image in `images/`, a code, a title, a paragraph, and optionally the `.repo` link.

Design tokens live in the `:root` block at the top of the `<style>` tag, so palette and typeface changes happen in one place. The page is responsive to phone width, keyboard focus is visible, and animation is suppressed under `prefers-reduced-motion`.
