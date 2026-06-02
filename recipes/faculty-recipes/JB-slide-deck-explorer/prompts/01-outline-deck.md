# Prompt template — Outline a structure-preserving deck

**Purpose:** turn an argumentative paper into a slide *outline* that preserves the
argument's structure (thesis, premises, objection, reply) rather than flattening
it into generic bullets. This produces an **outline for you to review and edit** —
not a finished deck. (Build the deck with `02-build-deck.md` after you approve it.)

**How to use:** fill in the `{{placeholders}}`, attach or paste the paper, and send.

---

You are helping a philosopher turn a scholarly argument into a slide deck
**without flattening the argument into bullet-point mush**. Read
`../context/deck-principles.md` and follow it.

**Source paper:** {{PAPER — attach the file or paste the text; the stand-in is
`../context/sample-source-passage.md`}}

**Talk length:** {{TALK_LENGTH — e.g. "20 minutes" / "a 45-min job talk"}}
**Audience:** {{AUDIENCE — e.g. "philosophers in my subfield" / "a mixed
faculty audience, some non-specialists"}}

## Do this

1. **First, reconstruct the argument before touching slides.** In a few lines,
   state the paper's: thesis; the premises that support it; the central
   objection(s); the reply; and the conclusion / upshot. Quote the thesis and the
   pivotal reply in the author's own words. If you are unsure of a move, flag it
   rather than smoothing it over.

2. **Then propose a slide outline** where **each slide carries one move**. For
   each slide give:
   - **Slide title** — name the *structural role* ("Thesis," "Premise 2 of 3,"
     "The objection," "Reply"), not a generic topic.
   - **Key line** — the single load-bearing claim for that slide, one sentence,
     in the author's register; use an exact quotation for the thesis and the
     pivotal reply.
   - **Speaker notes** — 2–5 sentences carrying the nuance, the qualification,
     the example: the part that makes the claim defensible. This is where the
     argument actually lives.
   - **Bullets (only if genuinely needed)** — each a *claim*, never a topic word;
     omit entirely if the key line suffices.

3. **Calibrate slide count to the talk length and to the argument** — not to a
   template. Roughly one slide per ~1.5–2 minutes is a ceiling, not a target;
   fewer, denser-in-notes slides are usually better. Keep objection and reply on
   separate, adjacent slides.

4. **Flag flattening risks honestly.** If any move resists slide form — e.g. it
   depends on close reading of a passage, or the reasoning is too interdependent
   to decompose cleanly — say so, and suggest the alternative (a quotation slide,
   a handout, or skipping slides for that stretch). See "When NOT to use slides"
   in the principles file.

## Output format
- A short **"Argument reconstruction"** section.
- A **"Slide outline"** section, slides numbered, each with Title / Key line /
  Speaker notes / (optional) Bullets.
- A short **"Flattening watch"** section: where the deck risks losing the
  argument, and what to do about it.

Do **not** generate a .pptx yet. Stop at the outline so the author can edit.
