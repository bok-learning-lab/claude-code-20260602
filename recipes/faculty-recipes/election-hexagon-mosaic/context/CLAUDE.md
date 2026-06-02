# Project memory — Election hexagon mosaic

## What this is

A data-visualization artifact: a **hexagonal tile mosaic** (cartogram-style)
driven by a CSV. Each hexagon is one group. Two variables are encoded at once:

- **Group size → hex SIZE** (encoded as AREA, not radius — see `design-notes.md`).
- **% Democratic → fill DARKNESS** (less Democratic = lighter, more Democratic = darker).

Outputs: a self-contained HTML visualization and a raster image (PNG/JPG).

## Folder layout

```
election-hexagon-mosaic/
├── README.md            ← the recipe brief (from the Day-1 recipe card)
├── context/
│   ├── CLAUDE.md         ← this file (project memory)
│   ├── recipe-card.jpg   ← the handwritten source recipe
│   ├── Tiles.csv         ← SAMPLE data (synthetic; swap in your own)
│   └── design-notes.md   ← the ambiguous decisions, resolved
├── prompts/
│   └── 01-build-mosaic.md ← reusable prompt template to (re)build the mosaic
└── outputs/
    ├── mosaic.html        ← the working, self-contained visualization
    └── NOTES.md           ← how to export to PNG/JPG + point at real data
```

## Data schema (`Tiles.csv`)

| column    | type            | meaning                                      |
|-----------|-----------------|----------------------------------------------|
| `group`   | string (label)  | the group's name (precinct / district / etc.) |
| `size`    | integer ≥ 0     | the group's size (e.g. number of voters)      |
| `pct_dem` | number 0–100    | percent Democratic (0 = none, 100 = all Dem)  |

Header row required. One row per hexagon.

## IMPORTANT — this is sample data

`context/Tiles.csv` is a **synthetic, clearly-labeled sample** with invented
precinct names. We do **not** have the faculty member's real dataset. The
faculty member swaps in their own `Tiles.csv` (same three columns) and rebuilds.
See `outputs/NOTES.md` for how to point the HTML at a real file.
