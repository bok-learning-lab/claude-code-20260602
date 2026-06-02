# Slide-deck explorer (faculty member JB)

**Source:** an email sent in lieu of a recipe card — see
`context/email-from-JB.md` (anonymized).

## Recipe, reconstructed

- **Ingredients (inputs):** one of JB's own scholarly philosophy papers (on the
  ethics of automated decision-making) as the raw source text; optionally target
  talk length and audience.
- **Instructions:** turn dense argumentative humanistic prose into a presentation
  *without* flattening the argument into bullet-point mush.
- **Serving (output):** a slide deck — **plus** an honest assessment of whether
  Cowork is the right tool for a humanist who dislikes making slides.

## What this project is

Half artifact, half experiment. JB is a close-reading philosopher exploring what
AI can do for traditional scholarship; the immediate pain point is that he
"despises creating slide decks from scratch." The deliverable tests the
Cowork → deck workflow for someone who values argumentation and nuance over
flash.

## Build brief (for the subagent)

Populate `context/`, `prompts/`, `outputs/`. See the spawn instructions.
We don't have JB's paper in-repo: use a **short stand-in argumentative passage**
(public-domain or clearly synthetic philosophy text) in `context/` so the prompt
templates and sample deck are demonstrable, with a clear note that JB swaps in his
own paper. The sample output should be a deck outline (and, if practical, a small
real `.pptx` or HTML deck) that **preserves the argument's structure** — premises,
moves, objections — rather than reducing it to generic bullets.
