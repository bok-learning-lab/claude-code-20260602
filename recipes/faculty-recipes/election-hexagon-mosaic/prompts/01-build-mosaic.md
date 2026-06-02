# Prompt template — build the hexagon mosaic

A reusable prompt for (re)building the visualization. Fill in the
`{{placeholders}}` and paste it to Claude (Chat, Cowork, or Code). It is written
to be safe to run again whenever the data changes.

---

Build a **self-contained HTML hexagon mosaic** (cartogram-style tile grid) from a
CSV, then export it to a raster image.

**Data:** `{{CSV_PATH}}` — columns include a label, a size column
`{{SIZE_COLUMN}}` (integer count), and a color column `{{COLOR_COLUMN}}` (a
0–100 percentage). One row = one hexagon.

**Title:** `{{TITLE}}`

**Encodings (be precise):**

1. **Size → hex AREA, not radius.** A regular hexagon's area ∝ radius², so map
   `radius = R_ref * sqrt(value / max_value)`. Do NOT map size linearly to
   radius — that exaggerates large groups. Clamp tiny groups to a small minimum
   radius so they stay visible.
2. **`{{COLOR_COLUMN}}` → fill darkness.** Light = low value, dark = high value.
   Ramp lightness within a single hue (e.g. blue `hsl(222, 70%, L)`), with
   L ≈ 96% at 0 and L ≈ 24% at 100.

**Requirements:**

- ONE HTML file, **no external libraries or CDNs** — vanilla JS + inline SVG (or
  canvas). It must render correctly when opened directly from disk (`file://`),
  so **inline the CSV rows as a JS array** (don't fetch over the network).
- Lay hexagons out in an **offset (honeycomb) grid**: pointy-top hexes, odd rows
  shifted half a column and interlocked vertically. Positions form a tidy
  mosaic; only the drawn hex size varies.
- Render the **title** and a **legend**: a labeled color ramp (0 / 50 / 100%) and
  a couple of size swatches. Show each group's label on hover (tooltip).
- Verify the geometry: regular hexagon vertices at 60° steps, and confirm the
  area (not radius) scales with the value.

**Then export a raster:** produce a PNG (or JPG) of the rendered mosaic — open
the HTML in a browser and screenshot it, or use the workshop's screenshot /
`replicate_image` path. Save it next to the HTML.

When done, tell me the file paths and confirm the largest hex corresponds to the
largest `{{SIZE_COLUMN}}` value and the darkest hex to the highest
`{{COLOR_COLUMN}}` value.
