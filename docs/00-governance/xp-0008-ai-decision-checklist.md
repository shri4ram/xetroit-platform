# AI Decision Checklist

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0008 |
| **Title** | AI Decision Checklist |
| **Version** | 0.1 |
| **Status** | Draft |
| **Owner** | Founder |
| **Category** | Governance |
| **Priority** | Critical |
| **Audience** | Developers / Architects / AI Agents |
| **Last Updated** | 2026-07-02 |
| **Related Documents** | XP-0000, XP-0001, XP-0002, XP-0004, XP-0005, XP-0006, XP-0007 |

---

## Purpose

Every AI agent that touches this repository (Claude Code, Codex, or any
future AI agent) needs one concrete, reusable checklist to run through
before making a change — not a re-derivation of governance philosophy each
time. This document is that checklist.

## Scope

Applies to any AI-driven action that creates or modifies documentation,
proposes architecture, or implements code anywhere in the XETROIT
repository. Does not apply to purely read-only exploration or discussion.

## Goals

- Give AI agents a fast, concrete pre-flight check instead of requiring
  them to re-reason about governance from first principles every time.
- Make "when to stop and ask" and "when to propose an ADR instead of
  implementing" unambiguous.
- Reduce the chance of an AI agent producing work that is later rejected
  for a reason that was checkable in advance.

## Non-Goals

- Does not replace the Approval Workflow (`xp-0002`) — this checklist is a
  pre-flight tool, not the approval mechanism itself.
- Does not redefine the Engineering Principles (`xp-0005`) or the Decision
  Pyramid (`xp-0006`) — it applies them.

## Dependencies

`xp-0000-documentation-governance.md`, `xp-0001-ai-engineering-governance.md`,
`xp-0002-approval-workflow.md`, `xp-0004-architecture-decision-records.md`,
`xp-0005-engineering-principles.md`, `xp-0006-engineering-decision-pyramid.md`.

## Architecture Notes

N/A.

## Business Rules

N/A.

## Technical Rules

### The Checklist

Run through every question below before making a change. Any "no" or
"unsure" answer to a question marked **(blocking)** means: stop before
implementing and resolve it first (fix it, document it, or escalate to the
Founder) — do not proceed and fix it retroactively.

1. **Is this documented?** *(blocking)* — Does a written specification for
   this behavior exist anywhere in `docs/`? If not, this is a
   documentation task first, not an implementation task (`xp-0000`).

2. **Does an approved XP document exist?** *(blocking)* — Is the specific
   document this work depends on at status `Approved`, verified against
   the current `DOCUMENT-INDEX.md` (not memory)? If it is `Draft` or
   `In Review`, implementation is not authorized yet (`xp-0002`).

3. **Does this duplicate an existing capability?** *(blocking)* — Search
   the platform for an equivalent module, function, or pattern before
   writing something new. Reuse before duplication (`xp-0005`, Principle
   3). If unsure whether something equivalent exists, treat that
   uncertainty itself as a reason to ask rather than duplicate.

4. **Does it violate governance?** *(blocking)* — Check against `xp-0000`
   (lifecycle/numbering), `xp-0001` (roles/authority), and `xp-0002`
   (approval gate). Any violation blocks the change regardless of how
   small it seems.

5. **Does it conflict with an ADR?** *(blocking)* — If any Architecture
   Decision Records exist and apply to this area, confirm the proposed
   change is consistent with their accepted decisions (`xp-0004`). A
   conflict with an `Accepted` ADR must be resolved by superseding the
   ADR first, not by implementing around it.

6. **Can it become a shared module?** — If similar logic is likely needed
   elsewhere in the platform, consider whether this should be designed as
   a reusable, shared capability rather than a one-off (`xp-0005`,
   Principles 2 and 3). This is a design-quality question, not
   automatically blocking, but should be answered deliberately, not
   skipped.

7. **Is it secure?** *(blocking)* — Has authentication, authorization,
   data exposure, and abuse potential been considered as part of the
   design, not left implicit (`xp-0005`, Principle 5)?

8. **Is it testable?** *(blocking)* — Is there a concrete way — automated
   test, verification script, or explicit manual check — to confirm this
   works as specified (`xp-0005`, Principle 12)?

9. **Is it maintainable?** — Would a future engineer or AI agent be able
   to safely change this later without special knowledge only the author
   has (`xp-0005`, Principle 10)?

10. **Is it understandable by future engineers?** — Is naming, structure,
    and documentation clear enough that intent doesn't need to be
    reverse-engineered from code (`xp-0005`, Principle 9)?

### When an AI Must Stop and Request Clarification

Stop and ask the Founder (or the relevant human/AI reviewer per `xp-0001`)
before proceeding when any of the following is true:

- A **blocking** checklist item above cannot be answered "yes" with
  confidence.
- The instruction received conflicts with a higher layer of the
  Engineering Decision Pyramid (`xp-0006`) — e.g. an instruction to
  implement against a non-`Approved` document, or to skip documentation
  entirely.
- Two existing Approved documents (or an Approved document and an
  Accepted ADR) appear to contradict each other.
- The action would be irreversible or high-consequence (e.g. deleting
  data, changing a public API contract, modifying financial/payment
  logic) and no explicit Approved document addresses that specific case.
- The scope of the request is broader than what its governing document
  actually authorizes.

Asking is always cheaper than reversing a wrong action. Silence or
best-effort guessing is not an acceptable substitute for asking when a
blocking item fails.

### When an ADR Should Be Proposed Instead of Implementation

Propose an ADR (per `xp-0004`) rather than implementing directly when:

- The work requires a technical decision not already covered by an
  Approved architecture document (e.g. choosing between two viable
  technical approaches with real trade-offs).
- The proposed approach would deviate from an existing Engineering
  Principle (`xp-0005`) and the deviation seems justified — document the
  justification as an ADR before proceeding, never as a silent exception.
- The change would alter or supersede a decision already recorded in an
  existing ADR.
- The decision, once made, will constrain future work in a way that later
  contributors will need to understand the reasoning for.

An ADR records the decision; it does not itself authorize implementation —
the underlying `XP-NNNN` document must still reach `Approved` per the
normal workflow before implementation begins, unless the ADR is explicitly
scoped as the sole governing artifact for a narrow technical choice within
an already-Approved document.

## AI Agent Notes

- Run this checklist at the start of a task and again before finalizing
  it — requirements and available documents can change mid-task.
- This checklist assumes good faith effort, not perfection. If a question
  is genuinely ambiguous after reasonable investigation, that ambiguity
  itself is the answer: stop and ask, rather than picking an interpretation
  silently.
- This checklist does not grant permission to implement once all items
  pass — it only confirms the work is *ready* to proceed. Approval Gate
  conditions (`xp-0002`) still govern whether implementation is authorized.

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
| 0.1 | 2026-07-02 | Claude Code | Initial draft: ten-item pre-flight checklist, stop-and-clarify triggers, ADR-vs-implementation guidance. |
