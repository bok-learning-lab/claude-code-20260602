# FAS catalytic domains (from Chem 27, Lecture 13)

Mammalian **fatty acid synthase (FAS)** is one very large, multifunctional
assembly-line enzyme that functions as a homodimer (~272 kDa per monomer). All
reactions happen on this single multi-domain protein, which catalyzes de novo
fatty acid synthesis to produce primarily **palmitate (16 carbons)**. Each domain
carries out one distinct step in the cycle. (Lecture slides 11–22.)

## The domains, in the lecture's linear order

The lecture's domain map (slide 11) reads, N→C:

> **KS – MAT – DH – ER – KR – ACP – TE**

The lecture groups them functionally as **elongation**, **tailoring**, and
**termination** domains. (Naming note: the structural figure labels the
transferase **MAT** = *malonyl/acetyl transferase*; the mechanism slides label the
same domain **AT** = *acyl transferase*. They are the same domain — we use **AT
(MAT)**.)

### Elongation domains — add one 2-carbon unit per cycle via a decarboxylative Claisen condensation
| Domain | Name | One-line function |
|---|---|---|
| **AT** (MAT) | Acyl transferase (malonyl/acetyl transferase) | Selects the monomer (acetyl-CoA starter / malonyl-CoA extender) and transfers it onto ACP. Active site: serine. |
| **ACP** | Acyl carrier protein | Carries the growing chain between all the other domains on its long phosphopantetheinyl (thiol) arm. Active site: serine modified to a thiol arm. |
| **KS** | Ketoacyl synthase (keto synthase) | Accepts the growing chain from the previous ACP and catalyzes the (decarboxylative) Claisen condensation that forms the new C–C bond, extending the chain by 2 carbons. Active site: cysteine. |

### Tailoring domains — reduce the newly added β-ketone down to a methylene (–CH₂–)
| Domain | Name | One-line function |
|---|---|---|
| **KR** | β-Ketoreductase | Reduces the β-ketone of the previous unit to a hydroxyl. Requires NADPH (hydride source). |
| **DH** | Dehydratase | Eliminates that hydroxyl as water to form an α,β-unsaturated (enoyl) thioester. Active site: histidine general base. |
| **ER** | Enoyl reductase | Reduces the α,β-double bond to a saturated single bond, completing the methylene. Requires NADPH. |

### Termination domain — releases the finished fatty acid
| Domain | Name | One-line function |
|---|---|---|
| **TE** | Thioesterase | **Termination / release.** Once the chain reaches full length (palmitate, C16), TE hydrolyzes the thioester linking the chain to the ACP arm, cutting the finished free fatty acid off the assembly line. |

## The cycle (elongation → tailoring), then termination
1. **Load** the starter (acetyl-CoA) and extender (malonyl-CoA) units via **AT**, onto **ACP**.
2. **Elongate**: **KS** runs the decarboxylative Claisen condensation, adding 2 carbons and creating a β-ketone.
3. **Tailor**: **KR → DH → ER** reduce that β-ketone all the way down to a methylene.
4. **Repeat** the elongation+tailoring cycle (~7 rounds) to build up to C16, **ACP** shuttling the chain throughout.
5. **Terminate**: **TE** hydrolyzes the thioester and releases palmitate.

## ⚠️ The domain the OLD cartoon is missing
**TE (thioesterase) — the termination domain.** The existing cartoon shows the
elongation and tailoring domains but stops there, so it never depicts how the
finished fatty acid actually comes *off* the enzyme. The new cartoon must include
**TE**, clearly labeled, as the final domain. (TE appears in the lecture's linear
domain bar and in the Lecture 13 objectives list — "AT, ACP, KS, KR, DH, ER, TE" —
even though it doesn't get its own mechanism slide.)
