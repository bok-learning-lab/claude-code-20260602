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
TF rehearses the questions real students will ask. The artifact could be a custom
chatbot (a skill / system prompt) or a small HTML page; the deliverable students
turn in is the **chat transcript + their lesson plan.**

## Build brief (for the subagent)

Populate `context/`, `prompts/`, `outputs/`. See the spawn instructions.
The interesting design question: what makes a *useful* simulated student —
plausible misconceptions, varied levels, not just generic curiosity.
