# Documentation Governance

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0000 |
| **Title** | Documentation Governance |
| **Version** | 1.0 |
| **Status** | Approved |
| **Owner** | Founder |
| **Category** | Governance |
| **Priority** | Critical |
| **Audience** | Investors / Developers / Architects / AI Agents |
| **Last Updated** | 2026-07-07 |
| **Related Documents** | XP-0001, XP-0002, XP-0003, XP-0004 |

**Frozen:** This document is `Approved` and **Frozen** as of 2026-07-08,
per Founder decision, completing the Phase 1 Founder Freeze. Further
changes require a new revision and a fresh approval cycle per
`xp-0002-approval-workflow.md` — it is not edited casually while frozen.

---

## Purpose

This document is the constitution of the XETROIT documentation system. It
defines what documentation is for, the rule that governs the relationship
between documentation and implementation, the lifecycle every document must
pass through, and the numbering convention used to identify documents
permanently and unambiguously.

It supersedes the informal governance notes originally placed in
`docs/README.md`; `docs/README.md` now acts as a navigation entry point and
defers to this document as the authoritative source.

## Scope

Applies to every document under `docs/`, and to every human and AI
participant who authors, reviews, approves, or consumes those documents.
Does not define product architecture itself — only the rules governing how
architecture and product documents come to exist and become authoritative.

## Goals

- Establish documentation as the enforceable specification for engineering
  work, not a description written after the fact.
- Make document status unambiguous at all times: Planned, Draft, In
  Review, Approved, Deprecated, or Archived — nothing else.
- Make the `XP-NNNN` identifier a permanent, collision-free reference usable
  by humans and AI agents alike.
- Make governance itself a documented, versioned, reviewable artifact
  rather than an implicit understanding.

## Non-Goals

- This document does not define *who* holds which role or approval
  authority — see `xp-0001-ai-engineering-governance.md`.
- This document does not define the mechanics of moving a document through
  review — see `xp-0002-approval-workflow.md`.
- This document does not define file/folder naming conventions — see
  `xp-0003-repository-standards.md`.
- This document does not define how architecture decisions themselves are
  recorded — see `xp-0004-architecture-decision-records.md`.

## Dependencies

None. This is the root governance document; all other governance and
platform documents are subordinate to it.

## Architecture Notes

N/A — this document governs documentation, not system architecture.

## Business Rules

### Docs-First Rule

**No feature, module, or service may be implemented before its
corresponding document exists and has reached `Approved` status.**

This applies equally to human engineers and every AI agent (Claude Code,
Codex, and any future AI agent). Documentation is not a byproduct of
engineering — it is the specification engineering must follow. Code that
contradicts an Approved document is a defect in the code, not the
document.

### Single Source of Truth

The `docs/` directory supersedes tribal knowledge, chat threads, and verbal
decisions. If a decision is not written here, it does not govern the
platform, regardless of who made it or where it was discussed.

## Technical Rules

### Document Lifecycle

Every formal document (any file with an `XP-NNNN` ID) moves through the
following states, in order. States may not be skipped, and only the
Founder may move a document into `Approved` (see `xp-0001` for full
approval authority rules).

| Status | Meaning |
|---|---|
| **Planned** | Identified and registered in `DOCUMENT-INDEX.md`, but writing has not started. |
| **Draft** | Actively being written. Content is incomplete or unverified. Not authoritative. |
| **In Review** | Complete draft under review by its Owner and relevant stakeholders (including Codex review, see `xp-0002`). |
| **Approved** | Reviewed, accepted, and authoritative. Implementation may begin. |
| **Deprecated** | Superseded by a newer Approved document but retained for historical reference. |
| **Archived** | No longer relevant to the current platform. Retained for audit history only. |

Status changes must be reflected in both the document's own metadata table
and its row in `DOCUMENT-INDEX.md` in the same change — the two must never
disagree.

### "Foundation Draft" Is Not a Lifecycle Status

Early in this repository's history, several bootstrap files (`docs/README.md`,
per-folder `README.md` files, `CONTRIBUTING.md`, `GLOSSARY.md`,
`CHANGELOG.md`) were marked `Status: Foundation Draft`. This is
**explicitly not one of the six lifecycle statuses above** and must never be
treated as equivalent to `Draft`.

**`Foundation Draft` is defined as:** a temporary, non-lifecycle marker used
only on repository scaffolding files — files that describe the *shape* of
the documentation system itself (folder purposes, navigation, templates)
rather than a specific `XP-NNNN` decision or specification. A file carrying
this status:

- Has no `XP-NNNN` ID and is never registered in `DOCUMENT-INDEX.md` as a
  numbered document.
- Is not subject to the Approval Gate (see below), because it authorizes no
  implementation work on its own.
- Must be replaced with a real lifecycle status the moment the file stops
  being pure scaffolding and starts carrying a specific, substantive
  decision — at which point it must be assigned an `XP-NNNN` ID and enter
  the lifecycle at `Draft`, as happened with the governance documents in
  this folder.

Any folder `README.md` describing "current status" as `Foundation Draft`
is stating that the *folder* has been scaffolded, not that any decision
inside it is ready to be acted upon.

### Document Numbering Convention

All formal documents use the prefix `XP` followed by a zero-padded
four-digit sequence number, assigned once, in order of registration, and
never reused:

```
XP-0000, XP-0001, XP-0002, ... XP-9999
```

Rules:

1. A number is assigned only when a document is registered in
   `DOCUMENT-INDEX.md`, even if its status is `Planned`.
2. Numbers are permanent. A deprecated or archived document's number is
   retired with it and never reassigned.
3. Folder placement indicates domain, not numbering order. The `XP-NNNN`
   ID — not the folder — is the canonical reference used in cross-links,
   commits, and AI agent context.
4. **No number may be assigned speculatively for a document whose content
   has not yet been authored under an approved governance process.** (This
   rule exists because an earlier draft of this repository pre-registered
   `XP-0000`–`XP-0010` for platform/module documents before governance
   existed, colliding with the numbers now correctly claimed by this
   governance charter. See `DOCUMENT-INDEX.md` for how that collision was
   resolved.)

## AI Agent Notes

- Treat this document, once `Approved`, as the highest-authority
  documentation-governance reference in the repository. If any other
  document's stated process conflicts with this one, this document wins
  until the conflict is resolved and one document is corrected.
- Never write `Approved` into this document's own status field, or into
  any document's status field — see `xp-0001-ai-engineering-governance.md`
  for who holds that authority.
- Never treat a file marked `Foundation Draft` as authoritative for
  implementation. It is scaffolding, not specification.
- When registering a new document, always assign the next unused `XP-NNNN`
  number by checking `DOCUMENT-INDEX.md` first — never guess or reuse a
  retired number.

## Open Questions

- Should `Foundation Draft` scaffolding files eventually be retired
  entirely once every folder has real `Approved` content, or do they
  remain permanently as navigation aids? Decision deferred to the Founder.

## Approval Checklist

- [x] Content reviewed by Founder
- [x] Reviewed by ChatGPT (CTO / Product Architect)
- [x] Reviewed by Codex
- [x] No open blocking questions remain
- [x] Cross-references updated in `DOCUMENT-INDEX.md`
- [x] Status updated in document metadata and `DOCUMENT-INDEX.md`

## Revision History

| Version | Date | Author | Summary of Change |
|---|---|---|---|
| 0.1 | 2026-07-02 | Claude Code | Initial governance concepts embedded in `docs/README.md` (pre-formalization). |
| 0.2 | 2026-07-02 | Claude Code | Formalized as XP-0000 in `00-governance/`; added explicit "Foundation Draft" bootstrap-state definition; documented numbering-collision resolution rule. |
| 1.0 | 2026-07-07 | Claude Code | Founder-approved: Status `In Review` → `Approved` as part of the Phase 1 Foundation Closeout. The remaining Open Question (Foundation Draft retirement) was assessed as non-blocking and Founder-confirmed; Approval Checklist fully satisfied. No content in Sections 1–17 changed. |
| 1.0 | 2026-07-08 | Claude Code | Founder Freeze: marked **Frozen** alongside `Approved`, completing the review workflow (CTO → Founder Review → Claude → CTO Review → Codex → CTO Review → Claude Fixes → Final CTO Review → Governance Closeout → Freeze) as part of the Phase 1 Founder Freeze. No content change. |
