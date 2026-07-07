# Repository Constitution

> Read time: under 10 minutes. If you are a new engineer or a new AI agent
> and only read one document before touching this repository, read this
> one — then follow its links for depth.

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0007 |
| **Title** | Repository Constitution |
| **Version** | 1.0 |
| **Status** | Approved |
| **Owner** | Founder |
| **Category** | Governance |
| **Priority** | Critical |
| **Audience** | Investors / Developers / Architects / AI Agents |
| **Last Updated** | 2026-07-07 |
| **Related Documents** | XP-0000, XP-0001, XP-0002, XP-0005, XP-0006, XP-0008 |

**Frozen:** This document is `Approved` and **Frozen** as of 2026-07-08,
per Founder decision, completing the Phase 1 Founder Freeze. Further
changes require a new revision and a fresh approval cycle per
`xp-0002-approval-workflow.md` — it is not edited casually while frozen.

---

## Purpose

This is the short-form constitution of the XETROIT repository: the small
set of non-negotiable facts every contributor — human or AI — must know
before doing anything else. Full detail lives in the linked documents;
this document exists so no one has to read all of them just to get
oriented.

## Scope

Covers repository purpose, docs-first policy, approval requirements, the
AI collaboration model, engineering and quality expectations,
documentation ownership, and change management philosophy — in summary
form. It does not restate their full mechanics.

## Goals

- Be readable in under ten minutes by a brand-new engineer or AI agent.
- Answer "what are the rules here" without requiring prior context.
- Point to the authoritative document for anyone who needs the full detail.

## Non-Goals

- Not a substitute for `XP-0000`, `XP-0001`, `XP-0002`, `XP-0005`, or
  `XP-0006` — it summarizes them and must never contradict them.
- Not a platform architecture document.

## Dependencies

`xp-0000-documentation-governance.md`, `xp-0001-ai-engineering-governance.md`,
`xp-0002-approval-workflow.md`, `xp-0005-engineering-principles.md`,
`xp-0006-engineering-decision-pyramid.md`.

## Architecture Notes

N/A.

## Business Rules

N/A.

## Technical Rules

### 1. Repository Purpose

This repository's `docs/` directory is the single source of truth for the
XETROIT Platform. If a decision isn't written here, it isn't official —
regardless of who said it or where. The repository serves four audiences
at once: investors, developers, architects, and AI coding agents.

### 2. Docs-First Policy

**No feature, module, or service is implemented before its governing
document exists and is `Approved`.** Documentation is the specification,
not a write-up after the fact. This applies identically to every human and
every AI agent. Full definition: `xp-0000`.

### 3. Approval Requirements

A document authorizes implementation only when three things are all true:
it exists, the architecture it depends on is `Approved`, and its own
status is `Approved`. **Only the Founder can set a document to
`Approved`** — no AI agent, regardless of role, holds that authority.
Full mechanics: `xp-0002`.

### 4. AI Collaboration Model

Five roles exist today: **Founder** (final authority), **ChatGPT**
(CTO / Product Architect — designs and drafts), **Claude Code**
(authors documentation, implements once Approved), **Codex** (independently
reviews and files findings), and **Future AI Agents** (no authority until
explicitly defined). Every non-trivial effort follows one fixed sequence:

```
Idea → Architecture → Documentation → Claude → Codex → Approval → Implementation → Documentation Update
```

Full definition: `xp-0001`.

### 5. Engineering Expectations

Every decision is judged against a fixed set of principles — simplicity
over complexity, platform before product, reuse before duplication,
documentation before implementation, security by design, AI augments
humans, API-first thinking, modular architecture, consistency over
cleverness, long-term maintainability, progressive enhancement, and
measurable quality. Full definitions and rationale: `xp-0005`.

When rules at different levels (vision, principles, governance,
architecture, business rules, implementation, testing, deployment,
operations) appear to conflict, the higher level always wins — see the
Engineering Decision Pyramid, `xp-0006`.

### 6. Quality Expectations

- Nothing ships that isn't traceable to an `Approved` document.
- Nothing ships that isn't testable or verifiable in some documented way.
- Nothing ships that duplicates an existing capability without a
  documented reason.
- Every contributor, human or AI, should be able to explain *why* a piece
  of work exists, not just *what* it does.

### 7. Documentation Ownership

Every `XP-NNNN` document has a named Owner accountable for its accuracy
and lifecycle progression — currently the Founder for all governance
documents. Ownership does not mean sole authorship; it means
accountability for the document staying correct and current.

### 8. Change Management Philosophy

Approved documents are not edited casually. A change requires a new
revision entry, re-review, and — for anything architecture-impacting —
Founder re-approval. Breaking an Approved decision to unblock code faster
is never acceptable; the document is corrected and re-approved first, per
`xp-0000` and `xp-0002`.

## AI Agent Notes

- This document is a map, not the territory. When in doubt about a
  specific mechanic (who approves what, when to stop, what counts as a
  principle violation), follow the link to the authoritative document
  rather than relying on this summary alone.
- If this document and one of its linked sources ever disagree, the
  linked source is correct and this document has drifted out of date —
  flag it for correction rather than trusting the summary.

## Open Questions

None at this time.

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
| 0.1 | 2026-07-02 | Claude Code | Initial draft: concise constitution summarizing XP-0000, XP-0001, XP-0002, XP-0005, XP-0006. |
| 1.0 | 2026-07-07 | Claude Code | Founder-approved: Status `In Review` → `Approved` as part of the Phase 1 Foundation Closeout. Approval Checklist fully satisfied. No content change. |
| 1.0 | 2026-07-08 | Claude Code | Founder Freeze: marked **Frozen** alongside `Approved`, completing the review workflow (CTO → Founder Review → Claude → CTO Review → Codex → CTO Review → Claude Fixes → Final CTO Review → Governance Closeout → Freeze) as part of the Phase 1 Founder Freeze. No content change. |
