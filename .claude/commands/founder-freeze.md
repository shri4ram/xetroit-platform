---
description: Operationalize a Founder decision to Freeze an Approved document. Never sets Approved or Frozen status itself.
argument-hint: [document or approval batch]
---

Prepare Founder Freeze for: $ARGUMENTS

Freeze is the final step of the existing review cycle
(`.claude/context/review-workflow.md`, `.claude/workflows/freeze-process.md`):
CTO → Founder Review → Claude → CTO Review → Codex → CTO Review →
Claude Fixes → Final CTO Review → Governance Closeout → **Freeze**. It
happens only after the Founder has already set the document's status to
`Approved`. This command does not add a step to that cycle, does not
perform the Founder's Approved decision, and does not itself mark
anything Frozen — it prepares the closeout bookkeeping and stops at the
point only the Founder may cross. It is the Founder-facing counterpart
of the existing `.claude/commands/freeze.md`; it does not replace or
duplicate that command's own preconditions.

## Pre-Checks

- Confirm the document's status is already `Approved`, recorded by the
  Founder, in both its own metadata (where one exists) and
  `docs/DOCUMENT-INDEX.md` — checked directly, not from memory of an
  earlier session.
- Confirm every Codex finding against it is resolved: fixed, or
  explicitly deferred with the Founder's own written reasoning already
  recorded.
- Confirm its Approval Checklist (or, for the Domain Architecture
  pattern, its Architecture Governance section) is fully satisfied.
- Confirm the approved state is already captured in a manual git
  commit.

## Required Confirmation

- Do not proceed past the pre-checks unless the current instruction
  contains an explicit, unambiguous Founder decision to freeze (e.g.
  "I confirm, freeze X") — not a general "continue" or "proceed."
- If that confirmation is missing, **stop immediately** and state
  exactly what explicit confirmation is needed before continuing. Do
  not draft or stage a freeze in anticipation of one.

## Allowed Actions (only once confirmation is present)

- Prepare a reviewable, **unapplied** patch adding a closing governance-
  closeout entry — a Revision History row, or an Architecture Governance
  note for the Domain Architecture pattern — recording the freeze date
  and the review chain completed, matching the style already used by
  frozen documents (e.g. `XP-0014`, `XP-0015`).
- Prepare the same for marking the document **Frozen** alongside (never
  instead of) `Approved`, only where `docs/DOCUMENT-INDEX.md` or the
  document's own convention calls for that marker.

## Forbidden Actions

- Never write `Approved` or `Frozen` to any file as part of this
  command's own execution, confirmed or not — per `.claude/CLAUDE.md`
  §4, no AI agent, Claude Code included, ever sets that status itself.
  The Founder applies the prepared patch.
- Do not alter the document's substantive content — Freeze closes out
  governance bookkeeping, it is not a last content edit.
- Do not update `docs/DOCUMENT-INDEX.md` or `docs/CHANGELOG.md` beyond
  what the current task explicitly asks for.
- Do not introduce a new workflow step or governance rule not already
  defined in `XP-0000`–`XP-0002`.
- Do not run `git commit`.

## Expected Output

A complete, unapplied patch (files, exact diffs) for the closeout entry
and, where applicable, the Frozen marker, plus a plain statement that it
has not been applied and requires the Founder to apply it directly. If
Founder confirmation was missing, output only the stop notice and what
confirmation is required — no patch.
