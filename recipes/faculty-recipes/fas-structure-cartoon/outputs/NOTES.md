# Output notes — fas-cartoon.html

## What this is
A self-contained HTML + inline-SVG cartoon of the seven FAS catalytic domains, in
the lecture's biosynthetic order (**KS – AT/MAT – DH – ER – KR – ACP – TE**), with a
title, per-domain labels, phase brackets (elongation+tailoring vs. termination), and
a legend of one-line functions. It is the in-repo stand-in for the "moderate-res
image" the recipe card asks for.

## How to export to PNG (for PowerPoint)
1. Open `fas-cartoon.html` in any browser (double-click it).
2. Zoom to ~150–200% so the figure card fills the window (crisper raster).
3. Screenshot just the white figure card:
   - macOS: **Cmd-Shift-4**, drag over the card.
   - Or in browser DevTools: right-click the `.figure` element → "Capture node screenshot".
4. Paste the PNG into the slide. SVG is resolution-independent, so a 2x screenshot
   gives clean moderate resolution; re-export larger if you need more.

## What to verify scientifically before using in class
- **TE is present and labeled as termination** — this is the whole point of the
  redo (the old cartoon omitted it). Confirmed present here.
- **Domain naming matches the lecture.** The lecture uses **AT (acyl transferase)**
  on its mechanism slides and **MAT (malonyl/acetyl transferase)** on the structural
  figure; this cartoon labels it **AT (MAT)**. Pick whichever your slide deck uses
  and make it consistent.
- **Domain order.** This follows the lecture's slide-11 linear bar
  (KS–MAT–DH–ER–KR–ACP–TE). If you instead want to mirror the *original* cartoon's
  layout exactly, adjust the block x-positions in the SVG (or re-run
  `../prompts/01-generate-cartoon.md` with a layout note).
- **Functions in the legend** are paraphrased from Lecture 13; double-check wording
  against `../context/fas-domains.md` and the slides (esp. NADPH use by KR/ER, the
  DH elimination, and that TE releases palmitate, C16).
- **Color** is an instructional choice, not a fixed convention — recolor to match
  your deck if desired (CSS variables at the top of the file).
