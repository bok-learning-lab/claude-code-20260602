# Project memory — Cognition-informed study-skill guides (JG)

## What this is

A synthesis-and-translation project for faculty member **JG** (graduate-education
leadership + lecturing in an engineering/applied-sciences school). The task: distill
a research base on learning and cognition into **two parallel guides off the *same*
evidence base** — one **student-facing** ("learn about your own learning") and one
**teacher / tutor / coach-facing** ("how to coach a student on this"). Output form is
a blog post or short series. The historical progression of learning-science guidance
is a *secondary* thread, not the spine.

## The defining constraint

**Two parallel audiences, one evidence base.** Both guides are built from the *same*
distilled principles in `context/key-principles.md`. For every principle, the
student guide says "here is what to do and why it works for you," and the teacher
guide says "here is how to diagnose and coach this in a student." The parallelism is
the point — a reader should be able to lay the two side by side and see the same
principle handled from both sides.

## Folder layout

- `context/` — the shared inputs both guides draw from.
  - `CLAUDE.md` — this file.
  - `reading-list.md` — the source list (full references + links + one-line note on
    what each contributes).
  - `key-principles.md` — ~7 evidence-based learning principles in original prose
    (principle, why it works, citation pointer). **The shared evidence base.**
- `prompts/` — reusable prompt templates for drafting each guide.
  - `01-student-guide.md` — template for the student-facing draft.
  - `02-teacher-guide.md` — parallel template for the coach-facing draft.
- `outputs/` — generated drafts.
  - `sample-student-guide.md` — short demonstrative excerpt (2 principles).
  - `sample-teacher-guide.md` — parallel coach-facing excerpt (same 2 principles).

## Citation expectation

This is rigorous-sourcing territory; JG is comfortable with it and expects it.

- **Do not reproduce copyrighted text** from the sources (How People Learn; How
  Learning Works; Redish; Mayer 1992; Bloom's taxonomy material). Work from
  well-known, attributable *principles* (retrieval practice, spaced practice, prior
  knowledge, metacognition, transfer, motivation, organized knowledge) in original
  prose.
- **Always attribute by reference.** Every principle and every guide section names
  which source(s) ground it. Use the short reference keys defined in
  `reading-list.md` (e.g., *How People Learn* (NRC, 2000); Ambrose et al., 2010;
  Redish, 2002; Mayer, 1992; Bloom et al., 1956 / revised Anderson & Krathwohl, 2001).
- Keep the person anonymized as **JG**. Do not invent a real name.
