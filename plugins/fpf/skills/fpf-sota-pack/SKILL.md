---
name: fpf-sota-pack
description: >
  Build a state-of-the-art pack: scope, schools of thought (TraditionCards),
  operators (OperatorCards), portfolio scaffold, and refresh discipline. Use
  when the deliverable is a reusable harvest / generator for a discipline,
  not a one-off recommendation. Triggers on "state of the art," "SoTA pack,"
  "harvest schools of thought," "build a portfolio kit," "TraditionCards,"
  "OperatorCards," or "survey the field."
argument-hint: "[discipline]"
---

# FPF — State-of-the-Art Pack

Apply FPF patterns **G.0 (CG-Spec / CG-Frame)**, **G.1 (Scope & schools)**, **G.2 (Harvest & TraditionCards)**, **G.4 (OperatorCards)**, **G.5 (Selector / dispatcher)**, **C.18 (NQD-CAL)**, and **C.19 (Explore-Exploit Governor)**.

## Principle

Most "state of the art" surveys are leaderboard snapshots: ordered lists by single aggregate score. They decay fast and hide the conceptual structure of the field. An FPF SoTA pack is a *reusable kit* — schools of thought, their operators, their assumptions, with refresh discipline. The pack is a generator, not a snapshot.

This skill is FPF entry family **5 (Generator / state-of-the-art / portfolio kit)**. It feeds [`fpf-portfolio`](../fpf-portfolio/SKILL.md) when a real selection is needed.

## Step 1: Define scope (G.1)

A scope statement bounds the pack:

- **Discipline** — what is in?
- **Out of scope** — what is explicitly excluded?
- **Time horizon** — last 3 years? last 10? lifetime?
- **Languages / venues** — English-language, peer-reviewed, conference + journal?
- **Audience for the pack** — who will use it, and for what?

A pack with no scope statement is unbounded and unmaintainable.

## Step 2: TraditionCards (G.2)

A Tradition is a school of thought — a cluster of approaches sharing assumptions, vocabulary, and canonical works. For each Tradition:

```
### Tradition: [Name]
- Founders / canonical works:
- Core operators:
- Key assumptions:
- Vocabulary signatures:
- Strengths:
- Known limits:
- Currently active groups / labs:
```

Aim for 4–8 TraditionCards per discipline. Fewer means the harvest is incomplete; more means clustering is needed.

The clustering is the work. A pack that lists 100 papers without traditions is not a pack — it's a bibliography.

## Step 3: OperatorCards (G.4)

An Operator is a concrete update rule, algorithm, or technique that lives within one or more Traditions. For each:

```
### Operator: [Name]
- Tradition(s):
- What it does:
- When to use:
- Inputs / outputs:
- Known failure modes:
- Reference implementations:
```

Aim for 2–5 OperatorCards per Tradition. The OperatorCards are what downstream selectors (G.5) actually reach for.

## Step 4: Portfolio scaffold (G.5)

The scaffold is the table that downstream `fpf-portfolio` will use:

| Candidate | Tradition | Operator | Maturity | Status (live / shortlisted / sunset) |
|---|---|---|---|---|

This is the bridge from harvest to selection. Without it, the pack does not connect to actual decisions.

## Step 5: Refresh discipline

A pack that is not refreshed becomes the "old SoTA." Declare:

- **Refresh cadence** — how often is the pack revisited (quarterly, annually)?
- **Decay markers** — what triggers an out-of-cycle refresh? (a new top venue, a paradigm-shifting paper, a vocabulary shift)
- **Refresh owner** — who carries the burden of refresh?
- **Versioning** — how is each refresh marked and indexed?

## Step 6: Produce the artifact

Use the **SoTA Pack** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). Save as `sota-pack-[discipline].md`. A pack is a *living* document; structure it so each refresh appends rather than overwrites.

## When to combine with other skills

- **Feeds:** [`fpf-portfolio`](../fpf-portfolio/SKILL.md) — the scaffold is the candidate list.
- **Feeds:** [`fpf-decision-criteria`](../fpf-decision-criteria/SKILL.md) — operators have natural characteristics.
- **Pairs with:** [`fpf-uts`](../fpf-uts/SKILL.md) — vocabulary signatures of Traditions go into the UTS.

## Anti-patterns

- **A bibliography, not a pack.** TraditionCards are required.
- **Listing one Tradition.** If only one cluster exists, the pack is too narrow or you're missing the rivals.
- **Skipping refresh discipline.** A snapshot is not a pack.
- **Aggregating into a single ranking.** Use vector-valued comparison, per characteristic; selection is a downstream skill.
- **Treating vendor claims as Tradition descriptions.** Vendor positions are one input, in one context.

## Notes

The SoTA pack is the FPF tool for *staying current* on a fast-moving field. It is heavier than [`fpf-portfolio`](../fpf-portfolio/SKILL.md) (which is per-decision) and lighter than a full literature review. Use it when the same field will inform many decisions, over time.
