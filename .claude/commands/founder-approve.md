---
description: Operationalize a Founder decision to move a document from In Review to Approved. Never sets Approved status itself.
argument-hint: [document or approval batch]
---

Prepare Founder Approval for: $ARGUMENTS

This command operationalizes the tail end of the existing review cycle
(`.claude/context/review-workflow.md`, `.claude/workflows/review-cycle.md`):
Codex review and its findings are already resolved, any resulting change
has already been captured in a manual git commit, and what remains is
the Founder's own decision (`docs/00-governance/xp-0002-approval-workflow.md`
step 6: `In Review → Approved` — **Founder only**). This command does not
add a step to that cycle and does not perform the decision itself — it
prepares for it and stops at the point only the Founder may cross.

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
  not draft, imply, or stage an approval in anticipation of one.

## Allowed Actions (only once confirmation is present)

- Prepare a complete, reviewable, **unapplied** patch covering exactly
  what `XP-0002` and `docs/00-governance/xp-0010-documentation-writing-standard.md`
  §12 require for the transition: `docs/DOCUMENT-INDEX.md` status
  row(s), each document's own internal Document Metadata table where one
  exists (`Status` → `Approved`, `Version` → exactly `1.0` — per §12,
  "upon first reaching `Approved`, the version becomes `1.0`," with no
  other value — `Last Updated`, a new Revision History row), and a
  `docs/CHANGELOG.md` entry recording the event. This command covers
  only a document's first transition into `Approved`; a later
  post-approval revision (`1.0` → `2.0` or `1.0` → `1.1`) is out of
  scope and not prepared by this command.
- Note plainly, in the same output, which documents (e.g. those
  following the Domain Architecture pattern) carry no internal metadata
  table to change, per `xp-0010` §3.

## Forbidden Actions

- Never write `Approved` (or any lifecycle status) to any file as part
  of this command's own execution, confirmed or not — per
  `.claude/CLAUDE.md` §4, no AI agent, Claude Code included, ever sets
  that status itself. The Founder applies the prepared patch.
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

A complete, unapplied patch (files, exact diffs) plus a plain statement
that this patch has not been applied and requires the Founder to apply
it directly. If Founder confirmation was missing, output only the stop
notice and what confirmation is required — no patch.
