---
name: fpf-uts
description: >
  Build a Unified Term Sheet (UTS) that stabilises vocabulary across bounded
  contexts. Distinguishes Tech vs. Plain names, maps SenseCells per context,
  flags risky aliases, and resolves high-risk polysemy ("agent," "model,"
  "interpretability," "fairness"). Triggers on "unified term sheet," "UTS,"
  "vocabulary," "glossary," "term mapping," "name conflicts," "polysemy," or
  "what does X mean across teams."
argument-hint: "[domain]"
---

# FPF — Unified Term Sheet (UTS)

Apply FPF patterns **F.17 (UTS discipline)**, **F.18 (Name Card discipline)**, and **E.10 (Lexical law: Tech / Plain registers)**.

## Principle

A UTS is the canonical, multi-context glossary. It distinguishes:

- **Tech names** — precise, context-specific, used in technical documents.
- **Plain names** — accessible, audience-appropriate, used in non-technical communication.
- **SenseCells** — the meaning of a term *inside* one bounded context.

The discipline is not "one word, one definition" — it is "one word, declared senses across contexts, with bridges where senses differ."

A UTS pairs naturally with [`fpf-bounded-contexts`](../fpf-bounded-contexts/SKILL.md): the contexts give the columns, the UTS fills the cells.

## Step 1: Inputs

Gather:
- The bounded contexts (or run `fpf-bounded-contexts` first).
- Existing glossaries / data dictionaries / ontologies.
- The drift-risk watchlist from the bounded-context map.

## Step 2: Term selection

Include in the UTS:
- Every term on the drift-risk watchlist.
- Every term that appears in 2+ contexts with possibly different meanings.
- Every term that is jargon in one context and plain in another.
- Every term used in a publicly-published artifact (paper, grant, contract, marketing).

Aim for 10–20 rows for a moderate project. More rows is fine if the project is large; fewer means the UTS is incomplete.

## Step 3: Build the core term sheet

| # | Plain Name | Tech Name | BC-1 | BC-2 | BC-3 | … | Risky Aliases |
|---|---|---|---|---|---|---|---|

- Each BC column is the SenseCell — the meaning *in that context*. Use "N/A" when the term doesn't apply in a context.
- **Risky aliases** lists names to *avoid*: synonyms, brand names, overloaded words. Include the reason.

## Step 4: Resolve high-risk polysemy

For terms with 3+ distinct senses, write a polysemy block:

```
## High-Risk Polysemy: "[Term]"

| Sense | Context | Referent | How it's measured / used |

**Recommendation:** [naming rule for this term going forward]
```

Common polysemy in mixed projects: *agent*, *model*, *foundation model*, *interpretability*, *fairness*, *quality*, *performance*, *training*, *modality*, *prototype*.

## Step 5: Naming discipline for publications

| Audience | Register | Example |
|---|---|---|

The point: when you write for a journal vs. a community workshop vs. a regulator vs. an internal architecture review, you swap registers — not meaning. The UTS makes the swap rule explicit.

## Step 6: Produce the artifact

Use the **Unified Term Sheet** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). Save as `uts.md` or `terminology.md`.

## When to combine with other skills

- **After:** [`fpf-bounded-contexts`](../fpf-bounded-contexts/SKILL.md) — contexts are the columns.
- **Pairs with:** [`fpf-name-card`](../fpf-name-card/SKILL.md) — when a single ambiguous name needs a deliberate rename.
- **Feeds:** every other skill, since they all use terms that should appear here.

## Anti-patterns

- **One definition per term.** That's a dictionary, not a UTS.
- **Skipping risky aliases.** The UTS earns its keep by telling people what *not* to say.
- **Pasting in a vendor or framework's glossary as our UTS.** It's *one input*, in *one context*.
- **Calling everything a "model" without per-context senses.** "Model" is one of the worst polysemy offenders in mixed AI / clinical / governance projects.
- **Updating the UTS once and never again.** Vocabulary drifts; the UTS needs a refresh policy (cadence and trigger).
