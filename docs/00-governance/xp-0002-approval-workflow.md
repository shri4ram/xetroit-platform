# Approval Workflow

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0002 |
| **Title** | Approval Workflow |
| **Version** | 0.1 |
| **Status** | Draft |
| **Owner** | Founder |
| **Category** | Governance |
| **Priority** | Critical |
| **Audience** | Developers / Architects / AI Agents |
| **Last Updated** | 2026-07-02 |
| **Related Documents** | XP-0000, XP-0001, XP-0004 |

---

## Purpose

`XP-0000` states that no document is authoritative until `Approved`, and
`XP-0001` states that only the Founder may grant that status. This document
defines the mechanical, step-by-step workflow a document moves through to
get there, and states the Approval Gate that blocks implementation until
every condition is met.

## Scope

Applies to every `XP-NNNN` document and every ADR (see `xp-0004`). Does not
apply to non-lifecycle scaffolding files marked `Foundation Draft` (see
`xp-0000`), which carry no implementation authority in the first place.

## Goals

- Make it mechanically checkable whether implementation is currently
  allowed for a given piece of work.
- Ensure Codex review happens before Founder approval, not after.
- Prevent partial or informal approval ("looks fine, go ahead") from
  substituting for a recorded status change.

## Non-Goals

- Does not re-define the six lifecycle statuses themselves — see
  `xp-0000-documentation-governance.md`.
- Does not define role responsibilities — see
  `xp-0001-ai-engineering-governance.md`.

## Dependencies

`xp-0000-documentation-governance.md`, `xp-0001-ai-engineering-governance.md`.

## Architecture Notes

N/A.

## Business Rules

### The Approval Gate

**Implementation work of any kind — application code, database schemas,
infrastructure changes, or generated production artifacts of any sort —
must not begin until all three of the following are true:**

1. **The relevant `XP-NNNN` document exists** under its correct governance
   or platform folder, following `xp-0003-repository-standards.md`
   naming and structure.
2. **The architecture the work depends on is Approved** — either the
   document itself is an approved architecture document, or it correctly
   cites an approved architecture document/ADR it depends on (see
   `Dependencies` section of the relevant document).
3. **The document's own status is `Approved`** in both its metadata table
   and its `DOCUMENT-INDEX.md` row.

If any one of these three is not true, the work is blocked. There is no
partial-credit state — `In Review` is exactly as non-authoritative as
`Draft` for implementation purposes, even if review is nearly finished.

This gate applies identically to Claude Code, Codex, any future AI agent,
and human contributors.

## Technical Rules

### Status Transition Steps

| Step | Transition | Who May Perform It | Preconditions |
|---|---|---|---|
| 1 | (none) → `Planned` | Anyone (Founder, ChatGPT, Claude Code) | Next unused `XP-NNNN` assigned; row added to `DOCUMENT-INDEX.md`. |
| 2 | `Planned` → `Draft` | ChatGPT or Claude Code | Authoring has actually begun; document uses `DOCUMENT-TEMPLATE.md` structure. |
| 3 | `Draft` → `In Review` | ChatGPT or Claude Code | All template sections completed (or explicitly marked N/A with reasoning); Open Questions list is current. |
| 4 | (within `In Review`) Codex review | Codex | Document is in `In Review`. Codex produces a findings list (may be empty). |
| 5 | `In Review` → `Draft` (rollback) | ChatGPT or Claude Code | Triggered when Codex findings, or Founder feedback, require rework. |
| 6 | `In Review` → `Approved` | **Founder only** | All Codex findings resolved (fixed or explicitly deferred with written reasoning in the document); no open blocking questions remain; Approval Checklist fully satisfied. |
| 7 | `Approved` → `Deprecated` | Founder | A newer Approved document supersedes it; deprecated document links to its replacement. |
| 8 | Any → `Archived` | Founder | Content no longer relevant; retained for audit only. |

### Resolving Codex Findings

A Codex finding is considered resolved when one of the following is true
and recorded in the document (typically in Open Questions or Revision
History):

- The underlying issue was fixed and the document updated accordingly, or
- The Founder explicitly accepted the finding as a deferred/known
  trade-off, with a written reason.

An unresolved finding blocks step 6 (`In Review` → `Approved`).

## AI Agent Notes

- Before generating or editing production code, Claude Code must verify
  the Approval Gate's three conditions against the actual current content
  of `DOCUMENT-INDEX.md` and the target document — not from memory of a
  prior conversation, since status can change between sessions.
- If asked to implement against a document that is not `Approved`, Claude
  Code should say so plainly and either stop or explicitly confirm the
  Founder is knowingly overriding the gate for that instance.
- Codex findings should be specific enough that "resolved" is
  unambiguous — a finding like "improve consistency" is not resolvable;
  restate it as a concrete, checkable defect.

## Open Questions

None at this time.

## Approval Checklist

- [ ] Content reviewed by Founder
- [ ] Reviewed by ChatGPT (CTO / Product Architect)
- [ ] Reviewed by Codex
- [ ] No open blocking questions remain
- [ ] Cross-references updated in `DOCUMENT-INDEX.md`
- [ ] Status updated in document metadata and `DOCUMENT-INDEX.md`

## Revision History

| Version | Date | Author | Summary of Change |
|---|---|---|---|
| 0.1 | 2026-07-02 | Claude Code | Initial draft: status transition table, Approval Gate, Codex finding resolution rule. |
