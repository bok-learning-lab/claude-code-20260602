# Anticipating student questions in chemistry

**Source:** Day-1 recipe card (`context/recipe-card.jpg`).

## Recipe (as written on the card)

- **Name:** Anticipating Student Questions in Chemistry
- **Ingredients (inputs):** Corpus of student questions from prior years in PS11
  (compiled from TFs) · microteaching questions · past student work (?) ·
  *OR* a few scenarios of student confusion for TFs to work through (much like
  the Rhonda Bondie approach).
- **Instructions:** An HTML site? Or just a custom chatbot?
- **Serving (output):** For use by grad students in **Chem 301** (a pedagogy
  seminar). TFs (Teaching Fellows) upload their microteaching question and
  get asked questions by simulated "students" to help them prep their lesson and
  improve their ability to anticipate student questions. Students upload a log of
  their chat alongside their lesson plan.

## What this project is

A **"student simulator"**: a practice partner that role-plays a confused or
curious intro-chemistry student, interrogating a TF's planned mini-lesson so the
TF rehearses the questions real students will ask. The artifact is a reusable
system prompt (paste into a chat, or wire into a Slack bot); the deliverable
students turn in is the **chat transcript + their lesson plan.**

## The personas (what makes the simulated student useful)

A *useful* simulated student is grounded, not generically curious. The simulator's
personas live in **`context/personas/`**: five **failure modes** documented in the
chemistry-education-research (CER) literature — Procedure Follower, Parts-to-Whole
Projector, Single-Factor Reasoner, Everyday Language Student, Pattern Matcher — each
written at **two levels**: *level 1* makes the misconception transparent (diagnostic
training); *level 2* wraps the same mode in realistic social texture. Built from
cognitive patterns, they transfer across general, organic, physical, and inorganic
chemistry — a TF swaps in whichever mode fits their lesson. See
`context/personas/README.md` to pick one.

The CER sources behind the personas (citations inside each persona file) are kept as
notes and PDFs in **`context/research/`**.

## How to run it
1. TF puts their mini-lesson in `context/sample-microteaching-lesson.md` (or supplies
   their own).
2. Pick a persona + level from `context/personas/` (see its `README.md`).
3. Start a chat with Claude: paste in the chosen persona file and your lesson, and ask
   Claude to stay in character as that student — questioning your lesson and voicing the
   misconception. Tell it how hard to push (gentle, moderate, or relentless). Claude
   stays in character until you signal you're done (e.g. type `DEBRIEF`).
4. Ask Claude to step out of character and debrief you — what you handled well, what
   exposed a gap, and what to add to the lesson.
5. Save the exchange to `outputs/`. **The Chem 301 deliverable is the transcript + the
   lesson plan.** A demonstrative run is in `outputs/sample-session-transcript.md`.
