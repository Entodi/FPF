# FPF Entry Families — Choosing Your Starting Point

Choose the entry by what you are really trying to decide, stabilize, or publish — not by document order. The router skill `fpf` uses this table to dispatch to specialists.

| # | Entry family | Use when… | Stabilizing result | Specialist skills |
|---|---|---|---|---|
| 1 | **Project alignment** | Responsibilities, working method, plans, and what actually happened are being mixed | Clean separation of responsibility/method/plan/work plus a first worksheet, alignment frame, or term sheet | `fpf-bounded-contexts`, `fpf-quartet`, `fpf-uts` |
| 2 | **Partly-said / language-state discovery** | A serious cue, concern, or emerging idea is too important to ignore but too early to present as a settled claim | A short preservation-and-burden note: what was noticed, how mature it is, what kind of pattern should inspect it next | `fpf-language-state` |
| 3 | **Boundary unpacking** | Contract, API, protocol, compliance, or SLA language mixes rules, gates, duties, and evidence in one blurred boundary story | A Claim Register or routed atomic claim set | `fpf-claim-register` |
| 4 | **Lawful comparison / selection / selected-set publication** | You need to compare alternatives honestly, keep a disciplined shortlist live, or publish a selected set without hiding the comparison logic | Declared characteristics, a comparison frame, candidate-pool policy, selected-set publication, or a lawful local decision home | `fpf-decision-criteria`, `fpf-portfolio`, `fpf-evidence-gaps` |
| 5 | **Generator / state-of-the-art / portfolio kit** | Your first deliverable is a reusable search, harvest, generator, or portfolio scaffold — not a one-off recommendation | A reusable kit naming scope, schools of thought, variants, and shortlist-ready outputs | `fpf-sota-pack`, `fpf-portfolio` |
| 6 | **Same-entity rewrite / explanation / comparative reading** | The job is to restate, explain, re-render, repair, or compare something already written without quietly changing what it is about | A rewrite, explanation note, repair note, or bounded comparison note that keeps the object of talk stable | `fpf-rewrite`, `fpf-name-card` |

## Detection heuristics for the router

| User says… | Likely entry | Skill |
|---|---|---|
| "Help me structure this project" | 1 | `fpf-bounded-contexts` then `fpf-quartet` |
| "What does X mean across our teams?" / "Build a glossary" | 1 | `fpf-uts` |
| "We're confusing what we are with what we do" | 1 | `fpf-quartet` |
| "I have a hunch but it's not ready yet" | 2 | `fpf-language-state` |
| "Unpack this contract / API / SLA" | 3 | `fpf-claim-register` |
| "Compare these options" / "Which architecture should we pick?" | 4 | `fpf-decision-criteria` then `fpf-portfolio` |
| "What evidence do we lack before committing?" | 4 | `fpf-evidence-gaps` |
| "Survey the field" / "State of the art for X" | 5 | `fpf-sota-pack` |
| "Rewrite this without changing the meaning" | 6 | `fpf-rewrite` |
| "We need a better name for this role / artifact" | 6 | `fpf-name-card` |

## When a session crosses families

A real session usually touches several entries. The order that tends to work:

```
bounded-contexts → quartet → uts → decision-criteria → portfolio → evidence-gaps
```

…with `language-state` and `name-card` available at any point, and `rewrite` reserved for publication-time.

If you don't know where to start, ask the user one question: *"What are you trying to decide, stabilize, or publish?"* Their answer maps to one of the six entries.

## What to skip

- Don't run the whole sequence on a small task. Pick one or two entries.
- Don't paste internal FPF pattern IDs (A.1.1, A.6, F.17) into a deliverable that will be read by managers or community partners. Translate to plain language; keep IDs in working notes only.
