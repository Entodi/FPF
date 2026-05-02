# FPF Pattern Glossary — Cheat Sheet

A compact map of the FPF pattern IDs each skill cites. For full normative text, see `FPF-Spec.md` at the repo root.

## Part A — Kernel architecture

| ID | Name | Used by skill |
|---|---|---|
| A.0 | Problem framing | (router) |
| A.1.1 | U.BoundedContext — the semantic frame | `fpf-bounded-contexts` |
| A.2.4 | Evidence role | `fpf-evidence-gaps` |
| A.3 | Transformer Constitution (System / TransformerRole / MethodDescription / Method / Work) | `fpf-quartet` |
| A.6 | Boundary discipline | `fpf-claim-register` |
| A.6.B / A.6.C | Boundary breakdown / boundary classes | `fpf-claim-register` |
| A.6.RSIG | Description-shape signature | `fpf-claim-register` |
| A.6.P / A.6.Q / A.6.A | Property / quality / action splits | `fpf-claim-register` |
| A.6.3.CR / A.6.3.RT | Comparative reading / re-render | `fpf-rewrite` |
| A.7 | Strict distinction (Object ≠ Description ≠ Role ≠ Work) | `fpf-quartet` |
| A.10 | Evidence Graph Referring | `fpf-evidence-gaps` |
| A.15 / A.15.1–3 | Role-Method-Work alignment | `fpf-quartet` |
| A.16 / A.16.1 / A.16.2 | Language-state markers | `fpf-language-state` |
| A.17 | Canonical Characteristic | `fpf-decision-criteria` |
| A.18 | CSLC-Kernel (Characteristic / Scale / Level / Coordinate) | `fpf-decision-criteria` |
| A.19 | CharacteristicSpace | `fpf-decision-criteria` |
| A.19.CN | CN-frame (comparability + normalization) | `fpf-decision-criteria`, `fpf-portfolio` |
| A.19.CPM | Vector-valued comparison | `fpf-decision-criteria` |
| A.19.SelectorMechanism | Selection kernel | `fpf-portfolio` |

## Part B — Trans-disciplinary reasoning

| ID | Name | Used by skill |
|---|---|---|
| B.3 | Trust & Assurance Calculus (F-G-R) | `fpf-evidence-gaps` |
| B.3.3 | Assurance levels (LA, LB, …) | `fpf-evidence-gaps` |
| B.3.4 | Evidence decay & epistemic debt | `fpf-evidence-gaps` |
| B.4.1 | Pre-abductive routing | `fpf-language-state` |
| B.5.1 | Explore → Shape → Evidence → Operate | `fpf-decision-criteria`, `fpf-portfolio` |
| B.5.2.0 | Endpoint patterns | `fpf-language-state` |
| B.5.2.1 | Creative search | `fpf-sota-pack` |

## Part C — Kernel extensions

| ID | Name | Used by skill |
|---|---|---|
| C.2.2a | Partly-said cue | `fpf-language-state` |
| C.2.LS / C.2.4–7 | Language-state working forms | `fpf-language-state` |
| C.11 | Local choice | `fpf-portfolio` |
| C.16 | Measurement & metrics characterization | `fpf-evidence-gaps` |
| C.17 | Creative search (NQD) | `fpf-sota-pack` |
| C.18 | NQD-CAL (open-ended search) | `fpf-portfolio`, `fpf-sota-pack` |
| C.19 | Explore-Exploit Governor | `fpf-portfolio`, `fpf-sota-pack` |
| C.24 | Call-planning / checkpoint-return | `fpf-portfolio` |
| C.25 | Quality bundle (Q-bundle) | `fpf-decision-criteria` |

## Part E — FPF Constitution & authoring

| ID | Name | Used by skill |
|---|---|---|
| E.1–E.2 | Vision / pillars | (router) |
| E.8 | Pattern authoring | (meta) |
| E.9 | DRR (Decision Rationale Record) | `fpf-decision-criteria`, `fpf-portfolio` |
| E.10 | Lexical law (Tech / Plain registers) | `fpf-uts`, `fpf-name-card` |
| E.17.EFP / E.17.ID.CR / E.17.AUD.LHR / E.17.AUD.OOTD | Same-entity rewrite & audit forms | `fpf-rewrite` |
| E.19 | Pattern review | (meta) |
| E.TGA / TEVB | Transduction-graph / route from principles to work | (router) |

## Part F — Unification suite

| ID | Name | Used by skill |
|---|---|---|
| F.9 | Bridge discipline | `fpf-bounded-contexts` |
| F.11 | Method / work vocabulary alignment | `fpf-bounded-contexts`, `fpf-quartet` |
| F.17 | UTS — Unified Term Sheet | `fpf-uts` |
| F.18 | Name Card discipline | `fpf-name-card` |

## Part G — State-of-the-art kit

| ID | Name | Used by skill |
|---|---|---|
| G.0 | CG-Spec / CG-Frame authoring | `fpf-portfolio`, `fpf-sota-pack` |
| G.1 | Scope & schools of thought | `fpf-sota-pack` |
| G.2 | Harvest & TraditionCards | `fpf-sota-pack` |
| G.4 | OperatorCards | `fpf-sota-pack` |
| G.5 | Selector / dispatcher | `fpf-portfolio`, `fpf-sota-pack` |

## Reading conventions

- **Short pattern IDs** (e.g., `A.6`) refer to the full FPF specification.
- **Skills cite IDs in their frontmatter and methodology sections** so a reader can drill down via `FPF-Spec.md`.
- **Plain-language outputs should not include pattern IDs.** Keep IDs in working notes; strip them from anything an audience outside FPF will read.
