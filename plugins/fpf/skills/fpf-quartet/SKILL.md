---
name: fpf-quartet
description: >
  Apply the Transformer Quartet to separate a project's Systems / Roles /
  MethodDescriptions / Methods / Work. Surfaces the category errors that
  cascade into planning failures (treating a system as a method, a role as a
  work record, a description as an enacted method). Triggers on "transformer
  quartet," "system vs method," "what is vs what we do," "separate roles and
  work," "method description," or "role overload."
argument-hint: "[project-name]"
---

# FPF — Transformer Quartet

Apply FPF patterns **A.3 (Transformer Constitution)**, **A.7 (Strict Distinction)**, and **A.15 (Role-Method-Work Alignment)**. The kernel rule: descriptions, capabilities, plans, and actual occurrences are not the same thing.

## Principle

Most planning documents mix five things:

1. **Systems** — what exists, what is being built (a model, a service, a dataset, an org).
2. **Roles** — who or what bears responsibility (a TransformerRole carried by a system or person).
3. **MethodDescriptions** — documented procedures, protocols, architectures (the blueprint).
4. **Methods** — the description actually enacted (how work is in fact performed).
5. **Work** — records of what happened (logs, results, artifacts).

A grant that says "ASPIRE will demonstrate ethical multi-agent care" mixes a system claim, a method description, and a work prediction. Quartet decomposition makes the parts visible — and exposes the gaps.

## Step 1: Gather inputs

Ask for or extract:
- The project's main systems (named entities being built or used).
- The named roles (PI, leads, working groups, contributors).
- Documented procedures (SOPs, protocols, architectures).
- Prior work records, if any (publications, datasets, infrastructure already in place).

A bounded-context map ([`fpf-bounded-contexts`](../fpf-bounded-contexts/SKILL.md)) makes this faster — each system / role lives in some BC.

## Step 2: Build the five tables

### 2.1 Systems

| System | Kind | Bounded Context | Status |
|---|---|---|---|

Kinds: cyber system, ML model, software component, platform (external), infrastructure, data asset, organisation. **Status:** being designed / in development / operational / external dependency.

A project named as "one system" is almost always 3–7 systems. Force the split.

### 2.2 Roles

| Role Holder | TransformerRole | Context | Responsibility Boundary |
|---|---|---|---|

A role holder may be a person, a committee, or a system. **Flag role overload** — the same holder bearing roles in multiple bounded contexts is a structural risk (A.7).

### 2.3 MethodDescriptions

| MethodDescription | Owner | Status | Evidence of Validity |
|---|---|---|---|

Status: published / described in this document / novel / inherited from prior art. **Evidence of validity is the critical column** — a novel method description with no validation evidence carries higher assurance burden (B.3) and cannot be planned as a reliable method.

### 2.4 Methods (enacted)

| MethodDescription | Enactment Risk | Evidence Needed |
|---|---|---|

A MethodDescription that has never been enacted is *not yet a Method*. The gap between description and enacted method is the primary execution risk on most projects.

### 2.5 Work (records)

- **Prior work records** carried forward (what's already done).
- **Work records to be generated** (what evidence will be produced for each KR / aim / milestone).

Without explicit work records, KR scores have no evidence carriers (A.10).

## Step 3: Find alignment issues

Walk the tables and flag:

- **System ≠ MethodDescription confusion.** A name used for both the artifact and the blueprint.
- **Role overload.** One holder, multiple contexts, no delegation.
- **MethodDescription without evidence.** Novel methods treated as reliable in the plan.
- **Work evidence not specified.** KR targets without evidence carriers.
- **Work-only plans.** A plan that lists deliverables but no methods — magical thinking.

Each issue gets a short paragraph: what it is, why it matters, recommended fix.

## Step 4: Produce the artifact

Use the **Transformer Quartet** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). Save as `transformer-quartet.md`.

## Anti-patterns

- **Letting "the project" stand for a system.** Most projects are several systems plus several method descriptions.
- **Conflating PI with project director with data coordinator.** Each is a distinct TransformerRole; the same person may hold several, but the holdings should be explicit.
- **Treating a published architecture as enacted method.** A wave2vec paper does not validate "wave2vec on our data."
- **Ignoring work evidence.** A score without an evidence carrier is hearsay.
