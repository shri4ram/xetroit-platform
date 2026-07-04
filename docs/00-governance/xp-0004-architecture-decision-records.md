# Architecture Decision Records

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0004 |
| **Title** | Architecture Decision Records |
| **Version** | 0.1 |
| **Status** | Draft |
| **Owner** | Founder |
| **Category** | Governance |
| **Priority** | High |
| **Audience** | Developers / Architects / AI Agents |
| **Last Updated** | 2026-07-02 |
| **Related Documents** | XP-0000, XP-0001, XP-0002, XP-0003 |

---

## Purpose

`XP-NNNN` documents capture durable specifications (what a module is and
how it behaves). They are not well suited to capturing the many smaller,
point-in-time technical decisions made while designing or building that
specification (e.g. "we chose PostgreSQL over MySQL," "we chose queue-based
processing over synchronous calls"). This document defines the Architecture
Decision Record (ADR) standard used to capture those decisions once
platform architecture work begins.

No ADRs are created by this document — it defines the standard only, per
this task's scope.

## Scope

Applies to any future architecturally significant decision made anywhere
in the platform (core platform, any module, infrastructure, AI platform).
Does not apply to documentation-governance decisions themselves, which are
captured directly in the relevant `00-governance/` document's Revision
History instead.

## Goals

- Give every non-trivial technical decision a permanent, dated, reviewable
  record independent of the broader `XP-NNNN` document it supports.
- Keep ADRs lightweight relative to full `XP-NNNN` documents.
- Ensure ADRs go through the same review discipline (Codex review, Founder
  approval) as any other governed decision.

## Non-Goals

- ADRs do not replace `XP-NNNN` documents — an ADR records *a decision*,
  an `XP-NNNN` document records *a specification*. A specification may cite
  several ADRs as justification for choices it makes.
- This document does not create any ADRs or an `adr/` folder yet; that
  begins once platform architecture work is authorized.

## Dependencies

`xp-0000-documentation-governance.md` (lifecycle), `xp-0002-approval-workflow.md`
(review/approval mechanics, reused for ADRs).

## Architecture Notes

N/A — this document defines a record-keeping standard, not architecture
itself.

## Business Rules

N/A.

## Technical Rules

### ADR Numbering

ADRs use a separate sequence from `XP-NNNN`, prefixed `ADR-`, zero-padded
to four digits, assigned in order and never reused:

```
ADR-0001, ADR-0002, ADR-0003, ...
```

ADRs will live under `docs/00-governance/adr/` once the first one is
created, named `adr-nnnn-short-descriptive-slug.md` (same lowercase
kebab-case convention as `XP-NNNN` files, per `xp-0003`). Each `XP-NNNN`
document that relies on one or more ADRs must list them in its
`Related Documents` field or `Dependencies` section.

### ADR Status Values

ADRs use their own, smaller status set — distinct from the six-state
`XP-NNNN` lifecycle, because a decision record's job is to freeze a
decision at a point in time, not to evolve through drafting stages:

| Status | Meaning |
|---|---|
| **Proposed** | Decision drafted, not yet reviewed or accepted. |
| **Accepted** | Reviewed and approved by the Founder; the decision is in effect. |
| **Rejected** | Considered and explicitly not adopted; retained for record. |
| **Superseded** | A later ADR replaces this decision; the record links to its successor. |
| **Deprecated** | The decision no longer applies (e.g. the component it concerned was removed), without being replaced by a new decision. |

### ADR Template

```markdown
# ADR-NNNN: [Decision Title]

**Status:** Proposed | Accepted | Rejected | Superseded | Deprecated
**Date:** YYYY-MM-DD
**Deciders:** Founder, ChatGPT (CTO / Product Architect)
**Related:** XP-NNNN, ADR-NNNN (if superseding/superseded)

## Context

What situation or problem made this decision necessary.

## Decision

The decision that was made, stated as a single clear sentence, followed by
supporting detail.

## Alternatives Considered

Other options evaluated and why they were not chosen.

## Consequences

What becomes easier or harder as a result of this decision, including
trade-offs knowingly accepted.

## Review

- [ ] Reviewed by Codex
- [ ] Approved by Founder
```

### Review Requirements

- Every ADR is reviewed by Codex before it may move from `Proposed` to
  `Accepted`, following the same finding-resolution rule as
  `xp-0002-approval-workflow.md`.
- Only the Founder may move an ADR to `Accepted` or `Rejected`.
- Superseding an ADR requires creating a new ADR that references the old
  one; the old ADR's status is then updated to `Superseded`, never deleted.

## AI Agent Notes

- Do not create ADR files or the `adr/` folder as part of documentation
  governance work — that begins only once platform architecture work is
  explicitly authorized, per this task's constraints.
- When platform architecture work does begin, use the template above
  verbatim as the starting structure for any new ADR.
- An ADR is not a substitute for updating the `XP-NNNN` document it
  supports — if a decision changes what a specification says, the
  specification document itself must also be revised.

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
| 0.1 | 2026-07-02 | Claude Code | Initial draft: ADR numbering, status values, template, and review requirements. |
