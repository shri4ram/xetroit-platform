# Engineering Decision Pyramid

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0006 |
| **Title** | Engineering Decision Pyramid |
| **Version** | 1.0 |
| **Status** | Approved |
| **Owner** | Founder |
| **Category** | Governance |
| **Priority** | Critical |
| **Audience** | Investors / Developers / Architects / AI Agents |
| **Last Updated** | 2026-07-07 |
| **Related Documents** | XP-0000, XP-0001, XP-0005, XP-0007, XP-0008 |

---

## Purpose

When two rules, decisions, or instructions appear to conflict, someone —
human or AI — must be able to determine which one wins without asking the
Founder every time. This document defines the strict hierarchy of
authority that every decision on the XETROIT Platform must respect,
starting from the Founder's vision down to day-to-day operations.

## Scope

Applies to every layer of decision-making across the platform: product
vision, engineering principles, governance rules, architecture,
business rules, implementation, testing, deployment, and operations. It
governs the *relationship* between these layers, not the content of any
one layer.

## Goals

- Make "which decision wins" mechanically resolvable by pointing at a
  layer number.
- Prevent lower-layer convenience (e.g. a quick implementation shortcut)
  from silently overriding a higher-layer rule (e.g. a governance
  requirement).
- Give AI agents an explicit reference for escalating conflicts instead of
  resolving them by guesswork.

## Non-Goals

- Does not define the content of any specific layer (e.g. this document
  does not list the engineering principles themselves — see `xp-0005`).
- Does not replace the Approval Workflow (`xp-0002`) — the pyramid defines
  precedence between layers; the approval workflow defines how a document
  moves through its own lifecycle.

## Dependencies

`xp-0000-documentation-governance.md`, `xp-0001-ai-engineering-governance.md`,
`xp-0005-engineering-principles.md`.

## Architecture Notes

N/A — this is a governance/authority model, not a system architecture.

## Business Rules

N/A.

## Technical Rules

### The Pyramid

```
        Founder Vision
              ↓
      Engineering Principles
              ↓
          Governance
              ↓
          Architecture
              ↓
         Business Rules
              ↓
         Implementation
              ↓
            Testing
              ↓
           Deployment
              ↓
           Operations
```

### Layer Definitions

| Layer | What It Contains | Authoritative Source (once it exists) |
|---|---|---|
| **Founder Vision** | The Founder's intent for what XETROIT is and why it exists. Cannot be overridden by any other layer. | `00-company/` (once authored) and direct Founder decisions. |
| **Engineering Principles** | The timeless judgment criteria for every technical decision. | `xp-0005-engineering-principles.md`. |
| **Governance** | Rules for how decisions are made, documented, reviewed, and approved — including roles and authority. | `00-governance/` (`XP-0000`–`XP-0004`, `XP-0007`). |
| **Architecture** | Platform-wide and module-level system design: boundaries, contracts, data flow. | Future `01-platform/`, `02-core-platform/`, and module documents, plus ADRs (`xp-0004`). |
| **Business Rules** | Domain-specific rules governing how a module behaves (e.g. Business OS, Marketplace, Payments). | Future module documents, written using `DOCUMENT-TEMPLATE.md`'s Business Rules section. |
| **Implementation** | The actual code implementing an Approved architecture and business rules. | The codebase itself, plus its governing `XP-NNNN` document. |
| **Testing** | Verification that implementation matches its specification. | Test suites and verification steps referenced by the governing document. |
| **Deployment** | How verified implementation reaches production. | Future `10-devops/` documents. |
| **Operations** | How the running system is monitored, maintained, and operated day to day. | Future `10-devops/` and `11-security/` documents. |

### The Non-Contradiction Rule

**A lower layer must never contradict a higher layer. When a conflict is
found, the higher layer wins, and the lower layer must be corrected — not
the reverse.**

Concretely:

1. An **Operations** habit that conflicts with a **Deployment** rule is
   wrong; fix the operational habit.
2. A **Testing** shortcut that lets **Implementation** diverge from its
   specification is wrong; fix the test or the implementation, not the
   specification, unless the specification itself is later revised through
   its own approval process.
3. An **Implementation** detail that contradicts documented **Business
   Rules** is a defect in the code, per `xp-0000`'s Docs-First Rule.
4. A **Business Rule** that contradicts platform **Architecture** must be
   escalated — either the business rule is adjusted, or an ADR is
   proposed to change the architecture, per `xp-0004`.
5. An **Architecture** decision that contradicts **Governance** (e.g.
   proposes skipping the Approval Gate) is invalid regardless of who
   proposed it.
6. A **Governance** rule that contradicts an **Engineering Principle**
   must be revised — governance exists to serve the principles, not
   override them.
7. An **Engineering Principle** that contradicts **Founder Vision** must
   be revised by the Founder — vision is the root of the pyramid and has
   no higher authority to defer to within this document.

### Resolving a Conflict

When any two layers appear to conflict:

1. Identify which layer each conflicting rule belongs to.
2. The higher layer's rule stands; the lower layer's rule (or the
   artifact expressing it — code, document, habit) must be corrected.
3. If the conflict reveals that a higher-layer document itself is wrong or
   outdated, that document must go through its own revision and
   re-approval (`xp-0002`) — it is never silently reinterpreted to make a
   lower-layer shortcut fit.
4. If resolution is unclear even after identifying the layers, escalate to
   the Founder rather than guessing (see `xp-0008-ai-decision-checklist.md`
   for the AI-specific version of this rule).

## AI Agent Notes

- Before implementing anything, an AI agent should be able to state which
  layer its instruction sits at and confirm no higher layer is being
  violated. If it cannot state this confidently, that is itself a signal
  to pause per `xp-0008`.
- "The Founder asked for it directly" does not automatically clear a
  request through every lower layer — Founder Vision sits at the top, but
  a specific instruction still needs to be checked against Governance and
  Architecture layers for consistency (e.g. the Founder asking for a quick
  implementation still requires an Approved document per the Docs-First
  Rule, unless the Founder explicitly and knowingly overrides the gate for
  that instance, per `xp-0002`).
- This pyramid does not grant any AI agent authority to reinterpret a
  higher layer in order to justify a lower-layer convenience.

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
| 0.1 | 2026-07-02 | Claude Code | Initial draft: ten-layer decision pyramid, layer definitions, non-contradiction rule, conflict resolution procedure. |
| 1.0 | 2026-07-07 | Claude Code | Founder-approved: Status `In Review` → `Approved` as part of the Phase 1 Foundation Closeout. Approval Checklist fully satisfied. No content change. |
