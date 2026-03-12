# Neck Facet Calculator

A lightweight, single‑page calculator for working out the facet
geometry of a guitar neck blank.  All of the UI, math and drawing code
lives in `index.html`, making it easy to open locally or host on a
static site.

## Features

* Specify width and thickness at fret 1 and fret 12 (or derive them from
  nut/last widths, scale length and number of frets).
* Choose a profile exponent (`n`) from a handful of common shapes.
* Interpolate for an arbitrary intermediate fret.
* See primary (45°) and secondary (22.5°/67.5°) facets drawn on a
  rectangle and on the resulting hexagon.
* Browse a library of manufacturer presets and load them with one click.
* Shareable URLs capture all parameters.
* Lightbox for enlarged canvas views.

## Usage

Open `index.html` in a modern desktop browser.  Adjust the inputs and
press **Calculate**.  Toggle between “Direct” and “From Blank” modes,
select profiles, or jump straight to a preset via the **Library** tab.

Use the **Share** button to copy a link containing the current settings
(works when served via HTTP; otherwise the query string is copied).

## Development

The page is currently a single file; splitting the JavaScript into
modules (`math.js`, `ui.js`, …) and adding unit tests around
`computeFacets`, `fretW`, etc. would make it easier to maintain.  Feel
free to restructure as you like.

## Disclaimer

This project is a non‑commercial hobby/tool written for personal use.
Profile values and calculations are based on public specs, measurements
and informed guesses; they may be incorrect or incomplete.  Always
double‑check critical dimensions before cutting any material.

## License

The content of this repository is licensed under the
[Creative Commons Attribution‑NonCommercial 4.0 International](./LICENSE)
licence.  You may share and adapt it for non‑commercial purposes with
attribution.
