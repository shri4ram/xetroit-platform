---
description: Prepare an Approved document for Freeze — final governance closeout after Founder approval.
argument-hint: [path to document]
---

Prepare the following document for Freeze: $ARGUMENTS

Freeze is the final step of the review cycle
(`.claude/context/review-workflow.md`): CTO → Founder Review → Claude →
CTO Review → Codex → CTO Review → Claude Fixes → Final CTO Review →
Governance Closeout → **Freeze**. It happens only after the Founder has
actually set the document's status to `Approved` — this command never
performs that transition itself.

## Pre-Checks

- Confirm the document's status is already `Approved`, recorded by the
  Founder, in both its own metadata and `docs/DOCUMENT-INDEX.md`.
- Confirm every Codex finding against it is resolved (fixed or
  explicitly deferred with written Founder reasoning) — an unresolved
  finding means it is not ready to Freeze, regardless of its status
  field.
- Confirm its Revision History (or, for the Domain Architecture pattern,
  its Architecture Governance section) reflects the approved content
  accurately.

## Allowed Actions

- Add a closing Revision History / governance-closeout entry recording
  the freeze date and reviewer chain, matching the style already used by
  frozen documents (e.g. `XP-0014`, `XP-0015`).
- Note the document as **Frozen** alongside `Approved`, if that is this
  document's own convention (see `.claude/context/architecture-governance.md`
  for which families already carry this marker).

## Forbidden Actions

- Do not set or imply `Approved` status yourself — that must already be
  true, set by the Founder, before this command runs.
- Do not alter the document's substantive content at this step — Freeze
  closes out governance bookkeeping, it is not a last content edit.
- Do not update `docs/DOCUMENT-INDEX.md` or `docs/CHANGELOG.md` unless
  the current task explicitly asks for it.

## Expected Output

A governance-closeout note confirming the document is `Approved` and, if
applicable, marking it **Frozen**, with an accurate closing history entry
— no content change beyond that bookkeeping.
