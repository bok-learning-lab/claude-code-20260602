# Prompt — "Top Tips" summary from a workshop transcript

**Input:** `inputs/day-1-transcript.md` (a timestamped, diarized transcript of a
live Learning Lab session)
**Output:** `outputs/day-1-top-tips.md`

Paste the prompt below into Claude (claude.ai or Cowork) along with the
transcript, or run it in Claude Code with the transcript path.

---

Read the attached transcript of a Learning Lab workshop session
(`inputs/day-1-transcript.md`). It's an automatically transcribed, diarized
recording — speakers are labeled (1-A, 1-B, …), timestamps are noisy, and the
transcription has occasional errors. Read past those.

I don't want a play-by-play recap of the demos. I want the **durable guidance** —
the principles and mental models the instructors kept returning to about *how to
think about and use these tools* so that a participant gets good output instead
of confident nonsense. The demos (multiplying big numbers, the Shakespeare
close reading, tidying the Downloads folder, the grading rubric) are evidence,
not the point — cite a demo only as a quick illustration of the underlying tip.

Write the result as a markdown file with this shape:

- An `# H1` title along the lines of "Day 1 — Top Tips for Using LLMs and
  Harnesses".
- A short 2–4 sentence intro paragraph immediately under the title that frames
  what this document is (the "how to think" half, as opposed to the click-by-click
  walk-through) and who it's for.
- A `---` horizontal rule.
- Then a numbered sequence of `## H2` sections, one per tip. Each heading is a
  punchy imperative or claim (e.g. "Give it context — don't ask cold, one-shot
  questions"), followed by 1–2 tight paragraphs explaining the idea and *why* it
  matters. Use **bold** for the one line a reader should remember, and *italics*
  for emphasis. Quote the instructors directly when they said something
  memorable.

Guidelines for the content:

- Aim for roughly 10–15 tips. Merge overlapping points; cut anything that's just
  workshop logistics.
- Keep the voice plain, warm, and practical — this is for Harvard faculty and
  staff who are not engineers. Explain jargon (tokens, context window, compact)
  in passing rather than assuming it.
- Where the instructors flagged a caveat or risk (data sensitivity, what folders
  to grant, "at your own risk" pilots), preserve it faithfully — don't soften it.
- It's fine to add a sentence of connective framing the instructors implied but
  didn't say outright; if you go beyond what was said, mark it (e.g. parenthetically).
- End with a tip about keeping human judgment in the loop — the tool extends the
  user, it doesn't replace them.

Save the result to `outputs/day-1-top-tips.md`.
