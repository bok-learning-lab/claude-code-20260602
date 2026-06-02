# Project memory: Chem 301 Student Simulator

## What this is
A **"student simulator"** for **Chem 301**, the graduate pedagogy seminar for
chemistry teaching staff. A Teaching Fellow (TF) brings a microteaching
mini-lesson they plan to deliver to intro-chemistry students. Claude role-plays a
*confused or curious intro-chem student* and interrogates the lesson — asking the
questions, voicing the misconceptions, and pushing on the gaps that real students
actually surface. The TF rehearses against this simulated student, then gets a
debrief.

The point is **anticipation**: most new TFs can present content but are caught off
guard by where novices get stuck. This tool lets them meet those questions in
rehearsal instead of live.

## How it's used (the loop)
1. TF writes or pastes a mini-lesson into `context/sample-microteaching-lesson.md`
   (or supplies their own).
2. TF picks a persona from `context/student-personas.md`.
3. TF runs `prompts/01-student-simulator.md`, filling in the `{{lesson}}` and
   `{{persona}}` placeholders. Claude stays in character as that student and asks
   questions until the stop condition is met.
4. TF runs `prompts/02-debrief.md`. Claude steps OUT of character and gives feedback:
   what was handled well, what exposed gaps, what to add to the lesson.
5. TF saves the full exchange to `outputs/` as their transcript. **The deliverable
   handed in for Chem 301 is the transcript + the lesson plan.**

## Folder layout
```
context/
  CLAUDE.md                       <- this file
  student-personas.md             <- 3-4 simulated-student profiles + misconceptions
  sample-microteaching-lesson.md  <- an example TF mini-lesson (acid/base equilibria)
  question-bank-notes.md          <- common intro-chem confusions (the "prior-years" corpus)
prompts/
  01-student-simulator.md         <- system-prompt TEMPLATE: Claude becomes the student
  02-debrief.md                   <- TEMPLATE: Claude steps out of character to coach the TF
outputs/
  sample-session-transcript.md    <- a DEMONSTRATIVE sample run + debrief
  simulator.html                  <- optional static framing page (instructions + personas)
```

## Design principle
A *useful* simulated student is grounded, not generically curious. The personas
carry **specific, documented intro-chem misconceptions** (see `question-bank-notes.md`),
sit at **different levels of confidence and ability**, and probe at a tunable
intensity. Generic "Can you explain more?" prompts are explicitly out of scope.
