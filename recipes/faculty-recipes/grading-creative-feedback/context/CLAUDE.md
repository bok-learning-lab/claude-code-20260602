# Project memory: Grading peer feedback on creative work

## What this project is

This project helps an instructor **grade the quality of the feedback students
give to a peer's creative work** — not the creative work itself. A student reads
a classmate's flash fiction (or poem, short essay, etc.), writes feedback, and is
graded on how *useful, specific, and generous* that feedback is.

Claude's job: read the rubric + the original creative work + the student's
feedback, and **draft** a grade with a short, rubric-anchored rationale that the
instructor then reviews.

## Folder layout

- `context/` — the stable inputs. The rubric, course/syllabus context, and the
  sample materials live here. This file (`CLAUDE.md`) is project memory.
  - `feedback-rubric.md` — the criteria and point bands used to grade feedback.
  - `course-context.md` — syllabus excerpt: the course, the assignment, weighting.
  - `sample-creative-work.md` — the peer's creative work being responded to.
  - `sample-student-feedback.md` — one student's feedback on that work.
- `prompts/` — reusable prompt templates with `{{placeholders}}`.
  - `01-grade-feedback.md` — draft a grade for one student's feedback.
  - `02-norming-pass.md` — optional calibration pass across several samples.
- `outputs/` — generated drafts for the instructor to vet.
  - `sample-grade-rationale.md` — a demonstrative sample of what 01 produces.

## THE NON-NEGOTIABLE RULE: human in the loop

**Claude proposes; the instructor disposes.** Every grade Claude produces is a
*draft for review*, never a final grade. Concretely:

1. Claude must always label its output as a **DRAFT / proposal**, not a verdict.
2. Claude must anchor every score to a specific rubric criterion and **quote the
   student's feedback** as evidence — so the instructor can check the reasoning,
   not just the number.
3. Claude must **not** record, finalize, or export a grade. The instructor reads
   the draft side by side with the work, edits or overrides as needed, and only
   then assigns the grade.
4. When the rubric is ambiguous, Claude flags the ambiguity rather than guessing.

This mirrors the Day-1 demo where the instructor made Claude "keep me honest" —
it drafts, the human vets, and the grade stays the instructor's grade.
