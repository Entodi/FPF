---
name: fpf-language-state
description: >
  Preserve a partly-said cue — a serious concern or emerging idea that is too
  important to ignore but too early to present as a settled claim,
  requirement, or work record. Produces a short preservation-and-burden note
  with maturity flags and a suggested next pattern. Triggers on "preserve
  this signal," "partly said," "early concern," "not ready to commit but
  worth noting," "I have a hunch," or "something's off but I can't name it
  yet."
argument-hint: "[topic]"
---

# FPF — Language-State Note

Apply FPF patterns **C.2.2a (partly-said cue)**, **C.2.LS / C.2.4–7 (language-state working forms)**, **A.16 / A.16.1 / A.16.2 (language-state markers)**, **B.4.1 (pre-abductive routing)**, and **B.5.2.0 (endpoint patterns)**.

## Principle

Most consequential ideas start partly-said — a cue, a worry, a half-formed framing that is too important to drop and too immature to present as a claim. The standard project response is to either ignore it (loss) or force it into a premature claim shape (distortion). FPF gives it a durable working form: a Language-State Note that records the cue, its maturity, its burden owner, and the pattern that should inspect it next.

This is the lightest-weight FPF artifact and the one most often skipped. Use it freely.

## When to use

- A reviewer says "something feels off about Aim 3" but cannot yet articulate what.
- A user-research signal hints at a misalignment between two stakeholder groups.
- A teammate flags a risk that doesn't fit any existing risk-register row.
- An emerging anomaly in data that doesn't yet rise to a claim.

If the cue is already a settled claim, use [`fpf-claim-register`](../fpf-claim-register/SKILL.md) or [`fpf-evidence-gaps`](../fpf-evidence-gaps/SKILL.md) instead.

## Step 1: Capture the cue verbatim

Write 1–3 sentences in the original speaker's words. Do not paraphrase, do not formalize, do not add caveats. The cue's value is its raw shape.

## Step 2: Tag the maturity

Pick exactly one (A.16):

- **Fully said** — the cue could be stated as a claim. Move it to a claim register.
- **Partly said (LS)** — the cue is real but its framing is not yet stable. This is the typical case for this skill.
- **Pre-abductive (B.4.1)** — something is up but no name yet attaches.

Tagging is a hard commitment. "Probably partly said" is a process bug; force the choice.

## Step 3: Name the burden owner

Who carries the responsibility to inspect this cue? A note without a burden owner is a wish. Examples: "Ethics Lead," "Architecture review committee," "Author at next 1:1."

## Step 4: Suggest the next pattern

Which FPF entry / specialist would inspect this next, and when? Examples:

- "Inspect via `fpf-bounded-contexts` if a vocabulary drift is suspected."
- "Inspect via `fpf-evidence-gaps` if the cue is about an unevidenced premise."
- "Inspect via `fpf-quartet` if it's a system / method / work confusion."
- "Re-inspect at the next quarterly review if it stays partly-said."

## Step 5: Do-not-collapse markers

List terms or distinctions that must not be flattened in further work. These protect the cue from premature merge with adjacent claims.

## Step 6: Produce the artifact

Use the **Language-State Note** template in [`../fpf/references/output-templates.md`](../fpf/references/output-templates.md). A typical note is 10–25 lines. Save in a `language-state/` folder so notes accumulate over a project.

## Anti-patterns

- **Forcing a partly-said cue into a claim.** That's the failure mode FPF is correcting.
- **Skipping the burden owner.** A note without an owner gets archived and forgotten.
- **Skipping the next-pattern field.** A note without a successor pattern can't be retired lawfully.
- **One huge LS note.** Multiple distinct cues = multiple notes.
- **Treating LS notes as a substitute for claim work.** They are the precursor; eventually most are either retired or promoted.

## What changes when the cue matures

A partly-said cue becomes either:

- **Promoted** — fully said, moved to a claim register, an evidence gap, or a decision.
- **Retired** — the cue resolved; record the resolution and date.
- **Long-running** — kept as LS across cycles; this is legitimate but deserves explicit acknowledgement.

Track this in the note's history block.
