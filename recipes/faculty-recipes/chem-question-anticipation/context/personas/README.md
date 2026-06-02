# Persona library — the simulated-student personas

This is the persona set for the simulator. Each persona is not a fictional character
but a **documented failure mode** from the chemistry-education-research (CER)
literature, translated into a voice a TF would actually hear across a table. Because
they are built from cognitive patterns rather than one topic, they transfer across the
whole department's intro sequence — general, organic, physical, and inorganic
chemistry — not just acid/base.

---

## The five failure modes

| Persona | Failure mode | Social texture (L2) | Key sources |
|---|---|---|---|
| **Procedure Follower** | Treats procedures as explanations; disconnects algorithmic steps from conceptual meaning | Confirms answers out loud | Cracolice et al. (2008), Nakhleh (1992), Bhattacharyya & Bodner (2005) |
| **Parts-to-Whole Projector** | Attributes emergent properties of a system to its component parts | Thinks out loud with conviction | Tümay (2016), Nakhleh (1992), Talanquer (2014) |
| **Single-Factor Reasoner** | Reduces multi-variable phenomena to one dominant factor; applies it universally | Summarizes and checks | Talanquer (2014), Tümay (2016), Bain et al. (2014) |
| **Everyday Language Student** | Reasons from colloquial meanings of scientific terms even after learning definitions | Casual and conversational | Bain et al. (2014), Nakhleh (1992) |
| **Pattern Matcher** | Categorizes problems by surface similarity to prior examples rather than causal reasoning | Enthusiastic connector | Bhattacharyya & Bodner (2005), Talanquer (2014) |

Each persona `.md` contains: **Role**, **Core Belief** (the misconception),
**Social Texture** (level 2 only), **Question Patterns**, **Example Questions**,
**Diagnostic Signals**, and **Research Grounding** (see `../research/`).

---

## The two levels

**Level 1 — failure mode transparent.** The misconception is legible directly in how
the student asks questions; the TF should be able to name the pattern mid-conversation.
Use when introducing the tool or training a TF new to pedagogical diagnosis.

**Level 2 — social texture added.** The same failure mode is equally present, but the
student feels like a real person — thinking out loud, summarizing with conviction,
connecting to prior examples with enthusiasm, or asking casually. Not *harder* to
diagnose, just more realistic to practice against.

```
personas/
├── level1/   ← failure mode transparent, diagnostic
│   ├── procedure-follower.md
│   ├── parts-to-whole-projector.md
│   ├── single-factor-reasoner.md
│   ├── everyday-language-student.md
│   └── pattern-matcher.md
└── level2/   ← same failure modes, social texture added
    └── (same five filenames)
```

---

## Picking a persona for a run

1. **Match the mode to the topic.** Acid strength / thermodynamics trends →
   Single-Factor Reasoner. Emergent or structure–property topics → Parts-to-Whole
   Projector. Mechanisms / categorization → Pattern Matcher. Vocabulary-heavy units
   (heat, entropy, spontaneity, equilibrium) → Everyday Language Student. Any
   "plug-and-chug" unit → Procedure Follower.
2. **Pick a level.** New TF or first rehearsal → Level 1. Experienced TF or a second
   pass → Level 2.
3. Paste the chosen persona file into a chat with Claude along with your lesson, and ask
   it to stay in character as that student — setting how hard to push (gentle, moderate,
   or relentless). When you're done, ask Claude to step out of character and debrief you.
