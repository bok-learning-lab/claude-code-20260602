# Project memory — FAS structure cartoon (Chem 27)

## What this is
A figure-authoring task for a **Chem 27** lecture ("Assembly Line Enzymology:
Fatty Acid Biosynthesis I", Lecture 13). The faculty member wants to **replace an
existing fatty-acid synthase (FAS) cartoon** with a new one that shows **ALL
catalytic domains** of the enzyme, **every domain labeled**, matching the
look/layout of the original so it drops into existing slides.

**The key requirement:** the new cartoon must **include the termination domain
(TE, thioesterase)** — the domain the *current* cartoon omits. Do not ship a
version that is missing TE.

## Folder layout
- `context/`
  - `recipe-card.jpg` — the handwritten Day-1 recipe card (the brief).
  - `L13-fatty-acid-synthesis-lecture.pdf` — the source lecture (domain
    vocabulary, colors, and assembly-line framing). **Authoritative for naming.**
  - `CLAUDE.md` — this file.
  - `fas-domains.md` — clean reference list of the FAS domains + functions + order.
- `prompts/`
  - `01-generate-cartoon.md` — reusable prompt template for (re)generating the
    cartoon as SVG/HTML, with {{placeholders}}.
- `outputs/`
  - `fas-cartoon.html` — self-contained HTML/inline-SVG cartoon (the shippable
    "moderate-res image"). Includes all domains incl. TE, with title + legend.
  - `NOTES.md` — what to verify scientifically + how to export to PNG.

## Domain naming (match the lecture)
Use the lecture's vocabulary. The lecture's **linear domain bar (slide 11)** reads:
**KS – MAT – DH – ER – KR – ACP – TE**. The lecture's mechanism/block slides label
the transferase domain **AT (Acyl Transferase)**; the structural figure labels it
**MAT (malonyl/acetyl transferase)**. We use **AT** as the primary label and note
**MAT** as the equivalent term. See `fas-domains.md` for the full list and the
elongation→tailoring→termination grouping.

## Export note
The deliverable is a **moderate-resolution PNG for PowerPoint**. The cartoon is
authored as HTML+SVG (most reproducible in-repo). The faculty member opens
`outputs/fas-cartoon.html` in a browser and **screenshots / exports it to PNG**,
then pastes that into the slide deck. (SVG is crisp at any zoom; a 2x screenshot
gives a clean moderate-res raster.)
