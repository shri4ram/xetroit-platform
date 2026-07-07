---
description: Record an explicit Founder decision by moving a document from In Review to Approved directly in the repository. Claude performs the mechanical update only; it never decides.
argument-hint: [document or approval batch]
---

Record Founder Approval for: $ARGUMENTS

This command operationalizes the tail end of the existing review cycle
(`.claude/context/review-workflow.md`, `.claude/workflows/review-cycle.md`):
Codex review and its findings are already resolved, any resulting change
has already been captured in a manual git commit, and what remains is
the Founder's own decision (`docs/00-governance/xp-0002-approval-workflow.md`
step 6: `In Review → Approved` — **Founder only**). This command does not
add a step to that cycle and does not make that decision — the decision
belongs to the Founder alone, given explicitly in the current
instruction. Once given, Claude performs the mechanical repository
update recording it directly; Claude never infers, assumes, or replays
a decision from an earlier turn, and never proceeds without one present
in the current instruction.

## Pre-Checks

- Confirm every document included in the target — whether a single
  document or a named Founder Approval Batch — is already `In Review`
  per `docs/DOCUMENT-INDEX.md` — not from memory of an earlier session.
  No document may be included, and no exception may be made, for a
  document sitting at any other point in `XP-0002`'s lifecycle sequence
  (`Planned`, `Draft`, `Deprecated`, `Archived`); a batch is ready only
  when every one of its documents individually satisfies this.
- Confirm every Codex finding against each document is resolved: fixed,
  or explicitly deferred with the Founder's own written reasoning
  already recorded (`XP-0002`, "Resolving Codex Findings").
- Confirm each document's Approval Checklist (or, for the Domain
  Architecture pattern, its Architecture Governance section) is fully
  satisfied.
- Confirm the reviewed state is already captured in a manual git
  commit — this command does not run one and does not treat uncommitted
  work as ready.

## Required Confirmation

- Do not proceed past the pre-checks unless the current instruction
  contains an explicit, unambiguous Founder approval decision (e.g. "I
  approve X," "As Founder, I approve this batch") — not a general
  "continue," "looks good," or "proceed."
- If that confirmation is missing, **stop immediately** and state
  exactly what explicit confirmation is needed before continuing. Do
  not perform, imply, or stage any part of the update in anticipation
  of one.

## Allowed Actions (only once confirmation is present)

- Apply directly, to the repository, exactly what `XP-0002` and
  `docs/00-governance/xp-0010-documentation-writing-standard.md` §12
  require for the transition: update `docs/DOCUMENT-INDEX.md` status
  row(s), update each document's own internal Document Metadata table
  where one exists (`Status` → `Approved`, `Version` → exactly `1.0` —
  per §12, "upon first reaching `Approved`, the version becomes `1.0`,"
  with no other value — `Last Updated`, a new Revision History row), and
  add a `docs/CHANGELOG.md` entry recording the event. This command
  covers only a document's first transition into `Approved`; a later
  post-approval revision (`1.0` → `2.0` or `1.0` → `1.1`) is out of
  scope.
- Save every file changed.
- Report plainly, in the same output, which documents (e.g. those
  following the Domain Architecture pattern) carry no internal metadata
  table to update, per `xp-0010` §3.

## Forbidden Actions

- Never apply any part of this update without an explicit, unambiguous
  Founder decision to approve present in the current instruction, per
  `.claude/CLAUDE.md` §4 and `XP-0002` step 6. Absent that explicit
  decision, take no action and state what is missing.
- Never make the approval decision itself — Claude records a decision
  the Founder has already given; it does not evaluate whether a
  document *should* be approved beyond the Pre-Checks' factual
  readiness criteria.
- Do not modify any document's substantive architecture, boundaries, or
  content — this is a lifecycle action only.
- Do not modify `docs/DOCUMENTATION-ROADMAP.md`'s phase structure, gates,
  or dependency order — only status-tracking prose describing what is
  now `Approved`.
- Do not introduce a new workflow step, review stage, or governance rule
  not already defined in `XP-0000`–`XP-0002`.
- Do not run `git commit` — the commit preceding Founder decision is
  manual, per this command's own preconditions.

## Expected Output

Confirmation of exactly what was changed: files modified, the lifecycle
fields changed in each, and a statement that the update has been saved
to the repository, recording the Founder's decision as given. If Founder
confirmation was missing, output only the stop notice and what
confirmation is required — no repository change.
