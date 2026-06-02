# Election hexagon mosaic

**Source:** Day-1 recipe card (`context/recipe-card.jpg`).

## Recipe (as written on the card)

- **Name:** *(left blank on the card)*
- **Ingredients (inputs):** `Tiles.csv`
- **Instructions:** Make an artifact that is a mosaic in which each tile is a
  hexagon. The **size** of each hexagon is the size of the group. Each tile is
  **shaded** according to the % Democratic — less Democratic = lighter, more
  Democratic = darker.
- **Serving (output):** An HTML, and an image in `.JPG` or `.PNG`.

## What this project is

A data-visualization artifact: a hexagonal tile-grid (cartogram-style mosaic)
driven by a CSV, where each hex encodes two variables — **group size → hex size**
and **% Democratic → fill darkness.** Outputs are an interactive/standalone HTML
and a raster export.

## Build brief (for the subagent)

Populate `context/`, `prompts/`, `outputs/`. See the spawn instructions.
We don't have the faculty member's real `Tiles.csv`, so **synthesize a small,
clearly-labeled sample `Tiles.csv`** (with a `group`/`size`/`pct_dem` schema or
similar) in `context/`, and build the sample HTML against it — with a note that
the faculty member swaps in their own file. Be precise about the size encoding
(area vs. radius) since "size of the group" is ambiguous.
