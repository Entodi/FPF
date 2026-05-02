---
name: fpf-claim-register
description: >
  Unpack contract / API / SLA / protocol / policy text into atomic claims —
  rules, gates, duties, evidence — each routed to an owner with subject,
  trigger, and witness. Surfaces overloaded boundary language that hides
  category errors. Triggers on "unpack this contract," "claim register," "API
  has mixed obligations," "SLA review," "boundary discipline," "atomic
  claims," or "what is this clause actually saying."
argument-hint: "[boundary-document-path]"
---

# FPF — Claim Register

Apply FPF patterns **A.6 (Boundary discipline)**, **A.6.B / A.6.C (Boundary classes)**, **A.6.RSIG (Description-shape signature)**, and **A.6.P / A.6.Q / A.6.A (property / quality / action splits)**.

## Principle

Boundary documents (contracts, APIs, SLAs, protocols, compliance text, policies) routinely mix four atom types in one paragraph:

- **Rule** — a normative constraint (must / shall / may not).
- **Gate** — a conditional admission (if X, then allowed).
- **Duty** — an obligation borne by a named party.
- **Evidence** — a record or witness required to prove satisfaction.

Each atom has a different owner, different trigger, different cost. Mixing them produces ambiguous, unauditable boundary language. The Claim Register splits them apart.

## Step 1: Identify the source

Ask for or be handed:
- The text to unpack (clause, section, full document).
- Who owns the source (counterparty, regulator, internal team).
- What's at stake (compliance, money, safety, reputation).

If the source is a small clause, atomize directly. If it's a long document, scope first ("which sections?") before atomizing — a register should not exceed ~50 atoms in one pass.

## Step 2: Description-shape (A.6.RSIG)

Before atomising, ask: **what kind of description is this?**

| Description shape | Hallmarks | Typical atoms |
|---|---|---|
| Contract | Obligations between named parties | Duties + Rules + Evidence |
| SLA | Performance targets with consequences | Rules + Gates + Evidence |
| API spec | Interface contract | Rules (preconditions) + Duties (the call) + Evidence (return shape) |
| Protocol | Procedural rules | Sequenced Duties + Gates |
| Policy | Internal normative text | Rules + Duties |
| Compliance text | Regulator-facing | Rules + Evidence |

Naming the shape narrows the atom types you will encounter and makes overloaded text visible.

## Step 3: Atomize

For each phrase that carries normative weight, write a row:

| ID | Original phrase | Class (Rule / Gate / Duty / Evidence) | Owner | Subject | Trigger | Witness |
|---|---|---|---|---|---|---|

- **Owner** — who bears the atom.
- **Subject** — what (or whom) the atom applies to.
- **Trigger** — when the atom is active.
- **Witness** — what would show the atom was satisfied.

Witness is the column that most often exposes defects. A duty with no witness is unenforceable; a rule with no witness is unauditable.

## Step 4: Property / Quality / Action splits (A.6.P / A.6.Q / A.6.A)

When boundary text mixes a property ("the system has X"), a quality ("the response is fast"), and an action ("the agent does Y"), split them:

- **Property atoms (A.6.P)** — invariants of the system.
- **Quality atoms (A.6.Q)** — measurable characteristics, often tied to A.17 (run [`fpf-decision-criteria`](../fpf-decision-criteria/SKILL.md) for measurement structure).
- **Action atoms (A.6.A)** — events / verbs.

Each split atom gets its own row.

## Step 5: Routing

Once atomized, each claim routes to an owner:

| Claim ID | Route to | Why |
|---|---|---|

A claim with no route is an orphan and a defect — flag it. Common routes: the implementing team (for duties), QA / audit (for evidence), legal / compliance (for rules), product (for gates).

## Step 6: Produce the artifact

Use the **Claim Register** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). Save as `claim-register.md`.

## Anti-patterns

- **Atomizing without identifying description shape first.** You'll miss whole categories.
- **Treating one paragraph as one claim.** A "shall" sentence with three sub-clauses is three claims.
- **Skipping the witness column.** "We'll know it when we see it" is unauditable.
- **Routing every claim to "the team."** That's not routing.
- **Calling a quality atom a rule.** "The response is fast" is a Q-atom, not an R-atom; it needs a measurement, not a yes/no test.

## Notes

This skill is the FPF entry family **3 (Boundary unpacking)**. Use it whenever contract / API / SLA / compliance language is being read for execution — not just review. The register is the durable artifact; "I read the contract" is not.
