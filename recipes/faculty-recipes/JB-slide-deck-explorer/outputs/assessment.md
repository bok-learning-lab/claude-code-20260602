# Is Cowork the right tool for turning your scholarship into a deck?

An honest answer to JB's actual question, from building the sample in this folder.

## Short version
**Yes — but as a drafting partner, not a ghostwriter, and on the condition that
you keep the editorial judgment.** The Cowork -> deck workflow is genuinely useful
for the part you dislike (the mechanical labor of laying out slides) and genuinely
dangerous for the part you care about (the argument), unless you split the work in
two and stay in charge of the second half.

## Where it clearly helps
- **It removes the chore, not the thinking.** The drudgery you "despise" —
  arranging slides, writing speaker notes, producing a real `.pptx` — is exactly
  what this does well. You bring the argument; it does the formatting.
- **It can be taught to preserve structure.** The whole design here is to make the
  tool reconstruct your *moves* (thesis / premises / objection / reply) and put
  **one move per slide**, with the nuance pushed into **speaker notes** rather than
  flattened onto the slide. With the principles file in `context/`, the default
  output respects argumentation instead of fighting it.
- **The outline step is a real editing surface.** `01-outline-deck.md` stops at an
  outline *on purpose*. That's a cheap, fast artifact you can mark up — moving,
  cutting, and rewording moves — before any deck exists. For a close reader, this
  is where the value is.
- **It forces a useful pre-mortem.** Asking the model to flag "flattening risks"
  surfaces precisely the slides where your argument resists slide form — often the
  most interesting parts of the paper.

## Where it risks flattening — watch these
- **Confident smoothing.** The failure mode isn't gibberish; it's plausible
  paraphrase that quietly drops a qualification or merges two distinct moves. You
  have to read the outline as a referee, not skim it.
- **Losing the dialectic.** Left alone, summarizers tend to drop objections
  because they "complicate the slide." Your objection and reply are the part a
  scholar defends; the templates here force them onto separate slides, but you
  should verify it every time.
- **Paraphrase where you'd want the exact sentence.** Pivotal lines (your thesis,
  your reply) should be quoted, not restated. Nuance leaks out in paraphrase.
- **False decomposability.** Some arguments — especially close readings of a text —
  don't break cleanly into discrete slide-sized moves. Forcing them into a deck
  distorts them.

## Recommendation
1. **Use it in two passes.** Generate an *outline* first (`01`), edit it by hand,
   then build the deck (`02`). Never let it go prose -> finished deck in one shot.
2. **Read the outline as a referee.** Check that each move survived, objections are
   intact, and the load-bearing sentences are quoted, not paraphrased.
3. **Let "no slides" be a valid answer.** For a close-reading or seminar talk, the
   honest output of this workflow may be *a projected passage and a handout*, not a
   deck. Recommending against slides is a success, not a failure, of the tool.
4. **Net:** worth adopting for the talks where slides are "more or less necessary."
   It will reliably save you the labor you dislike; it will *not* reliably protect
   the argument you care about — that part stays yours, and the workflow here is
   built to keep it that way.
