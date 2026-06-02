# Prompt template — student-facing guide

Reusable template for drafting the **student** guide ("learn about your own
learning") from the shared evidence base. Fill the `{{placeholders}}`, paste into
Claude with the two context files attached, and iterate. Keep it parallel to the
teacher template (`02-teacher-guide.md`) — same principles, learner-facing voice.

---

## Prompt

You are helping faculty member **JG** write a **student-facing** study-skills guide
grounded in learning science. The audience is **undergraduate students** learning
about their own learning.

**Read these first** (attached):
- `context/key-principles.md` — the shared evidence base. Draw only from here for the
  science; do not introduce unsourced claims.
- `context/reading-list.md` — full references and the short citation keys to use.

**Write the guide covering these principles:** {{PRINCIPLES_TO_FEATURE}}
*(e.g. "Prior knowledge; Retrieval practice; Spacing & interleaving" — or "all seven")*

**Length / format:** {{LENGTH}}
*(e.g. "a single ~1,200-word blog post" or "a 5-post series, ~400 words each")*

### Voice and stance
- **Encouraging, concrete, self-directed.** Talk *to* the student ("you"). Assume a
  capable, busy undergraduate who wants advice they can act on tonight.
- For each principle: name it in plain language, give **one or two concrete moves**
  the student can do this week, and briefly say **why it works** (the cognition) so
  the advice is believable, not just asserted.
- Name and dispel the relevant **illusion of competence** where it applies (e.g.
  "rereading feels like learning but isn't").
- Optional, brief: one **self-check** per principle ("how do I know it's working?").

### Citations
- Attribute each principle to its grounding source using the short keys from
  `reading-list.md`, e.g. "(Ambrose et al., 2010)" or "as summarized in *How People
  Learn* (NRC, 2000)." Light but honest — this is a blog post, not a paper.
- **Do not reproduce copyrighted text.** Original prose only.
- End with a short **Sources** section listing the full references used.

### Optional secondary thread
If {{INCLUDE_HISTORY}} is yes, add **one short framing paragraph** on the historical
progression (behaviorism → cognitivism → constructivism; Mayer, 1992) — secondary,
not the spine.

### Output
Markdown. Start with a one-line note: *"Draft — student-facing guide. Grounded in
`context/key-principles.md`; cites sources by reference."* Then a title, a short
intro, one section per featured principle, and Sources.
