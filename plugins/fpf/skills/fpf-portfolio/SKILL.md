---
name: fpf-portfolio
description: >
  Build an alternative portfolio for a decision. Keeps search wide before
  selection, declares the explore-exploit policy (keep frontier / narrow to
  subset / sequential commitment), and writes sunset criteria so candidates
  can be dropped lawfully. Triggers on "alternatives portfolio," "compare
  options," "explore vs exploit," "which architecture," "candidate options,"
  "lawful comparison," or "shortlist."
argument-hint: "[decision-subject]"
---

# FPF — Alternative Portfolio

Apply FPF patterns **G.0 (CG-Spec / CG-Frame)**, **C.18 (NQD-CAL open-ended search)**, **C.19 (Explore-Exploit Governor)**, **A.19.SelectorMechanism**, and **G.5 (selector / dispatcher)**.

## Principle

In open-ended work, diversity of options matters before selection. A single-vendor or single-architecture decision with no portfolio is premature convergence — a category-3 failure in FPF terms. Keep candidates live until selection is forced by a real gate.

This skill assumes you have already declared characteristics for the decision (run [`fpf-decision-criteria`](../fpf-decision-criteria/SKILL.md) first or in parallel).

## Step 1: Declare the portfolio policy

Pick one explore-exploit policy (C.19):

- **Keep frontier** — explore alternatives in parallel; multiple may proceed.
- **Narrow to subset** — evaluate, then confirm or pivot to a smaller live set.
- **Sequential commitment** — commit to primary; alternatives are fallback only.
- **Open exploration** — no primary yet; aim is shortlist authoring.

A "no policy" portfolio is not a portfolio.

## Step 2: Enumerate candidates

For each candidate, fill the row:

| Candidate | School of Thought | Key Mechanism | Prior Evidence in Our Context |
|---|---|---|---|

A school of thought groups candidates that share assumptions (e.g., contrastive learning, masked prediction, joint embedding predictive). Naming the school keeps the comparison legible — and helps spot families with no candidates yet.

Aim for 4–8 candidates. Fewer means the search is too narrow; more means schools-of-thought clustering is needed first.

## Step 3: State lawful comparison requirements

What must be the same across candidates for comparison to be lawful?

- Same data splits (or declared per-split policy).
- Same compute budget (or declared budget-performance curve).
- Same evaluation protocol (linear probe, fine-tune, end-to-end).
- Same metric definitions (with units).

This is the CN-frame from `fpf-decision-criteria`, applied. If it is missing, the experiment that selects from this portfolio will be non-comparable.

## Step 4: Selection mechanism

Specify how the selection actually happens:

- **Hard gates** — thresholds that disqualify a candidate before any soft comparison.
- **Soft comparison** — vector-valued, per-characteristic.
- **Decision rule** — single winner / top-K live / per-context dispatch.
- **Decision gate** — date / event after which the policy changes.

## Step 5: Sunset line (C.19)

Declare in advance:

- What evidence triggers a candidate's removal? (e.g., "fails to converge in budget; >20% below leader on majority of downstream tasks")
- Who has authority to sunset?
- What's the appeal path?

A portfolio without sunset criteria becomes a graveyard of half-evaluated options.

## Step 6: Portfolio health check

Before publishing, audit:

- **Diversity** — do schools of thought span the live frontier?
- **Evidence maturity** — how many candidates have been validated in our context vs. extrapolated from other domains?
- **Selection pressure** — is there a real gate forcing a choice, or are we sandbagging the portfolio indefinitely?
- **FPF concern** — what is the single biggest weakness in this portfolio?

## Step 7: Produce the artifact

Use the **Alternative Portfolio** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). Save as `portfolio-[decision].md`.

## When to combine with other skills

- **Before:** [`fpf-decision-criteria`](../fpf-decision-criteria/SKILL.md) declares the comparison axes.
- **Alongside:** [`fpf-evidence-gaps`](../fpf-evidence-gaps/SKILL.md) audits the prior-evidence column.
- **Upstream:** [`fpf-sota-pack`](../fpf-sota-pack/SKILL.md) builds the harvest from which this portfolio is drawn.

## Anti-patterns

- **One candidate, no alternatives.** Premature convergence. Force at least three.
- **Alternatives that are minor variants of the primary.** Diversity ≠ permutation of one choice.
- **No sunset criteria.** "We'll see how it goes" is not lawful.
- **A leaderboard ranking as the comparison.** Vector-valued, per-characteristic. Always.
- **Treating sequential commitment as a portfolio.** A pipeline like Mode 1 → Mode 2 → Mode 3 is a development sequence, not a selection portfolio. Label it correctly.
