---
description: Operationalize the Founder's final release decision after manual git commit — confirms repository tracking is consistent. Never commits or changes lifecycle status itself.
argument-hint: [approval batch or milestone]
---

Prepare Founder Release for: $ARGUMENTS

This command operationalizes the final two steps of the existing
pipeline used for recent governance and foundation work: Codex Approval
→ **Manual Git Commit** → **Founder Decision**
(`.claude/context/review-workflow.md`, `docs/00-governance/xp-0002-approval-workflow.md`).
"Release" here means only that: confirming a Founder-approved (and,
where applicable, Frozen) change is accurately committed and that the
repository's own tracking files agree with it — it does not define a
new lifecycle status. The six statuses in
`docs/00-governance/xp-0000-documentation-governance.md` (`Planned`,
`Draft`, `In Review`, `Approved`, `Deprecated`, `Archived`) remain the
only lifecycle states that exist; this command introduces none.

## Pre-Checks

- Confirm the Founder has already made the underlying decision this
  release closes out (an approval via `founder-approve`, a freeze via
  `founder-freeze`, or an equivalent decision already recorded in
  `docs/DOCUMENT-INDEX.md`) — checked directly, not assumed from earlier
  conversation turns. Note explicitly that `founder-approve` and
  `founder-freeze` never perform a lifecycle status change themselves —
  each only prepares a reviewable, unapplied lifecycle patch; the
  Founder alone applies it. This command's job is to confirm that
  application already happened and is captured in git, never to apply
  it on `founder-approve`'s or `founder-freeze`'s behalf.
- Confirm the change is captured in a git commit — inspect `git log` /
  `git status` for the actual commit, not a description of one.
- Confirm `docs/DOCUMENT-INDEX.md`, `docs/DOCUMENTATION-ROADMAP.md`, and
  `docs/CHANGELOG.md` agree with each other and with the committed
  state (statuses, phase-gate notes, and the changelog entry describing
  the same event).

## Required Confirmation

- Do not proceed past the pre-checks unless the current instruction
  contains an explicit, unambiguous Founder decision that this batch or
  milestone is released/final (e.g. "I confirm this batch is released")
  — not a general "continue" or "proceed."
- If that confirmation is missing, **stop immediately** and state
  exactly what explicit confirmation is needed before continuing.

## Allowed Actions (only once confirmation is present)

- Report, read-only, whether the three tracking files and the git
  history are already consistent with the Founder's decision.
- Where a genuine gap exists (e.g. a tracking file not yet updated to
  match an already-committed, already-approved change), prepare a
  reviewable, **unapplied** patch closing exactly that gap — nothing
  else.

## Forbidden Actions

- Never run `git commit`, `git push`, or any other git write operation —
  the commit this command follows is manual, performed by the Founder
  or under their explicit, separate instruction, never as a side effect
  of this command.
- Never write a lifecycle status change to any file as part of this
  command's own execution — that remains `founder-approve`'s and
  `founder-freeze`'s boundary, and ultimately the Founder's alone
  (`.claude/CLAUDE.md` §4).
- Do not invent a "Released" status or any status beyond the six
  `xp-0000` already defines.
- Do not modify any document's substantive architecture or content.
- Do not modify `docs/DOCUMENTATION-ROADMAP.md`'s phase structure,
  gates, or dependency order.

## Expected Output

Either: a consistency confirmation (tracking files, git history, and
the Founder's decision all agree — nothing to patch); or a small,
reviewable, unapplied patch closing a named tracking gap, with a plain
statement that it has not been applied. If Founder confirmation was
missing, output only the stop notice and what confirmation is required.
