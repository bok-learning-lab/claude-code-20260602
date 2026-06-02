# Outputs — notes

## Viewing

Open `mosaic.html` directly in any browser (double-click, or drag onto a browser
window). It is fully self-contained — no server, no internet, no libraries. The
sample data is inlined in the file, so it renders immediately.

## Exporting to PNG / JPG (the recipe's "image" output)

Pick whichever is handiest:

1. **Browser screenshot (simplest).** Open `mosaic.html`, then capture the
   visualization card:
   - macOS: `Cmd+Shift+4`, drag a box around the mosaic → saves a PNG to the
     Desktop.
   - Or use the browser's built-in "Capture full size screenshot" (Chrome/Edge
     devtools → Cmd/Ctrl+Shift+P → type "screenshot").

2. **Workshop screenshot / `replicate_image` path.** If you're in Claude Code or
   Cowork, ask Claude to screenshot the rendered page (the preview / browser
   tooling), or run it through the workshop's `replicate_image` MCP to produce a
   clean raster. Save the result next to this file as `mosaic.png` or
   `mosaic.jpg`.

3. **Headless (no clicking).** If Chrome is installed:
   ```
   "/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
     --headless --disable-gpu --screenshot=mosaic.png \
     --window-size=1000,700 \
     "file://$PWD/mosaic.html"
   ```

## Pointing at a REAL Tiles.csv

The sample rows are inlined as a JS array (`const DATA = [...]`) so the file
works with zero setup. To use real data, do **one** of these:

- **Quick:** open `mosaic.html`, replace the `DATA` array with your rows
  (`{ group, size, pct_dem }` objects), and set `TITLE`. Re-open in the browser.
- **Re-generate:** hand `prompts/01-build-mosaic.md` to Claude with your real
  `Tiles.csv` path filled into the `{{placeholders}}` and let it rebuild.

Schema reminder (see `context/CLAUDE.md`): `group` (label), `size` (integer
count), `pct_dem` (0–100). Everything — the size reference, color ramp, and grid
width — recomputes automatically from whatever rows are present.
