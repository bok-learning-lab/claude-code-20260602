# Project memory — JB slide-deck explorer

## What this is
A starter project for **JB**, a close-reading philosopher who dislikes building
slide decks from scratch and wants to know whether Cowork can help turn his
scholarship into a presentation **without flattening the argument**. Half
artifact (a real deck), half experiment (an honest assessment of the workflow).

JB is anonymized throughout. We do **not** have his real paper, so this project
ships with a short, clearly-synthetic argumentative passage as a stand-in.
**JB swaps in his own paper** wherever the sample passage appears.

## Folder layout
- `context/`
  - `CLAUDE.md` — this file.
  - `sample-source-passage.md` — synthetic ~700-word philosophy argument (the
    stand-in for JB's real paper).
  - `deck-principles.md` — how to slide-ify a humanities argument *well*.
- `prompts/`
  - `01-outline-deck.md` — template: source paper -> structure-preserving outline.
  - `02-build-deck.md` — template: approved outline -> real deck file (.pptx).
- `outputs/`
  - `sample-deck-outline.md` — demonstrative outline built from the sample passage.
  - `assessment.md` — honest answer to JB's actual question.
  - `sample-deck.pptx` — (optional) a real deck built from the outline.

## The defining constraint
**Preserve the argument's structure.** A philosophy paper is a chain of moves —
thesis, premises, an objection, a reply — not a list of topics. The failure mode
this project exists to avoid is turning that chain into generic bullet mush
("Key points," "Background," "Conclusions") that loses the *reasoning*.

Concretely: one move per slide; slides should show where you are in the argument
(this is a premise / this is the objection / this is the reply); the nuance lives
in the **speaker notes**, not crammed onto the slide; bullets are minimal and
honest. If a passage can't survive this treatment, that is itself a finding —
say so rather than forcing it.

## Workflow
1. Drop the real paper into `context/` (replacing the sample passage).
2. Run `prompts/01-outline-deck.md` to get an outline. **Review and edit it** —
   this is where the philosopher's judgment matters most.
3. Run `prompts/02-build-deck.md` on the approved outline to produce the deck.
