---
name: fpf-pipeline
description: >
  End-to-end FPF analysis pipeline. Takes a source artifact (grant, design
  doc, charter, RFP, spec) and runs it through the chain
  bounded-contexts → quartet → uts → decision-criteria → portfolio →
  evidence-gaps, producing a multi-file analysis like the canonical ASPIRE
  example. Triggers on "run FPF on this," "full FPF analysis," "FPF
  pipeline," "give me the full pass," "FPF this project," or when the user
  wants a complete project-alignment artifact set rather than one piece.
argument-hint: "[source-path] [output-dir]"
---

# FPF — Analysis Pipeline

Apply FPF entry family **1 (Project alignment)** as a chained workflow. The pipeline produces seven interlinked artifacts that together stabilize a project's vocabulary, structure, decisions, alternatives, and evidence posture.

## Inputs

The pipeline takes:

- **`$ARGUMENTS[0]`** — path to the source artifact (PDF, markdown, doc, or set of docs). If absent, ask for it.
- **`$ARGUMENTS[1]`** — output directory (default: `<source-name>-fpf/`).
- Optional context: project name, audience for the deliverables, scope limits.

If the source is a multi-file repo, ask the user to identify the canonical "what is this project" document(s) before proceeding.

## Stage 0: Preflight

Before running the chain:

1. Read the source. Confirm scope and time-budget with the user (a full pipeline on a 30-page grant is ~6 artifacts, ~30–60 minutes of work).
2. Decide whether to run **the full chain** or a **partial chain**. Partial chains are common — for instance:
   - "Just contexts + UTS" for vocabulary work.
   - "Just decisions + portfolio + evidence" for a pre-commitment review.
   - "Full chain" for project kickoff or onboarding documentation.
3. Confirm with the user before running more than two stages back-to-back.

## The Chain

| Stage | Skill | Output file | Reads from |
|---|---|---|---|
| 1 | [`fpf-bounded-contexts`](../fpf-bounded-contexts/SKILL.md) | `01-bounded-contexts.md` | source |
| 2 | [`fpf-quartet`](../fpf-quartet/SKILL.md) | `02-transformer-quartet.md` | source + 01 |
| 3 | [`fpf-uts`](../fpf-uts/SKILL.md) | `06-terminology.md` | source + 01 |
| 4 | [`fpf-decision-criteria`](../fpf-decision-criteria/SKILL.md) | `03-decision-criteria.md` | source + 01 + 02 |
| 5 | [`fpf-portfolio`](../fpf-portfolio/SKILL.md) | `04-alternative-portfolio.md` | source + 03 |
| 6 | [`fpf-evidence-gaps`](../fpf-evidence-gaps/SKILL.md) | `05-evidence-gaps.md` | source + 02 + 03 + 04 |
| 0 | (overview, written last) | `00-overview.md` | the six above |

The numbering matches the canonical ASPIRE example.

### Why this order

- **Bounded contexts first** — every later stage depends on knowing which vocabularies exist.
- **Quartet second** — separating system / role / method / work uses the contexts but is independent of vocabulary stabilization.
- **UTS third (numbered 06 for output)** — needs both contexts and quartet to stabilize cross-context terms; written third because later artifacts reference it.
- **Decision criteria fourth** — declarations of characteristics live inside contexts and refer to systems / methods named in the quartet.
- **Portfolio fifth** — alternatives are framed against declared criteria.
- **Evidence gaps sixth** — audits the prior-evidence column from 03 / 04, the method validity from 02, and any quartet alignment issues.
- **Overview last** — written after the artifacts exist; it summarises what the analysis found, not what it set out to find.

## Stage 1 — Run `fpf-bounded-contexts`

Dispatch to the specialist. Output: `<output-dir>/01-bounded-contexts.md`.

After Stage 1, **stop and confirm** with the user before proceeding. The contexts identified shape every later stage; an incorrect context map costs more to fix later.

## Stage 2 — Run `fpf-quartet`

Reads the source plus `01-bounded-contexts.md`. Output: `<output-dir>/02-transformer-quartet.md`.

After Stage 2, **stop and confirm**. Alignment issues found here often warrant an explicit conversation before continuing.

## Stage 3 — Run `fpf-uts`

Reads the source plus `01-bounded-contexts.md`. Output: `<output-dir>/06-terminology.md` (the high number reflects the canonical ordering — UTS is published last in the artifact set even though it stabilises vocabulary used by 03 / 04 / 05).

## Stage 4 — Run `fpf-decision-criteria`

Reads the source plus `01-bounded-contexts.md` + `02-transformer-quartet.md`. Output: `<output-dir>/03-decision-criteria.md`.

Identify the live decisions in the source (selection points where alternatives matter), then run the criteria skill *per decision*, batching results into one file with one section per decision.

## Stage 5 — Run `fpf-portfolio`

Reads `03-decision-criteria.md`. Output: `<output-dir>/04-alternative-portfolio.md`. Same per-decision batching as Stage 4.

## Stage 6 — Run `fpf-evidence-gaps`

Reads the source + `02-transformer-quartet.md` + `03-decision-criteria.md` + `04-alternative-portfolio.md`. Output: `<output-dir>/05-evidence-gaps.md`.

This stage typically finds the most surprising defects — Tier-3 claims that gate high-stakes decisions, decay risks the author hadn't named, epistemic debt that compounds across decisions.

## Stage 7 — Write the overview (`00-overview.md`)

Last, not first. The overview includes:

1. **Why FPF for [project]** — which of the six FPF earns-its-keep conditions apply.
2. **What FPF added** — table summarising the gap each of the six artifacts addresses.
3. **FPF entry points used** — list which entries (1–6) the analysis touched.
4. **How to use these files** — one sentence per audience (engineers, managers, ethicists, reviewers, etc.) pointing to the right starting artifact.

## Stop conditions

The pipeline stops if any stage produces:

- **No findings.** A bounded-context map with one context, or an evidence-gap audit with no Tier-2/3 claims, suggests the source isn't substantial enough for FPF — confirm with the user before continuing.
- **An unclear scope.** If a stage flags that the source mixes multiple distinct projects, surface this and re-scope before continuing.
- **A blocking Tier-3 finding.** If Stage 6 finds a critical evidence gap that gates a decision already being executed, surface it and pause.

## Output structure

```
<output-dir>/
  00-overview.md
  01-bounded-contexts.md
  02-transformer-quartet.md
  03-decision-criteria.md
  04-alternative-portfolio.md
  05-evidence-gaps.md
  06-terminology.md
```

Cross-link liberally between files. The reader should be able to start at any artifact and find the others.

## When to NOT run the full pipeline

- **Small task.** Pick one or two stages.
- **Vocabulary-only burden.** Run `fpf-bounded-contexts` + `fpf-uts` only.
- **Decision-only burden.** Run `fpf-decision-criteria` + `fpf-portfolio` + `fpf-evidence-gaps`.
- **Already have a context map.** Skip Stage 1; feed the existing map into Stage 2.

## Anti-patterns

- **Running all stages in one turn without checkpoints.** Every stage's output is an input to the next; mistakes cascade.
- **Treating the artifacts as one document.** They are six artifacts plus an overview; cross-linking, not concatenation.
- **Skipping the overview.** Written last, but essential — it is the only file most readers will open first.
- **Pasting pattern IDs into deliverables.** The artifacts cite IDs; the overview, audience-specific summaries, and any extracted findings should not.
