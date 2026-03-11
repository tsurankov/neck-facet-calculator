# Neck Facet Calculator

A lightweight, single-page calculator for working out the facet
geometry of a guitar neck blank. All of the UI, math and drawing code
lives in `index.html`, making it easy to open locally or host on a
static site.

## Features

- Specify width and thickness at fret 1 and fret 12 directly, or derive
  them from nut/last widths, scale length and number of frets (Nut to Heel mode).
- Choose a profile exponent (`n`) from named shapes (Soft V through Thin U)
  with a fine-tune slider for precise control.
- Interpolate for an arbitrary intermediate fret.
- See primary (45°) and secondary (22.5°/67.5°) facets drawn on the
  rectangle blank and on the resulting hexagon, with all measurement
  points labeled.
- Browse a library of reference presets and load them with one click.
- Switch between mm and inches.
- Shareable URLs capture all parameters.
- Click any canvas to open an enlarged lightbox view.

## Usage

Open `index.html` in a modern desktop browser. Adjust the inputs —
results update automatically. Toggle between **Fret 1 / Fret 12** and
**Nut to Heel** modes, select profiles, or jump straight to a preset
via the **Library** tab.

Use the **Share** button to copy a link containing the current settings
(works when served via HTTP; when opened as a local file the query
string is copied instead).

## Development

The page is currently a single file; splitting the JavaScript into
modules (`math.js`, `ui.js`, …) and adding unit tests around
`computeFacets`, `fretW`, etc. would make it easier to maintain.

## Disclaimer

This project is a non-commercial hobby tool written for personal use.
Profile values and calculations are based on public specs, community
measurements and informed estimates; they may be incorrect or
incomplete. Always double-check critical dimensions before cutting
any material.

## License

The content of this repository is licensed under the
[Creative Commons Attribution-NonCommercial 4.0 International](./LICENSE)
licence. You may share and adapt it for non-commercial purposes with
attribution.