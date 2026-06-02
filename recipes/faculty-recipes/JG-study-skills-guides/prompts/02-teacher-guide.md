# Prompt template — teacher / tutor / coach-facing guide

Reusable template for drafting the **coach** guide from the **same** evidence base as
the student guide. Fill the `{{placeholders}}`, paste into Claude with the two context
files attached. Keep it parallel to `01-student-guide.md` — **same principles, same
order**, but framed as "how to coach a student on this."

---

## Prompt

You are helping faculty member **JG** write a **teacher / tutor / coach-facing**
guide grounded in learning science. The audience is **instructors, tutors, and
coaches** helping students build study skills.

**Read these first** (attached):
- `context/key-principles.md` — the shared evidence base. Same principles as the
  student guide; draw only from here for the science.
- `context/reading-list.md` — full references and the short citation keys.

**Cover these principles (use the same set and order as the student guide):**
{{PRINCIPLES_TO_FEATURE}}

**Length / format:** {{LENGTH}}

### Voice and stance
- **Practical, diagnostic, collegial.** Talk to a fellow educator. Assume they have
  limited time with each student and want moves they can use in the next session.
- For each principle, give the coach:
  1. **Why it matters** — the cognition, in one or two sentences (same mechanism the
     student guide explains, but stated for an instructor).
  2. **Diagnostics** — how to *spot* whether a student has this problem (the tells,
     the questions to ask, what their work or talk reveals).
  3. **Coaching moves** — 2–3 concrete things to do or assign that shift the student
     toward the better practice. Frame as nudging the student to self-direct, not
     doing the work for them.
- Where useful, point to the **parallel student-guide section** so the two stay in
  step ("this is the coach's side of the student's 'test yourself' advice").

### Citations
- Same short citation keys as the student guide, drawn from `reading-list.md`.
- **No copyrighted text.** Original prose. End with a **Sources** section.

### Optional secondary thread
If {{INCLUDE_HISTORY}} is yes, add **one short paragraph** on the historical
progression (behaviorism → cognitivism → constructivism; Mayer, 1992) and what it
implies for how we coach today — secondary, not the spine.

### Output
Markdown. Start with a one-line note: *"Draft — teacher/coach-facing guide. Parallel
to the student guide; grounded in `context/key-principles.md`; cites by reference."*
Then a title, a short intro, one section per principle (Why it matters / Diagnostics /
Coaching moves), and Sources.
