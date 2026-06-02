# Prompt template — generate / regenerate the FAS domain cartoon

Reusable prompt for (re)building the labeled fatty-acid-synthase domain cartoon as
a self-contained SVG/HTML file. Fill in the `{{placeholders}}`, paste into Claude,
and iterate. See `../context/fas-domains.md` for the authoritative domain list and
`../context/CLAUDE.md` for the project requirement.

---

You are creating an instructional cartoon of **mammalian fatty acid synthase (FAS)**
for a Chem 27 lecture slide. Produce a **single self-contained HTML file with an
inline SVG** (no external assets, no JS required to render). It must be clean,
legible at slide scale, and exportable to PNG by screenshot.

**Visual style:** {{visual_style — e.g. "match the original template: a horizontal
beads-on-a-string / linear assembly-line of rounded-rectangle domain blocks,
flat colors, sans-serif labels, light background"}}

**Layout:** {{layout — e.g. "single horizontal row, left→right, in biosynthetic
order; connect the blocks with a thin linker line to read as one polypeptide"}}

**Domains to include (ALL of them — do not omit any):** {{domains — default order
from the lecture's domain bar, N→C: KS, AT (MAT), DH, ER, KR, ACP, TE}}

**REQUIRED — the termination domain:** You MUST include the **TE (thioesterase)**
domain as the final block, clearly labeled. TE is the *termination/release* domain
and is the one **missing from the cartoon we are replacing** — its omission is the
entire reason for this redo. Do not produce a version without TE.

**Labels:** {{label_requirements — e.g. "every domain labeled with its
abbreviation inside the block AND its full name; group/annotate the blocks as
Elongation (AT/MAT, ACP, KS), Tailoring (KR, DH, ER), and Termination (TE)"}}

**Title + legend:** Include a title ({{title — e.g. "Mammalian Fatty Acid Synthase
— Catalytic Domains"}}) and a small legend mapping each abbreviation to its full
name and one-line function (pull functions from `fas-domains.md`).

**Color cues (optional, to echo the lecture):** {{colors — e.g. "AT teal, ACP
magenta, KS blue, KR yellow-green, DH green, ER red, TE purple"}}

**Scientific accuracy:** Match the **lecture's** vocabulary and emphasis (the PDF
wins over outside conventions). Note that the lecture labels the transferase domain
**AT** in mechanism slides and **MAT** in the structural figure — use {{at_label —
default "AT (MAT)"}}. Keep the assembly-line framing: ACP carries the growing chain
between domains; KS runs the decarboxylative Claisen condensation; KR/DH/ER tailor
the new β-ketone down to a methylene; TE hydrolyzes the thioester to release
palmitate (C16).

**Output note:** Add an HTML comment at the top of the file reminding the user that
this is meant to be screenshotted / exported to PNG at ~2x for pasting into
PowerPoint.

After generating, briefly list which domains you included so the user can confirm
TE is present.
