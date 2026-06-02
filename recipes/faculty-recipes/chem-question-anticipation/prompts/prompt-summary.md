# Project Development Summary
*How the student simulation tool came together*

---

## Starting point

The project began with `project_as_recipe.md`, a sketch from the Bok Center's Summer of Claude workshop. The core idea: a tool for graduate teaching fellows in Chem 301 (the department's pedagogy seminar) that simulates student questions to help TFs prepare for section. The input would be a lesson plan or microteaching question; the output would be a conversation with a simulated confused student. The chat log would be submitted alongside the lesson plan as a Chem 301 deliverable.

The recipe sketch left implementation open ("Claude plugin? HTML site? Or just a custom chatbot?") and identified a corpus of prior student questions as a key ingredient that hadn't been assembled yet.

---

## Literature review

Four papers were already in the folder at the start:

- **Nakhleh (1992)** — foundational survey of chemical misconceptions; particulate nature of matter as the core gap
- **Cracolice, Deming & Ehlert (2008)** — algorithmic vs. conceptual problem solving; students without reasoning skills default to memorized procedures
- **Tümay (2016)** — emergence as a structural feature of chemistry that produces predictable misconceptions; students attribute emergent properties to component parts
- **Bain, Moon, Mack & Towns (2014)** — review of thermodynamics misconceptions at the university level; alternative conceptions of heat, entropy, and spontaneity

A literature search identified gaps and recommended additional sources, organized by what was missing:

**Organic chemistry** (largest gap): Bhattacharyya & Bodner (2005), "It Gets Me to the Product" — students reason backward from products using pattern-matching rather than electron flow; Flynn & Featherstone (2017) on acid-base reasoning across the general-to-organic transition; Cooper et al. (2019) OCLUE curriculum for the framework behind mechanistic reasoning.

**Chemical bonding**: Luxford & Bretz (2014) Bonding Representations Inventory — documented bonding misconceptions post-instruction in general chemistry.

**Cross-cutting heuristics**: Talanquer (2014), "Chemistry Education: Ten Heuristics to Tame" — catalog of cognitive shortcuts students use across all chemistry sub-areas; identified as the most generative single source for designing student simulation prompts.

**Quantum/atomic structure**: Concept inventory for quantum chemistry (2016); paper on atomic orbital energy diagram misconceptions (2022) — relevant for Chem 10 and Chem 160 TFs.

**GTA training**: Marbach-Ad et al. (2017) on TA knowledge and beliefs after professional development; GTA training course development paper (2019) — both directly relevant to the Chem 301 context.

Reading priority recommended: Bhattacharyya & Bodner first (fills biggest content gap), then Talanquer (2014) for the cross-cutting framework, then Flynn & Featherstone for the PS11→organic transition, then Marbach-Ad et al. for the GTA training design.

---

## Persona design decisions

### Organizing principle: failure mode over sub-area

The first design decision was how to organize the five personas. Two options were considered:

- **By sub-area** (e.g., organic student, physical chemistry student): more immediately recognizable to a TF prepping a specific lesson, but less transferable — the same cognitive patterns appear across all sub-areas, and sub-area personas would need to be replaced when the curriculum changes.

- **By failure mode / reasoning pattern**: grounded in how the CER literature actually organizes student difficulties. Talanquer, Tümay, Nakhleh, and Cracolice all describe *how* students think, not *what topic* they're thinking about. A TF who learns to recognize "single-factor reasoning" is better equipped across their whole teaching career.

**Decision: organize by failure mode.** The tradeoff (less immediately recognizable for a specific lesson) is mitigated by grounding each persona's example questions in concrete chemistry content.

### The five failure modes

Derived from the literature:

1. **Procedure Follower** — treats procedures as explanations; algorithmic competence disconnected from conceptual meaning. *(Cracolice et al., Nakhleh, Bhattacharyya & Bodner)*
2. **Parts-to-Whole Projector** — attributes emergent properties of systems to component parts; can't account for structure and interaction. *(Tümay, Nakhleh, Talanquer)*
3. **Single-Factor Reasoner** — reduces multi-variable phenomena to one dominant factor and applies it universally. *(Talanquer, Tümay, Bain et al.)*
4. **Everyday Language Student** — reasons from colloquial meanings of scientific terms (heat, entropy, spontaneous, equilibrium) even after learning definitions. *(Bain et al., Nakhleh)*
5. **Pattern Matcher** — categorizes problems by surface similarity to prior examples rather than causal reasoning. *(Bhattacharyya & Bodner, Talanquer)*

### Two-level structure

Each failure mode is implemented at two levels:

**Level 1 — failure mode transparent.** Questions are written so the cognitive pattern is audible directly in how the student asks. The Procedure Follower asks "which equation do I use?"; the Single-Factor Reasoner asks "so electronegativity is always what determines acid strength, right?" A TF working through level 1 should be able to name the failure mode mid-conversation. Designed as a training mode for TFs who are new to pedagogical diagnosis.

**Level 2 — social texture added.** The same failure mode, equally legible, but the student behaves more like a real person. Each persona has a characteristic social texture:

| Persona | Level 2 social texture |
|---|---|
| Procedure Follower | Confirms answers out loud |
| Parts-to-Whole Projector | Thinks out loud with conviction |
| Single-Factor Reasoner | Summarizes and checks |
| Everyday Language Student | Casual and conversational |
| Pattern Matcher | Enthusiastic connector |

**One important correction in development:** An early draft of level 2 framed the social textures as obstacles — the social behavior was designed to *obscure* the failure mode and make it harder to diagnose. This was wrong. The intent is for level 2 to add realism without adding difficulty. The failure mode should be equally legible at both levels; level 2 just feels more like sitting across from an actual student. The files were revised accordingly.

---

## Implementation decisions

**Delivery mechanism: Slack bots.** TFs upload a lesson plan to a Slack bot configured with a persona. The bot reads the lesson plan and generates in-character questions specific to that lesson's content — not generic chemistry questions, but questions a student with that failure mode would ask about what the TF is actually teaching. The TF responds; the conversation is logged and submitted to Chem 301.

**Course scope.** An early version of the README specified PS11 (*Foundations and Frontiers of Modern Chemistry*) as the target course. This was walked back: the tool is designed for TFs across the department's undergraduate courses. PS11 is noted as the most likely initial source for a corpus of real student questions, not as the fixed scope.

---

## Current state of the folder

```
/
├── README.md                         ← project overview and folder guide
├── prompt-summary.md                 ← this file
├── project_as_recipe.md              ← original project sketch
├── Chemistry Course Offerings.md     ← department course list (2026–27)
│
├── personas/
│   ├── level1/                       ← 5 failure-mode personas, diagnostic
│   └── level2/                       ← same 5 with social texture
│
└── [research notes]
    ├── Nakhleh_1992.md
    ├── Cracolice et al_2008.md
    ├── Tümay_2016.md
    └── Bain et al_2014.md
```

---

## What comes next

The three main pieces still to build, in rough order of dependency:

1. **Slack bot system prompt template** — a wrapper that tells the bot how to ingest a lesson plan and generate in-character questions using a given persona. This is the bridge between the persona files and the actual tool.

2. **Course-specific question banks** — example questions keyed to actual PS11 (and other course) topics, to supplement the research-derived examples already in the personas. Likely built from prior TF section notes and student question logs once those are assembled.

3. **Chem 301 debrief materials** — a rubric for reviewing submitted chat logs and a facilitation guide for introducing the tool in the seminar.
