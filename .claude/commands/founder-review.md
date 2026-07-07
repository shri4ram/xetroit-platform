---
description: Operationalize moving a document or batch from Draft to In Review, readying it for Codex review. Never performs the transition itself.
argument-hint: [document or batch]
---

Prepare Draft → In Review for: $ARGUMENTS

This command operationalizes `docs/00-governance/xp-0002-approval-workflow.md`
step 3: `Draft → In Review`. Per `XP-0002`'s own Status Transition Steps
table, this specific transition may be performed by ChatGPT or Claude
Code — unlike `Approved` (step 6), which `XP-0002` reserves for the
Founder alone and which `founder-approve` and `founder-freeze`
operationalize. This command does not change who `XP-0002` says may
perform this step and does not add a step to the existing cycle
(`.claude/context/review-workflow.md`). It still applies the same
explicit-confirmation discipline as the rest of the `founder-*` family
before preparing anything, and it never performs the transition itself
— it prepares an unapplied lifecycle patch and stops.

## Pre-Checks

- Confirm the target document(s) are actually `Draft` per
  `docs/DOCUMENT-INDEX.md` — not from memory of an earlier session. A
  document already `In Review`, `Approved`, `Deprecated`, or `Archived`
  is out of scope for this command.
- Confirm every required section of `DOCUMENT-TEMPLATE.md` is present,
  or explicitly marked `N/A` with a stated reason (`XP-0002` step 3
  precondition; `docs/00-governance/xp-0010-documentation-writing-standard.md`
  §17, Definition of Done) — for the Domain Architecture pattern,
  confirm the equivalent section set per `xp-0010` §3 instead.
- Confirm the document's Open Questions list is current: nothing
  resolved is still listed open, nothing genuinely open is missing.
- Confirm the document is genuinely ready for the next step in the
  cycle — Codex review while `In Review` (`XP-0002` step 4) — i.e., no
  known structural gap or unresolved internal contradiction would make
  that review premature.

## Required Confirmation

- Do not proceed past the pre-checks unless the current instruction
  contains an explicit, unambiguous decision to move the document(s)
  into `In Review` (e.g. "move X to In Review," "ready X for Codex
  review") — not a general "continue" or "proceed."
- If that confirmation is missing, **stop immediately** and state
  exactly what explicit confirmation is needed before continuing.

## Allowed Actions (only once confirmation is present)

- Prepare a reviewable, **unapplied** patch updating exactly what
  `XP-0002` step 3 requires: the `docs/DOCUMENT-INDEX.md` status row(s)
  (`Draft` → `In Review`), and, where a document's own internal Document
  Metadata table exists, its `Status` field (`Draft` → `In Review`) and
  `Last Updated` field.
- Note, only where the current task's own prior content changes were
  genuinely substantive, that a version increment may apply per
  `xp-0010` §12 — this command does not invent one, edit content, or
  decide this on its own; it only reflects a version change the
  authoring work already made.
- Note plainly which documents (e.g. those following the Domain
  Architecture pattern) carry no internal metadata table to change, per
  `xp-0010` §3.

## Forbidden Actions

- Never write `In Review` (or any lifecycle status) to any file as part
  of this command's own execution, confirmed or not — this command only
  prepares the patch; whoever is directing the work applies it.
- Do not perform, anticipate, or imply the `In Review → Approved`
  transition, Codex's review itself, or any Freeze/Release action —
  those remain `founder-approve`'s, `founder-freeze`'s, and
  `founder-release`'s own boundaries, and the Founder-only decision
  among them remains the Founder's alone (`.claude/CLAUDE.md` §4).
- Do not modify any document's substantive architecture, boundaries, or
  content while preparing this patch — that belongs to the authoring
  step that precedes this command's own scope.
- Do not modify `docs/DOCUMENTATION-ROADMAP.md`'s phase structure, gates,
  or dependency order.
- Do not introduce a new workflow step, review stage, or governance rule
  not already defined in `XP-0000`–`XP-0002`.
- Do not run `git commit`.

## Expected Output

A complete, unapplied patch (files, exact diffs) plus a plain statement
that this patch has not been applied and requires deliberate application
by whoever is directing the work. If explicit confirmation was missing,
output only the stop notice and what confirmation is required — no
patch.
