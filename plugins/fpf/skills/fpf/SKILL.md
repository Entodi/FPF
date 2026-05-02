---
name: fpf
description: >
  Operating system for thought. Apply Anatoly Levenchuk's First Principles
  Framework (FPF) to structure a project, problem, or programme: bounded
  contexts, transformer quartet, decision criteria, alternative portfolios,
  evidence gaps, unified term sheets, claim registers, language-state notes,
  same-entity rewrites, name cards, and state-of-the-art packs. Triggers when
  the user mentions FPF, "first principles framework," "operating system for
  thought," asks to "structure my project," "map bounded contexts," "compare
  options lawfully," "find evidence gaps," or wants a durable reasoning artifact
  rather than a one-off answer.
argument-hint: "[entry-family|skill-name]"
---

# FPF — First Principles Framework

This skill is the router for FPF work. It detects the user's entry burden and dispatches to a specialist skill that produces a durable artifact. The non-negotiable rules in `references/kernel.md` apply to every mode.

## Detect the user's entry burden

| User intent | Entry family | Specialist |
|---|---|---|
| "Structure this project" / "Map who owns what vocabulary" | Project alignment | [`fpf-bounded-contexts`](../fpf-bounded-contexts/SKILL.md) |
| "Separate what we are from what we do" / "Role vs. method confusion" | Project alignment | [`fpf-quartet`](../fpf-quartet/SKILL.md) |
| "Build a glossary that survives across teams" | Project alignment | [`fpf-uts`](../fpf-uts/SKILL.md) |
| "I have a hunch but it's not ready as a claim" | Partly-said | [`fpf-language-state`](../fpf-language-state/SKILL.md) |
| "Unpack this contract / SLA / API" | Boundary unpacking | [`fpf-claim-register`](../fpf-claim-register/SKILL.md) |
| "Compare options honestly" / "What characteristics matter?" | Lawful comparison | [`fpf-decision-criteria`](../fpf-decision-criteria/SKILL.md) |
| "Build a portfolio of alternatives" / "Explore vs. exploit" | Lawful comparison | [`fpf-portfolio`](../fpf-portfolio/SKILL.md) |
| "What evidence are we missing?" / "F-G-R audit" | Lawful comparison / assurance | [`fpf-evidence-gaps`](../fpf-evidence-gaps/SKILL.md) |
| "Survey the field" / "State of the art for X" | Generator / SoTA kit | [`fpf-sota-pack`](../fpf-sota-pack/SKILL.md) |
| "Rewrite this without changing the meaning" | Same-entity rewrite | [`fpf-rewrite`](../fpf-rewrite/SKILL.md) |
| "Find a better name for this role / artifact" | Same-entity rewrite | [`fpf-name-card`](../fpf-name-card/SKILL.md) |

If the user typed `$ARGUMENTS` as one of `bounded-contexts | quartet | uts | language-state | claim-register | decision-criteria | portfolio | evidence-gaps | sota-pack | rewrite | name-card`, dispatch directly to that specialist.

If intent is ambiguous, ask one question: **"What are you trying to decide, stabilize, or publish?"** The answer maps to one of the six entries.

## Foundation: rules that apply in every mode

Read [`references/kernel.md`](references/kernel.md) for the seven core ideas. The most often-violated:

- **Local meaning, explicit translation.** Don't assume a term means the same thing in two contexts. If it crosses a boundary, build a bridge.
- **Separate System / Role / MethodDescription / Method / Work.** A grant proposal that says "ASPIRE will…" is mixing all five. Break them apart before planning.
- **Trust has structure.** Every claim deserves an F-G-R label (Formality, Scope, Reliability). Bare claims that gate high-stakes decisions are a defect.
- **Keep search wide before selection.** A single-vendor decision with no portfolio is premature convergence.
- **Aligned outputs from one underlying body of reasoning.** Engineering, management, research, and assurance views should be projections of the same work — not independent documents.

See [`references/entry-families.md`](references/entry-families.md) for full dispatch logic and [`references/pattern-glossary.md`](references/pattern-glossary.md) for the FPF pattern IDs each specialist cites.

## Mode: full-pass project alignment

When the user says "run FPF on this project" or "give me the full pass," dispatch in this order:

1. **`fpf-bounded-contexts`** — what contexts exist, who owns each vocabulary
2. **`fpf-quartet`** — separate System / Role / MethodDescription / Method / Work
3. **`fpf-uts`** — stabilize the cross-context terms
4. **`fpf-decision-criteria`** — declare characteristics for the live decisions
5. **`fpf-portfolio`** — alternatives for each decision
6. **`fpf-evidence-gaps`** — F-G-R audit before commitment

Stop and confirm after each step — do not produce all six artifacts in one turn unless the user explicitly asks for a single batch.

## Mode: single-skill dispatch

If the user names a specific entry family or specialist, hand the work directly to that skill. Do not run extra entries unprompted.

## Output discipline

Every artifact this skill or its specialists produces should:

- Lead with the FPF pattern IDs it instantiates (so a reader can drill into `FPF-Spec.md`).
- Use tables for comparison-shaped content; reserve prose for framing and findings.
- **Distinguish declared vs. undeclared.** FPF's value is making the implicit visible.
- **Strip pattern IDs from any deliverable that will be read by a non-FPF audience.** Pattern IDs belong in working notes, not in board memos, grant text, or community materials.

See [`references/output-templates.md`](references/output-templates.md) for ready templates.

## What FPF will not do

- Think instead of you. Without good problem framing, FPF will produce well-structured nonsense — just better-organized than unstructured nonsense.
- Replace agile / waterfall / scrum / OKRs. FPF sits underneath those, supplying the reasoning artifacts they assume but rarely produce.
- Provide a single right answer. Most FPF outputs are a structured set of alternatives + a declared decision frame, not a recommendation.

## Anti-patterns

- Don't paste internal pattern IDs (A.6, F.17, B.3) into a deliverable for non-FPF readers.
- Don't run all six entry families on a small task. Pick one or two.
- Don't treat "ASPIRE" or any other named project as a single system. It is almost always several systems plus several method descriptions plus several work records.
- Don't accept a comparison that uses one aggregate score (a leaderboard rank). FPF requires vector-valued comparison across declared characteristics.
- Don't drop a candidate from a portfolio without a sunset criterion that was declared in advance.

## Citation

This skill set is a Claude-skills conversion of Anatoly Levenchuk's *First Principles Framework* (April 2026). Upstream: https://github.com/ailev/FPF
