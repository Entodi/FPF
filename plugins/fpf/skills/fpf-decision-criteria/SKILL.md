---
name: fpf-decision-criteria
description: >
  Declare characteristics, scales, polarity, and the CN-frame for a decision so
  alternatives can be compared lawfully. Surfaces undeclared comparison axes,
  hidden hard gates, and quality bundles ("interpretability," "fairness,"
  "robustness") that hide multiple distinct measurements. Triggers on "decision
  criteria," "characteristics," "comparison frame," "CN-frame," "how should we
  compare," "what should we measure," or "quality bundle."
argument-hint: "[decision-subject]"
---

# FPF — Decision Criteria

Apply FPF patterns **A.17 (Canonical Characteristic)**, **A.18 (CSLC-Kernel)**, **A.19 (CharacteristicSpace)**, **A.19.CN (CN-frame)**, **A.19.CPM (vector-valued comparison)**, and **C.25 (Quality bundle)**.

## Principle

Every comparison or selection should declare its characteristics explicitly: what is being measured, on what scale, with what polarity, under what comparability conditions. A decision that compares options on a single aggregate score (a leaderboard rank) is hiding the trade-offs.

## Step 1: Identify the decision

Ask:
- What is being chosen? (the **DecisionSubject**)
- Who is the decision-maker?
- When is the decision gate? Is the decision reversible?
- Are any characteristics already implied by stakeholders or contracts?

A project usually has 3–10 live decisions. Run this skill **per decision** — don't try to cover them all in one table.

## Step 2: Enumerate characteristics

For each candidate characteristic, fill the row:

| Characteristic | Scale | Polarity | Declared? |
|---|---|---|---|

- **Scale:** Nominal (categories), Ordinal (rank), Interval (distance, no zero), Ratio (true zero). State the levels explicitly: `Ordinal: abandoned / maintained / actively developed`.
- **Polarity:** higher preferred / lower preferred / target value / required (hard gate) / nominal (categorical match needed).
- **Declared?** Yes / No / Implicit. The undeclared ones are the FPF finding.

Aim for 5–10 characteristics per decision. Fewer means hidden axes; more means the decision is too broad and should be split.

## Step 3: Build the CN-frame (A.19.CN)

The Comparability + Normalization frame says how candidates are made commensurate:

- **Comparability mode:** same data / same compute / same evaluation protocol / same time horizon.
- **Normalization:** how scores are made comparable (min-max, z-score, percent of baseline, none).
- **Hard gates:** thresholds that disqualify a candidate before any soft comparison.
- **Evidence requirements:** which characteristics need stats (CIs, effect sizes, sample sizes) and which can be ordinal estimates.

A decision without a CN-frame is non-auditable: a reviewer cannot verify whether the same characteristics would yield the same selection.

## Step 4: Unpack quality bundles (C.25)

Words like *interpretability*, *fairness*, *robustness*, *trustworthiness*, *scalability* are quality bundles, not single characteristics. For each that appears, run the bundle test:

| Quality term | Declared? | Unpacked into characteristics? | Mechanism / measurement? |
|---|---|---|---|

If "fairness" is in the deliverable but not unpacked into a specific definition (demographic parity, equalised odds, calibration, …), flag it. The same word in two contexts hides different measurements.

## Step 5: Vector-valued comparison (A.19.CPM)

Reject single-aggregate-score comparisons unless the user has a documented reason. Default output is a per-characteristic comparison table; aggregation, if any, comes after — and shows weights.

## Step 6: Produce the artifact

Use the **Decision Criteria** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). Save as `decision-criteria.md`.

The artifact pairs naturally with [`fpf-portfolio`](../fpf-portfolio/SKILL.md) (which fills in candidates) and [`fpf-evidence-gaps`](../fpf-evidence-gaps/SKILL.md) (which audits the evidence column).

## Anti-patterns

- **One leaderboard score per option.** That's not lawful comparison; it's vibes.
- **Undeclared hard gates.** "Of course it must be open-source" — say so explicitly, with the disqualification rule.
- **Bundling "interpretability" without unpacking.** Run the C.25 test.
- **Picking characteristics after seeing the candidates.** That's confirmation, not selection.
- **Decay-blind characteristics.** A characteristic whose rank shifts monthly (e.g., LLM ChatBot Arena) needs an explicit refresh policy.
