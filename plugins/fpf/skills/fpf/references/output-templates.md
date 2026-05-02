# FPF Output Templates

Common templates each specialist skill emits. Adapt freely; the structure matters more than the headings.

---

## Template: Bounded Context Map

```markdown
# Bounded Context Map for [Project]

**FPF Pattern:** A.1.1 — U.BoundedContext

## Identified Bounded Contexts

### BC-1: [Name] ([Domain / Technical / Normative / Platform / Admin / Research / Architecture])
**Owner:** [role/person]
**Local vocabulary:**
- "[Term]" = [meaning in this context]
- ...
**Invariants:**
- [non-negotiable rule]
**Boundary artifacts:** [what crosses out of this context]

### BC-2: ...

## Cross-Context Bridges

| Bridge | From → To | Term at Risk | Bridge Discipline |
|---|---|---|---|
| BR-1 | BC-X ↔ BC-Y | "[term]" | [explicit translation rule] |

## Semantic Drift Risks

1. **"[Term]"** — N senses across BC-A, BC-B, BC-C
```

---

## Template: Transformer Quartet

```markdown
# Transformer Quartet — [Project]

**FPF Patterns:** A.3, A.7, A.15

## 1. Systems
| System | Kind | Bounded Context | Status |

## 2. Roles
| Role Holder | TransformerRole | Context | Responsibility Boundary |

## 3. Method Descriptions
| MethodDescription | Owner | Status | Evidence of Validity |

## 4. Methods (Enacted)
| MethodDescription | Enactment Risk | Evidence Needed |

## 5. Work (Records)
- Prior work records: ...
- Records to be generated: ...

## Alignment Issues Found
### Issue 1: [System ≠ MethodDescription / Role overload / etc.]
```

---

## Template: Decision Criteria

```markdown
# Decision Criteria for [Decision]

**FPF Patterns:** A.17, A.18, A.19, A.19.CN

## Decision D0X: [Subject]
**DecisionSubject:** [what is being chosen]

| Characteristic | Scale | Polarity | Declared? |
|---|---|---|---|
| [name] | [Nominal/Ordinal/Interval/Ratio: levels] | [higher/lower/required] | [Yes/No/Implicit] |

**CN-frame:**
- Comparability mode: [same data / same compute / same protocol]
- Normalization: [how scores are made comparable]
- Hard gates: [disqualifying thresholds]
- Evidence requirements: [stats, CIs, effect sizes]

## Quality Bundles (C.25)
| Quality term | Declared? | Unpacked? | Mechanism? |
```

---

## Template: Alternative Portfolio

```markdown
# Portfolio for [Decision]

**FPF Patterns:** G.0, C.18, C.19, A.19.SelectorMechanism

**Status:** [Pre-selected / Open exploration / Sequential commitment]
**E/E-LOG Policy (C.19):** [Keep frontier / Narrow to subset / Sequential]

| Candidate | School of Thought | Key Mechanism | Prior Evidence |
|---|---|---|---|

**Lawful comparison requirements:**
- [same data / same compute / same evaluation]

**Selection mechanism:**
- Hard gates: ...
- Soft comparison: vector-valued

**Sunset line:** [when a candidate is dropped]
```

---

## Template: Evidence Gap List

```markdown
# Evidence Gap Analysis — [Project]

**FPF Patterns:** B.3 (F-G-R), A.10, B.3.4, C.16

## Tier 1: Strong Evidence (F≥5, G=specific, R=published)
| Claim | Evidence | F-G-R |

## Tier 2: Partial Evidence (F=3-5, G=narrow, R=lab/analogical)
| Claim | Evidence | F-G-R | Gap |

## Tier 3: Weak / No Evidence (F<3)
| Claim | Evidence | F-G-R | Gap |

## Critical Gaps to Close Before Commitment
### EG-1: [Title]
**What we don't know:**
**Why it matters:**
**Evidence needed:**
**When:**
**FPF pattern:** [B.5.1 / B.3.3 / C.16 / etc.]

## Evidence Decay Risks
| Evidence | Age | Decay Risk |

## Epistemic Debt Register
| Debt Item | Interest Rate | Compounding Risk |
```

---

## Template: Unified Term Sheet

```markdown
# Unified Term Sheet (UTS) — [Domain]

**FPF Patterns:** F.17, F.18, E.10

## Core Term Sheet

| # | Plain Name | Tech Name | BC-1 | BC-2 | BC-3 | Risky Aliases |
|---|---|---|---|---|---|---|

## High-Risk Polysemy: "[Term]"
| Sense | Referent | Context | Notes |

**Recommendation:** [naming rule for this term]

## Naming Discipline for Publications
| Audience | Register | Example |
```

---

## Template: Claim Register

```markdown
# Claim Register — [Boundary Document]

**FPF Patterns:** A.6, A.6.B, A.6.C, A.6.RSIG

## Atomic Claims

| ID | Original phrase | Class (Rule/Gate/Duty/Evidence) | Owner | Subject | Trigger | Witness |
|---|---|---|---|---|---|---|

## Description-Shape (A.6.RSIG)
- What kind of description is this? [contract / SLA / API / protocol / policy]
- What atoms appear? [property / quality / action]

## Routing
| Claim ID | Route to | Why |
```

---

## Template: Language-State Note

```markdown
# Language-State Note — [Topic]

**FPF Patterns:** C.2.LS, A.16, B.4.1

## What was noticed
[1-3 sentences — preserve the cue verbatim]

## Maturity
- [ ] Fully said (could be stated as a claim)
- [ ] Partly said (cue is real but framing is not yet stable)
- [ ] Pre-abductive (something is up but we cannot yet name it)

## Burden owner
[who carries the responsibility to inspect this]

## Suggested next pattern
[which FPF entry / specialist would inspect this next, and when]

## Do-not-collapse markers
- [terms or distinctions that must not be flattened in further work]
```

---

## Template: Same-Entity Rewrite

```markdown
# Rewrite — [Source Title]

**FPF Patterns:** A.6.3.CR, A.6.3.RT, E.17.EFP

## Object of talk (must remain stable)
[1-2 sentences naming the entity being rewritten]

## Stable elements (kept)
- [...]

## Changed elements (allowed)
- Register: [Tech → Plain / Plain → Tech]
- Audience: [...]
- Length: [...]

## Audit log (E.17.AUD.LHR)
| Source span | Rewrite span | Change type | Evidence claim affected? |

## Rewrite
[the actual rewritten text]
```

---

## Template: Name Card

```markdown
# Name Card — [Current Name]

**FPF Patterns:** F.18, E.10

## Current name
[verbatim]

## Problem with the current name
[what semantic drift / overload / mismatch motivates the rename]

## Pareto-front of candidate names

| Candidate | Tech / Plain | Strength | Cost |
|---|---|---|---|

## Recommendation
[chosen name + rationale]

## Migration note
[what will break if we rename, where the old name is referenced]
```

---

## Template: SoTA Pack

```markdown
# State-of-the-Art Pack — [Discipline]

**FPF Patterns:** G.0, G.1, G.2, G.4, G.5

## Scope (G.1)
[discipline boundaries; what is in / out]

## TraditionCards (G.2)
### Tradition: [Name of school of thought]
- Founders / canonical works:
- Core operators:
- Strengths:
- Known limits:

## OperatorCards (G.4)
### Operator: [Name]
- Tradition:
- What it does:
- When to use:
- Inputs / outputs:

## Portfolio scaffold (G.5)
| Candidate | Tradition | Operator | Maturity | Status |

## Refresh discipline
- Refresh cadence: [how often the pack is revisited]
- Decay markers: [what triggers an out-of-cycle refresh]
```

---

## Style notes for every template

- **Lead with the FPF pattern reference** so the reader can drill into `FPF-Spec.md`.
- **Use tables** rather than bullet trees where comparison matters.
- **Be explicit about declared vs. undeclared** — FPF's value is making the implicit visible.
- **Strip pattern IDs** when publishing to a non-FPF audience.
