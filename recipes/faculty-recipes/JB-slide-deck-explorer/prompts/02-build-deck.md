# Prompt template — Build the deck from an approved outline

**Purpose:** turn an **approved, edited** slide outline (from `01-outline-deck.md`)
into a real slide deck, **preserving speaker notes** so the argument survives.

**Prerequisite:** run `01-outline-deck.md` first and **edit the outline by hand**.
This step is mechanical; the judgment happened upstream. Garbage outline in,
garbage deck out.

**How to use:** fill in the `{{placeholders}}`, attach/paste the approved outline,
and send.

---

You are building a slide deck from an outline that a philosopher has already
reviewed and approved. Your job is faithful execution, not re-editing the
argument. Follow `../context/deck-principles.md`.

**Approved outline:** {{OUTLINE — attach or paste the edited outline; the
demonstrative one is `../outputs/sample-deck-outline.md`}}

**Output format I want:** {{FORMAT — choose one:
- "a real .pptx file" (preferred for a talk),
- "an HTML/Markdown deck",
- "leave it as a polished outline I'll build in Keynote/PowerPoint myself"}}

**Visual register:** {{STYLE — e.g. "plain and academic; text-forward; no stock
photos or icons; one idea per slide; lots of white space"}}

## Rules
1. **One move per slide**, exactly as the outline specifies. Do not merge, split,
   reorder, or "improve" the argument. If something in the outline looks wrong,
   *flag it and ask* — do not silently fix it.
2. **Put the key line on the slide; put the speaker notes in the notes field.**
   Speaker notes are not optional decoration — they carry the nuance and must be
   preserved verbatim (lightly tightened only for spoken delivery). Do not dump
   the notes onto the slide face.
3. **Keep bullets minimal and honest** — only those in the outline, each a claim.
4. **Quotations stay exact**, with attribution, especially the thesis and reply.
5. **Restraint over flash.** No decorative filler, no clip-art, no padding slides.
   Title slide + thesis + premises + objection + reply + upshot is a complete deck.

## If producing a real .pptx
Use the **pptx skill** to generate the file — it is the supported path to a real
PowerPoint, and it can write **speaker notes** into the notes field (essential
here: the notes are where the argument lives). Generate it, then report:
- the path to the .pptx,
- a slide-by-slide confirmation that each slide's speaker notes were carried over,
- any place where a slide felt too sparse or too dense, flagged for the author.

If a .pptx is not practical in this environment, produce a clean Markdown/HTML
deck with an explicit `Notes:` block per slide instead, and say so.
