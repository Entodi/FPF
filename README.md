# FPF — First Principles Framework as Claude Skills

> Operating system for thought, packaged as 13 Claude skills.

This repository converts Anatoly Levenchuk's [**First Principles Framework**](https://github.com/ailev/FPF) (April 2026) into a Claude Code plugin. Each FPF entry family becomes a callable skill that produces a durable, reviewable artifact rather than a one-off answer.

## What it is

Twelve specialist skills plus one router and one end-to-end pipeline:

| Skill | Produces |
|---|---|
| [`fpf`](plugins/fpf/skills/fpf/SKILL.md) | Router — detects intent and dispatches |
| [`fpf-pipeline`](plugins/fpf/skills/fpf-pipeline/SKILL.md) | End-to-end project alignment (six artifacts + overview) |
| [`fpf-bounded-contexts`](plugins/fpf/skills/fpf-bounded-contexts/SKILL.md) | Bounded context map + cross-context bridges |
| [`fpf-quartet`](plugins/fpf/skills/fpf-quartet/SKILL.md) | Transformer Quartet (System / Role / MethodDescription / Method / Work) |
| [`fpf-decision-criteria`](plugins/fpf/skills/fpf-decision-criteria/SKILL.md) | Declared characteristics + CN-frame |
| [`fpf-portfolio`](plugins/fpf/skills/fpf-portfolio/SKILL.md) | Alternative portfolio with explore/exploit policy |
| [`fpf-evidence-gaps`](plugins/fpf/skills/fpf-evidence-gaps/SKILL.md) | F-G-R audit, decay risks, epistemic debt |
| [`fpf-uts`](plugins/fpf/skills/fpf-uts/SKILL.md) | Unified Term Sheet across contexts |
| [`fpf-claim-register`](plugins/fpf/skills/fpf-claim-register/SKILL.md) | Atomic claims from contract / API / SLA / policy text |
| [`fpf-language-state`](plugins/fpf/skills/fpf-language-state/SKILL.md) | Partly-said preservation note |
| [`fpf-rewrite`](plugins/fpf/skills/fpf-rewrite/SKILL.md) | Same-entity rewrite + audit log |
| [`fpf-name-card`](plugins/fpf/skills/fpf-name-card/SKILL.md) | Deliberate rename with Pareto-front rationale |
| [`fpf-sota-pack`](plugins/fpf/skills/fpf-sota-pack/SKILL.md) | TraditionCards + OperatorCards + portfolio scaffold |

## Repository layout

```
FPF/
  README.md                 ← you are here
  FPF-Spec.md               ← preserved upstream specification (~6 MB)
  .claude-plugin/
    marketplace.json        ← plugin manifest
  plugins/fpf/skills/       ← 13 skills, each with SKILL.md
    fpf/references/         ← shared kernel.md, entry-families.md,
                              pattern-glossary.md, output-templates.md
```

## Choosing your first skill

The six FPF entry families map to skills:

| If you are trying to… | Start with |
|---|---|
| Structure a new project end-to-end | [`fpf-pipeline`](plugins/fpf/skills/fpf-pipeline/SKILL.md) |
| Map who owns which vocabulary | [`fpf-bounded-contexts`](plugins/fpf/skills/fpf-bounded-contexts/SKILL.md) |
| Separate what you are from what you do | [`fpf-quartet`](plugins/fpf/skills/fpf-quartet/SKILL.md) |
| Stabilise vocabulary that's drifting | [`fpf-uts`](plugins/fpf/skills/fpf-uts/SKILL.md) |
| Compare options honestly | [`fpf-decision-criteria`](plugins/fpf/skills/fpf-decision-criteria/SKILL.md) + [`fpf-portfolio`](plugins/fpf/skills/fpf-portfolio/SKILL.md) |
| Audit what evidence you lack | [`fpf-evidence-gaps`](plugins/fpf/skills/fpf-evidence-gaps/SKILL.md) |
| Unpack a contract / API / SLA | [`fpf-claim-register`](plugins/fpf/skills/fpf-claim-register/SKILL.md) |
| Preserve an early hunch | [`fpf-language-state`](plugins/fpf/skills/fpf-language-state/SKILL.md) |
| Rewrite something for a new audience | [`fpf-rewrite`](plugins/fpf/skills/fpf-rewrite/SKILL.md) |
| Find a better name | [`fpf-name-card`](plugins/fpf/skills/fpf-name-card/SKILL.md) |
| Survey a fast-moving field | [`fpf-sota-pack`](plugins/fpf/skills/fpf-sota-pack/SKILL.md) |

If you are unsure: start with [`fpf`](plugins/fpf/skills/fpf/SKILL.md) — the router asks one question and dispatches.

## When FPF earns its keep

Use these skills when several of these are true:

- work is split across specialised people, teams, or AI agents;
- the real-world oracle is delayed, noisy, expensive, or risky;
- different audiences need aligned outputs from the same underlying work;
- trade-offs between speed, quality, risk, novelty, and compliance must be explicit, not hidden in one opaque score;
- existing categories are breaking down and you need to grow new concepts from first principles.

## When FPF is overkill

- the task is small;
- vocabulary is already stable;
- feedback is fast and cheap;
- the cost of semantic drift is low;
- you mainly need a quick answer, not a reusable reasoning form.

For small, fast-feedback work, plain prompts beat FPF. The discipline costs time; spend it where it pays off.

## Relationship to the upstream FPF

This is a packaging conversion, not a re-authoring. The normative kernel — patterns, definitions, review rules — comes from `FPF-Spec.md` (preserved at the repo root) and Levenchuk's upstream repository. Each skill cites the FPF pattern IDs it instantiates so a reader can drill into the spec for full context.

What this conversion adds:

- **Skill-shaped entry points** — one callable unit per durable artifact.
- **Shared references** — kernel.md, entry-families.md, pattern-glossary.md, output-templates.md.
- **A pipeline** — chains the project-alignment artifacts in a deterministic order.

What this conversion does **not** change:

- The seven core ideas, F-G-R structure, transformer quartet, UTS discipline, bridge rule.
- The pattern IDs (A.1.1, A.6, B.3, F.17, …) — they remain the canonical addresses.
- Levenchuk's authorship of the framework.

## Citation

If you use FPF, please cite:

```
Levenchuk, Anatoly. First Principles Framework (FPF).
GitHub repository: https://github.com/ailev/FPF
```

## Upstream

The normative framework is maintained at https://github.com/ailev/FPF. This skill-set fork lives at https://github.com/Entodi/FPF.

## Status

Eternal alpha — already useful, still evolving. The skills are stable enough to run on real projects; the underlying FPF is itself versioned and refines its patterns over time.
