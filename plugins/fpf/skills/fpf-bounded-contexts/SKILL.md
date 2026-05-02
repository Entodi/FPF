---
name: fpf-bounded-contexts
description: >
  Map bounded contexts and cross-context bridges for a project. Identifies the
  local vocabularies, invariants, and responsibility boundaries of each
  specialised area, then names the bridges that translate terms across
  contexts. Triggers on "map bounded contexts," "what does X mean in our team,"
  "context map," "responsibility boundaries," "vocabulary differences," or "who
  owns which terms."
argument-hint: "[project-name]"
---

# FPF — Bounded Contexts

Apply FPF pattern **A.1.1 (U.BoundedContext)** and **F.9 (bridges)** to map a project's contexts. Read [`../fpf/references/kernel.md`](../fpf/references/kernel.md) for the underlying rule (local meaning, explicit translation).

## Principle

Terms live inside bounded contexts. Cross-context reuse is never obvious — it needs an explicit bridge. A project that uses one shared vocabulary across teams is hiding semantic drift, not preventing it.

## Step 1: Gather context

Ask only what you can't infer from the source material:
- Project name, scope, and main artifacts (grant, RFP, design doc, code repo).
- Teams and their leads.
- Documents that already define vocabulary (glossaries, ontologies).

If the user provides a source file (grant, spec, charter), read it and extract candidate contexts before asking.

## Step 2: Identify candidate contexts

Look for at least these classes; a real project usually has 5–8:

- **Domain** — the substantive subject matter (clinical care, finance, supply chain).
- **Technical / engineering** — the systems being built.
- **Normative / ethics / governance** — policies, oversight, community.
- **Platform / infrastructure** — data, compute, ops.
- **Administrative** — funder, contract, milestones.
- **Research** — ideas under investigation that aren't yet engineering.
- **Architecture** — composition decisions about the product / system shape.

A name appearing in two contexts with different meanings is a context boundary, not a synonym.

## Step 3: For each context, write the card

| Field | What goes here |
|---|---|
| BC-N name + class | "BC-3: Ethics & Co-Design (Normative Context)" |
| Owner | Role(s) accountable for this context |
| Local vocabulary | 4–8 terms with the meaning *inside this context* |
| Invariants | Non-negotiable rules (safety, IRB, reproducibility, etc.) |
| Boundary artifacts | What crosses out of this context to others |

A term that is *the same word* but means different things in two contexts MUST appear in both vocabulary lists with the local meaning.

## Step 4: Build the bridge table

For every term that appears in 2+ contexts, list the bridge:

| Bridge | From → To | Term at risk | Bridge discipline |
|---|---|---|---|
| BR-1 | BC-2 ↔ BC-1 | "interpretability" | ML prototype activation ≠ clinical explainability. Bridge: rubric mapping ProtoSeqNet outputs to clinical narratives via clinician evaluation. |

A bridge without a discipline (rule for how the term translates) is a defect. Either declare the rule, or merge the contexts.

## Step 5: List semantic drift risks

Order terms by drift risk (number of distinct senses × stakes). Top 3–5 go into the deliverable as a "watch list" for the eventual UTS.

## Step 6: Produce the artifact

Use the **Bounded Context Map** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). Save as `bounded-contexts.md` (or whatever the user's pipeline expects).

## Anti-patterns

- **One global vocabulary for the whole project.** That's not FPF; it's wishful thinking.
- **Listing contexts without owners.** A context with no owner has no boundary discipline.
- **Listing bridges without translation rules.** "We'll figure it out" is not a bridge.
- **Treating funding / contract language as the canonical vocabulary.** It's one context (BC-Admin), not the substrate.
- **Pasting pattern IDs (A.1.1, F.9) into deliverables for non-FPF readers.** Strip them.
