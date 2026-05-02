---
name: fpf-evidence-gaps
description: >
  Audit a project's claims against F-G-R (Formality, Scope, Reliability),
  bucket them into evidence tiers, surface critical gaps that must close
  before commitment, and register evidence decay risk and epistemic debt.
  Triggers on "evidence gaps," "what don't we know," "F-G-R," "trust
  calculus," "assurance audit," "epistemic debt," or "what's our weakest
  claim."
argument-hint: "[project-name]"
---

# FPF — Evidence Gaps

Apply FPF patterns **B.3 (Trust & Assurance Calculus, F-G-R)**, **A.10 (Evidence Graph Referring)**, **B.3.3 (assurance levels)**, **B.3.4 (evidence decay & epistemic debt)**, and **C.16 (Measurement & metrics characterization)**.

## Principle

Every claim deserves an F-G-R label:

- **F (Formality)** — how rigorously the claim is stated. 0 = aspirational handwave; 8 = formal proof.
- **G (Scope)** — where the claim applies. `aspirational` < `analogical` < `general` < `domain-specific` < `our-data`.
- **R (Reliability)** — what evidence supports it. `none` < `nascent` < `lab` < `published` < `operational` < `community-validated`.

Bare claims that gate high-stakes decisions are a defect. Pre-publication of an evidence-gap list is the FPF discipline that pushes mistakes left.

## Step 1: Inventory claims

Extract claims from the source material (grant, design doc, charter). For each, capture:
- The claim itself (one sentence).
- The evidence cited (or its absence).
- The F-G-R label.

Aim for 10–25 claims per project. Fewer means under-scrutiny; more means the granularity is wrong.

## Step 2: Tier the claims

| Tier | Threshold | Treat as |
|---|---|---|
| Tier 1 | F≥5, G=specific, R=published or operational | Reliable for planning |
| Tier 2 | F=3-5, G=narrow / analogical, R=lab or analogical | Needs validation in our context before commitment |
| Tier 3 | F<3, G=aspirational, R=none or claimed-only | High assurance burden — cannot gate high-stakes decisions |

Each tier becomes a table:

| Claim | Evidence | F-G-R | Gap (Tier 2 & 3 only) |
|---|---|---|---|

## Step 3: Critical gap list

For each Tier-2 or Tier-3 claim that gates a high-stakes decision, write a gap card:

```
### EG-N: [Title]
**What we don't know:**
**Why it matters:**
**Evidence needed:**
**When (gate / milestone):**
**FPF pattern:** [B.5.1 / B.3.3 / C.16 / etc.]
```

Aim for 3–7 critical gaps. More than 7 means the project should not have entered execution.

## Step 4: Evidence decay (B.3.4)

| Evidence | Age | Decay risk |
|---|---|---|

Decay risk is high for: leaderboard snapshots, vendor positions, market-rate estimates, unreplicated single-paper claims. Low for: foundational results, well-established standards, operational metrics from your own systems.

A claim with high decay risk needs a refresh policy — the date by which it must be re-checked or retired.

## Step 5: Epistemic debt register

Epistemic debt = the gap between what is claimed and what is evidenced, compounding as downstream decisions inherit the unevidenced premise.

| Debt item | Interest rate | Compounding risk |
|---|---|---|

Interest rate is high when many downstream claims inherit the assumption. Compounding risk is high when the assumption gates a path that's expensive to back out of.

## Step 6: Produce the artifact

Use the **Evidence Gap List** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). Save as `evidence-gaps.md`.

## When to combine with other skills

- **Upstream:** [`fpf-decision-criteria`](../fpf-decision-criteria/SKILL.md) and [`fpf-portfolio`](../fpf-portfolio/SKILL.md) — many gaps live in the "Prior evidence" column.
- **Pairs with:** [`fpf-quartet`](../fpf-quartet/SKILL.md) — MethodDescriptions without evidence are a frequent Tier-3 source.

## Anti-patterns

- **Listing only Tier-1 claims.** That's a credentials page, not an evidence audit.
- **Citing analogical evidence (X works in NLP, so it works for us) without flagging the gap.** That's Tier-2 by definition.
- **Treating prior work in adjacent domains as our-context evidence.** PPG ≠ ECG ≠ ABP, even though all are physiological signals.
- **Skipping the decay table.** A leaderboard snapshot from six months ago is not current evidence.
- **No critical-gap list.** If you can't name 3 things you'd want evidence on before committing, you're not auditing.
