---
name: fpf-name-card
description: >
  Design a deliberate, defensible name for an ambiguous role, programme, or
  artefact. Performs an honest search on the local Pareto-front of candidate
  names, declares trade-offs, and produces a Name Card with current name,
  problem, candidates, recommendation, and migration note. Triggers on "what
  should we call this," "name card," "rename role," "find a better name,"
  "this label is misleading," or "we keep arguing about what to call it."
argument-hint: "[current-name]"
---

# FPF — Name Card

Apply FPF patterns **F.18 (Name Card discipline)** and **E.10 (Lexical law: Tech / Plain registers)**.

## Principle

A bad name is a debt that compounds. Most teams keep a misleading label out of inertia ("everyone knows what we mean") until the cost of the drift exceeds the cost of the rename. The Name Card forces the rename decision to be made deliberately, with an audit trail.

A Name Card is *not* a rebrand. It's a small, structured choice document for one ambiguous label.

## When to use

- A role title that no longer matches the responsibility.
- An internal program name that confuses outsiders or new hires.
- An artefact name that overloads with another team's concept.
- A vendor / framework name being adopted as if it were a proper noun.
- A term flagged in [`fpf-uts`](../fpf-uts/SKILL.md) high-risk polysemy.

If multiple names need attention, run this skill once per name. A batch rename is a different exercise.

## Step 1: Capture the current name and the problem

| Field | Content |
|---|---|
| Current name | (verbatim) |
| What it currently refers to | 1 sentence |
| What's wrong with the current name | 1–3 sentences |

Common problems:

- **Polysemy** — the same word means something else in another context.
- **Outdated reference** — the name encodes a decision or scope that has changed.
- **Brand collision** — the name copies a vendor / framework / public concept.
- **Over-specific** — the name names one configuration but the entity is general.
- **Under-specific** — the name names a category but the entity is one specific instance.

## Step 2: Generate candidates on the Pareto front

Aim for 4–7 candidate names. Span the Pareto front along these axes:

- **Tech vs. Plain register** — at least one of each.
- **Descriptive vs. metaphor** — at least one of each.
- **Specificity** — span from highly specific to deliberately general.
- **Compounding** — single word, two-word phrase, abbreviation.

Reject candidates that:

- Reuse another team's owned vocabulary.
- Encode a current decision that may change (don't bake "v2" into a name).
- Require non-obvious pronunciation or spelling.
- Echo a known-difficult name in the literature.

## Step 3: Score the candidates

| Candidate | Tech / Plain | Strength | Cost |
|---|---|---|---|

Strength: what does this name do well? Cost: what does it sacrifice or risk?

This is a vector-valued comparison; do *not* collapse to a single score.

## Step 4: Recommend

State the chosen name and the rationale in 2–4 sentences. The rationale must reference the Pareto axes — "we picked X because it spans both registers and avoids the brand collision in Step 1."

## Step 5: Migration note

| Field | Content |
|---|---|
| Where the old name appears | (code paths, docs, slide decks, repos) |
| Risk of breakage | (low / medium / high — what breaks if we rename) |
| Rollout plan | (e.g., "alias for one quarter, then deprecate") |
| Owner of the migration | (named role) |

A Name Card without a migration note is half-done. The migration is where renames go to die.

## Step 6: Produce the artifact

Use the **Name Card** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). Save as `name-card-[current-name].md`.

## When to combine with other skills

- **Upstream:** [`fpf-uts`](../fpf-uts/SKILL.md) — UTS surfaces polysemy that often demands a Name Card.
- **Pairs with:** [`fpf-rewrite`](../fpf-rewrite/SKILL.md) — once renamed, downstream documents need same-entity rewrites.

## Anti-patterns

- **Listing 1–2 candidates.** That's not a Pareto front; it's a fait accompli.
- **Picking a clever name no one outside the team understands.** Cleverness is a cost, not a strength.
- **Skipping the migration note.** A rename without a migration plan is theatre.
- **Renaming to a vendor / framework name.** "We'll call it Whisper" — until Whisper is something else next year.
- **Renaming silently.** A rename is an event; record the date, the rationale, and the migration owner.
