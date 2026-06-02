# Prompt template: Draft a grade for one student's peer feedback

> Reusable template. Replace each `{{placeholder}}` (or, in Claude Code / Cowork,
> just point Claude at the files in `context/` and it will read them). The point
> of this prompt is a **draft for the instructor to vet** — not a final grade.

---

You are helping me grade the **quality of the feedback** one student gave on a
peer's creative work. You are NOT grading the creative work itself.

**Read these inputs:**

- **Course context:** {{course-context, e.g. context/course-context.md}}
- **Rubric for evaluating feedback:** {{feedback-rubric, e.g. context/feedback-rubric.md}}
- **The original creative work being responded to:** {{sample-creative-work, e.g. context/sample-creative-work.md}}
- **The student's feedback to grade** (intent/margin notes + end-of-summary
  comments): {{sample-student-feedback, e.g. context/sample-student-feedback.md}}

**Do this:**

1. Score the feedback against **each rubric criterion**, using the point bands.
2. For every score, give a one-to-two-sentence rationale that **quotes the
   student's feedback** as evidence (so I can check your reasoning, not just the
   number).
3. Sum the criteria into a total out of 20 and note the suggested letter band.
4. Add a short **"For the instructor"** note: anything ambiguous in the rubric,
   anything you were unsure about, and any place where reasonable graders might
   disagree.

**Hard rules (do not break these):**

- This is a **DRAFT proposal, not a final grade.** Label it that way at the top.
- Do not invent feedback the student did not write. Quote only what is in the
  feedback file.
- If the rubric is unclear for a given case, **flag it** rather than guessing.
- Do not record, finalize, or "submit" anything. I will read your draft side by
  side with the work, edit or override, and assign the grade myself.

Begin your reply with: **"DRAFT FOR INSTRUCTOR REVIEW — not a final grade."**
