---
name: fpf-rewrite
description: >
  Same-entity rewrite, explanation, repair, or comparative reading that
  preserves the object of talk. Use when the job is to restate, re-render, or
  re-explain something already written — for a different audience, register,
  or length — without quietly changing what it is about. Produces an audit
  log of stable / changed elements. Triggers on "rewrite without changing
  meaning," "explain this passage," "repair note," "render the same thing
  for a different audience," or "comparative reading."
argument-hint: "[source-path]"
---

# FPF — Same-Entity Rewrite

Apply FPF patterns **A.6.3.CR (comparative reading)**, **A.6.3.RT (re-render)**, **E.17.EFP (entity-first publication)**, **E.17.ID.CR (identity preservation across rewrite)**, and **E.17.AUD.LHR / E.17.AUD.OOTD (audit forms)**.

## Principle

The hardest publication task is *not* writing something new — it is restating something existing for a different audience, register, or length without changing what the text is about. Standard rewriting tools silently shift the object of talk: "patient outcomes" becomes "user outcomes"; "evidence" becomes "data"; "duty" becomes "best practice." A same-entity rewrite preserves the entity being described; the audit log proves it.

## Step 1: Name the object of talk

Write 1–2 sentences naming the entity that must remain stable. Examples:

- "The CHoRUS ASPIRE multi-agent system, specifically Aim 3 (bimodal agents)."
- "The contractual SLA between vendor X and team Y, specifically the latency clause."
- "The project decision D02 (LLaMA-3 backbone selection), as recorded on [date]."

If you cannot write this sentence, you are not doing a same-entity rewrite — you are doing a generic edit. Different skill needed.

## Step 2: List stable elements

What MUST be the same in the rewrite as in the source?

- The entity (system / decision / claim) being described.
- The factual claims with their F-G-R labels.
- The named owners / parties.
- The stated obligations or commitments.
- The evidence carriers (citations, exhibits, logs).

If a stable element does *not* survive the rewrite, that is a defect — not a stylistic choice.

## Step 3: List allowed changes

What is allowed to change?

- **Register** — Tech ↔ Plain (E.10).
- **Audience** — engineers / managers / community / regulator / reviewers.
- **Length** — expansion or compression.
- **Structure** — tables ↔ prose, ordering, headings.
- **Examples** — substitute domain-appropriate examples.
- **Term names** — only via the UTS, swapping a Tech name for its Plain counterpart and vice versa.

## Step 4: Write the rewrite

Apply the changes from Step 3 while preserving everything from Step 2.

If the rewrite reaches a point where preserving Step 2 forces awkward language, that's a signal: either accept the awkwardness, or recognise that you are *not* doing a same-entity rewrite — you are taking on a new claim.

## Step 5: Audit log (E.17.AUD.LHR)

| Source span | Rewrite span | Change type | Evidence claim affected? |
|---|---|---|---|

For each non-trivial change, log it. The audit log is the artifact that proves identity preservation. Without it, the rewrite is unauditable and indistinguishable from a generic edit.

## Step 6: Out-of-the-door check (E.17.AUD.OOTD)

Before publishing, run:

- Does the rewrite still describe the same entity (Step 1)?
- Are all stable elements (Step 2) present?
- Did any change in Step 5 affect an evidence claim? If yes, flag.
- Would a reader of the rewrite reach materially different conclusions about the entity than a reader of the source?

The last check is the hardest: do the rewrite. Set it down. A day later, read both and see if they describe the same world.

## Step 7: Produce the artifact

Use the **Same-Entity Rewrite** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). Save the rewrite + audit log as a single deliverable.

## When to combine with other skills

- **Pairs with:** [`fpf-uts`](../fpf-uts/SKILL.md) — register swaps must use UTS Plain ↔ Tech mappings.
- **Pairs with:** [`fpf-name-card`](../fpf-name-card/SKILL.md) — if a *name* changes, it's a Name Card task, not a rewrite.

## Anti-patterns

- **Skipping the object-of-talk sentence.** Without it, identity preservation is unverifiable.
- **No audit log.** A rewrite without an audit log is indistinguishable from a generic edit.
- **Quietly substituting "we" for "the team," or "users" for "patients."** That's a re-frame, not a rewrite. Flag it.
- **Treating a Tech → Plain rewrite as a downgrade.** Both are first-class registers; the UTS makes the swap lawful.
- **Letting "audience appropriateness" justify changing a stable element.** If the audience can't handle the stable element, you may be writing for the wrong audience.
