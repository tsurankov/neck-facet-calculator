# Neck Facet Calculator — Guitar Neck Carving Tool

A free, lightweight, single-page luthier calculator for working out the
facet geometry of a guitar neck blank. Supports primary (45°) and
secondary (22.5° / 67.5°) facets with step-by-step markup measurements.
All of the UI, math and drawing code lives in `index.html`, making it
easy to open locally or host on a static site.

## What is a neck facet?

When carving a guitar neck by hand, luthiers typically cut a series of
flat facets into the rectangular blank before rounding everything to the
final profile. This calculator computes exactly where to mark those cuts —
saving time and reducing the risk of removing too much wood.

## Features

- Specify width and thickness at fret 1 and fret 12 directly, or derive
  them from nut/last widths, scale length and number of frets (Nut to Heel mode).
- Choose a neck profile exponent (`n`) from named shapes — Soft V, Vintage C,
  C Shape, Modern C, Thin C, D Shape, Sorcerer, Sorcerer II, Thin U — with a
  fine-tune slider for precise control.
- Interpolate dimensions for any intermediate fret.
- Visualize primary (45°) and secondary (22.5°/67.5°) facets drawn on the
  rectangle blank and on the resulting hexagon, with all measurement points labeled.
- Browse a library of reference neck profiles and load them with one click.
- Switch between millimetres and inches.
- Shareable URLs capture all parameters.
- Click any canvas to open an enlarged lightbox view.

## Usage

Open `index.html` in a modern desktop browser. Adjust the inputs —
results update automatically. Toggle between **Fret 1 / Fret 12** and
**Nut to Heel** modes, select a neck profile, or jump straight to a
reference preset via the **Library** tab.

Use the **Share** button to copy a link containing the current settings
(works when served via HTTP; when opened as a local file the query
string is copied instead).

## Who is this for?

Guitarists and bass players building their own instruments, luthiers
looking for a quick reference, and anyone learning hand-carving techniques
for guitar neck shaping.

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