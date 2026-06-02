# Grading student feedback on creative work

**Source:** Day-1 recipe card (`context/recipe-card.jpg`), reinforced by the Day-1
grading demo in the session transcript.

## Recipe (as written on the card)

- **Name:** Grading on Student Feedback of Student Creative Work
- **Ingredients (inputs):** Syllabus · Grading rubric for feedback · the Feedback
  itself (handwritten intent notes, end-of-summary comments — based on student
  questions vs. response) · the Student Work being responded to.
- **Instructions:** Grade and ascribe a short rationale for the grade.
- **Serving (output):** Grades of student feedback (with rationale).

## What this project is

The student isn't being graded on their *own* creative work — they're being
graded on the **quality of the feedback/critique they gave** to a peer's creative
work. Claude reads the rubric + the work + the feedback and proposes a grade with
a short, rubric-anchored rationale that the instructor then reviews.

## Relevant shared context

The transcript captures a closely related faculty workflow (speaker 1‑A): a
"draft-a-rubric" skill where Claude takes a prompt/solution + sample student work
+ prior rubrics + the instructor's notes on common mistakes, drafts a *straw-man*
rubric, the instructor edits it, and only then is it used to grade scanned
handwritten work — **Claude keeps the instructor honest by refusing to grade
until the human has vetted the rubric.** That human-in-the-loop pattern should
carry into this project.

## Build brief (for the subagent)

Populate `context/`, `prompts/`, `outputs/`. See the spawn instructions.
