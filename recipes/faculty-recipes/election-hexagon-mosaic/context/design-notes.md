# Design notes — resolving the ambiguous bits

The recipe card says "the size of the hexagon is the size of the group" and
"shaded according to the % Democratic." Both phrases need a precise definition
before they become code. Here are the decisions, and why.

## 1. Size encodes AREA, not radius (honest perception)

"Bigger group → bigger hexagon" is ambiguous: bigger in *radius* or in *area*?
It matters a lot. If you map `size` linearly to the hexagon's radius, a group
that is 4× larger looks **16× larger** on screen (area grows with radius²). That
is a classic, misleading "area chart" error.

We want the **perceived area** of each hexagon to be proportional to `size`.
For a regular hexagon, area = `(3·√3 / 2) · r²`, so area ∝ r². Therefore:

```
radius ∝ sqrt(size)
```

Concretely, with a reference size `S_ref` mapped to a reference radius `R_ref`:

```
r(group) = R_ref · sqrt(size / S_ref)
```

We use the dataset's **maximum** `size` as `S_ref` so the largest hex fits the
cell, and clamp tiny groups to a small minimum radius so they stay visible.
This is the single most important correctness check: **area scaling = radius ×
sqrt(value)**, never radius × value.

## 2. Color ramp: light (less Dem) → dark (more Dem)

`pct_dem` is a 0–100 scale that maps to fill **darkness / saturation**:

- **0% Democratic → lightest** fill.
- **100% Democratic → darkest** fill.

We ramp within a single blue hue (the conventional "Democratic" color) by
interpolating **lightness**: high lightness (near-white blue) at 0%, low
lightness (deep navy) at 100%. Using one hue with a lightness gradient keeps the
encoding readable as a true light→dark sequence and prints sensibly in grayscale.

```
lightness = lerp(96%  /* 0% dem  */, 24% /* 100% dem */, pct_dem/100)
fill = hsl(222, 70%, lightness)
```

A short legend renders this exact ramp with a few labeled stops (0 / 50 / 100%)
plus a couple of size swatches, so a reader can decode both channels.

## 3. Layout: offset (brick) hex packing

Hexagons are laid out as a **pointy-top offset grid**: each row is shifted half a
column, and odd rows nudge vertically so the hexes interlock like a honeycomb.
Cells are placed on a fixed pitch (a uniform grid spacing big enough for the
largest hex); the *drawn* hex inside each cell scales by area as above. So the
**positions** form a tidy mosaic while the **sizes** vary — a cartogram-style
tile grid, not a true geographic map.

Row width (columns per row) is chosen to make a roughly square overall block for
the number of rows. The faculty member can later replace this auto-layout with a
hand-authored row/col assignment if they want a specific map-like arrangement
(the way US-state hex cartograms pin each state to a cell).

## 4. What the faculty member changes

Only `Tiles.csv` (same `group,size,pct_dem` columns). Everything above is
data-driven: the size reference, the color ramp endpoints, and the grid width
all recompute from whatever rows are present.
