---
description: Prepare a document for Codex's independent review pass before it advances toward Approved.
argument-hint: [path to document]
---

Prepare the following document for Codex review: $ARGUMENTS

Codex review happens while a document is `In Review`, before Founder
approval (`docs/00-governance/xp-0002-approval-workflow.md`). This
command gets a document *ready* for that pass — it does not perform the
Codex review itself.

## Pre-Checks

- Confirm the document is actually complete enough for `In Review`: every
  required section present or explicitly `N/A` with a reason
  (`docs/00-governance/xp-0010-documentation-writing-standard.md` §17,
  Definition of Done).
- Confirm every cross-reference resolves to a real document/section.
- Confirm Open Questions are current — nothing resolved is still listed
  open, nothing open is missing.

## Allowed Actions

- Fix structural gaps: missing sections, unresolved internal
  contradictions, stale cross-references, outdated Revision History.
- Update the document's own status to `In Review` once genuinely ready
  (`XP-0002` step 3), if the task's scope covers that transition.

## Forbidden Actions

- Do not perform the Codex review yourself or write findings on Codex's
  behalf — Codex's review is independent of the authoring process.
- Do not set status to `Approved`.
- Do not resolve a real, substantive Open Question by guessing — an
  unresolved substantive question means the document is not ready for
  this pass yet.

## Expected Output

A document at `In Review`, structurally complete per the Definition of
Done, with current Open Questions — genuinely ready for an independent
reviewer to evaluate, not merely marked as if it were.
