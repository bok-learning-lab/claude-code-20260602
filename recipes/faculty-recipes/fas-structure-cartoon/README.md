# Fatty-acid-synthase structure cartoon (Chem 27)

**Source:** Day-1 recipe card (`context/recipe-card.jpg`) + the lecture deck it
references (`context/L13-fatty-acid-synthesis-lecture.pdf` — Chem 27, Lecture 13,
"Assembly Line Enzymology: Fatty Acid Biosynthesis I").

## Recipe (as written on the card)

- **Name:** Chem 27 — Fatty Acid Synthase Structure Cartoon
- **Ingredients (inputs):** Lecture files on fatty-acid synthesis · a picture of
  the original cartoon to be replaced.
- **Instructions:**
  - Produce a *new* cartoon showing **all domains** of the fatty-acid synthase
    enzyme, using the original image as a template.
  - **Include the termination domain**, which is currently absent from the
    existing cartoon.
  - Include labels for all domains.
- **Serving (output):** A picture file at moderate resolution that can be pasted
  into PowerPoint.

## What this project is

A figure-authoring task: regenerate an instructional enzyme diagram so it's
complete (all catalytic domains, incl. the missing termination/thioesterase
domain) and clearly labeled, matching the layout/feel of the original so it drops
into existing slides. The lecture PDF supplies the domain vocabulary and the
assembly-line framing the diagram should reflect.

## Build brief (for the subagent)

Populate `context/`, `prompts/`, `outputs/`. See the spawn instructions.
A reasonable sample output here is a **self-contained SVG/HTML diagram** of the
labeled FAS domains (code is the most reproducible "moderate-res image" we can
ship in-repo); note that the faculty member would export it to PNG for slides.
