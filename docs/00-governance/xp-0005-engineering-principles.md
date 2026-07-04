# Engineering Principles

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0005 |
| **Title** | Engineering Principles |
| **Version** | 0.1 |
| **Status** | Draft |
| **Owner** | Founder |
| **Category** | Governance |
| **Priority** | Critical |
| **Audience** | Investors / Developers / Architects / AI Agents |
| **Last Updated** | 2026-07-02 |
| **Related Documents** | XP-0000, XP-0001, XP-0006, XP-0007, XP-0008 |

---

## Purpose

Every architectural and implementation decision on the XETROIT Platform —
made by the Founder, ChatGPT, Claude Code, Codex, or any future AI agent —
must be traceable to a small set of timeless principles. This document
defines those principles so that "why did we build it this way" always has
an answer that predates and outlives any single feature.

These principles do not describe *what* to build (no product, module, or
Laravel/Flutter implementation detail appears here). They describe *how
every decision about what to build is judged*.

## Scope

Applies to every decision made anywhere in the platform: architecture,
module design, API shape, data modeling, security posture, and AI-assisted
implementation. Does not apply to business/product decisions themselves
(e.g. which vertical to build) — see `00-company/` and future platform
documents for those.

## Goals

- Give every engineer and AI agent a fixed, small reference for judging
  whether a proposed approach fits XETROIT's engineering culture.
- Make trade-off reasoning explicit rather than personal preference.
- Provide the layer immediately below Founder Vision in the decision
  hierarchy (see `xp-0006-engineering-decision-pyramid.md`).

## Non-Goals

- Does not define the decision hierarchy itself — see `xp-0006`.
- Does not define approval mechanics — see `xp-0002`.
- Does not describe any specific module, business rule, or technology
  implementation.

## Dependencies

`xp-0000-documentation-governance.md` (lifecycle these principles are
governed by), `xp-0001-ai-engineering-governance.md` (roles applying them).

## Architecture Notes

N/A — this document defines judgment criteria, not architecture.

## Business Rules

N/A.

## Technical Rules

### The Principles

Each principle below is binding guidance, not a suggestion. A design that
violates one of these without a documented, reasoned exception (recorded
as an ADR per `xp-0004`) should be treated as incorrect, not merely
suboptimal.

#### 1. Simplicity Over Complexity

- **Why it exists:** Complexity compounds. A platform maintained by a
  small team plus AI agents cannot afford accidental complexity — every
  extra moving part is a future point of confusion, bugs, and slower AI
  reasoning about the codebase.
- **Practical implications:** Prefer the boring, well-understood solution
  over the clever one. If two designs solve the problem equally well,
  choose the one with fewer concepts, fewer layers, and fewer new
  abstractions.

#### 2. Platform Before Product

- **Why it exists:** XETROIT is a platform of composable capabilities
  (Core Platform, Business OS, Community OS, Life OS, Marketplace,
  Payments, AI, Mobile), not a single app with features bolted on. A
  product decision that weakens the platform's coherence costs every
  future product built on it.
- **Practical implications:** When a feature request conflicts with
  platform consistency, the platform's shape wins by default; product
  exceptions require an explicit, documented trade-off, not silent
  deviation.

#### 3. Reuse Before Duplication

- **Why it exists:** Duplicated logic drifts out of sync over time and
  multiplies the surface area an AI agent or human must reason about
  correctly.
- **Practical implications:** Before writing new logic, check whether an
  equivalent capability already exists in the core platform or another
  module. Prefer extending or sharing over copy-pasting. See the AI
  Decision Checklist (`xp-0008`) — "Does this duplicate an existing
  capability?" is a mandatory check before implementation.

#### 4. Documentation Before Implementation

- **Why it exists:** This is the Docs-First Rule from `xp-0000`, restated
  here as a first-class engineering principle rather than only a
  procedural gate: documentation is the specification, not a description
  written after the fact.
- **Practical implications:** No architecture, API, or business rule is
  implemented before its governing `XP-NNNN` document (or ADR) exists and
  is `Approved`. This applies to humans and AI agents identically.

#### 5. Security by Design

- **Why it exists:** Retrofitting security after a system is built is more
  expensive, less reliable, and often incomplete compared to designing it
  in from the start — especially for a platform handling business,
  community, personal, and payment data.
- **Practical implications:** Every design must consider authentication,
  authorization, data exposure, and abuse scenarios at design time, not
  as a follow-up task. Security-relevant decisions are never left as
  implicit assumptions in code.

#### 6. AI Augments Humans

- **Why it exists:** AI agents (Claude Code, Codex, future agents) are
  productivity multipliers acting under human authority, not autonomous
  decision-makers. This principle underlies the entire approval authority
  model in `xp-0001`.
- **Practical implications:** AI agents implement, draft, and review
  faster and more thoroughly than a human alone could — but final
  authority, product vision, and risk acceptance always rest with the
  Founder. An AI agent should never make an irreversible or
  high-consequence decision unilaterally.

#### 7. API-First Thinking

- **Why it exists:** A modular monolith with a mobile client (Flutter) and
  possible future specialized Node.js services only stays coherent if
  every capability is designed as a contract first, implementation
  second.
- **Practical implications:** Design the interface/contract for a
  capability before its internals. Internal modules should be able to
  consume each other, and mobile should be able to consume the platform,
  through the same disciplined contract shape — even before a formal
  `13-api/` document exists.

#### 8. Modular Architecture

- **Why it exists:** A modular monolith gets its benefits (single
  deployable, shared infrastructure, low operational overhead) only if
  its internal modules stay genuinely decoupled. Without discipline, a
  monolith degrades into an undifferentiated ball of mud.
- **Practical implications:** Every module owns its own domain and
  exposes deliberate boundaries to other modules. Reaching across a module
  boundary informally (e.g. directly querying another module's tables) is
  a violation of this principle, not a convenient shortcut.

#### 9. Consistency Over Cleverness

- **Why it exists:** A clever, non-obvious solution saves time once and
  costs time every time someone (human or AI) has to re-understand it
  afterward.
- **Practical implications:** Follow established patterns already present
  in the platform even when a novel approach seems marginally more
  elegant. Introduce a new pattern only when the existing ones are
  genuinely insufficient, and document why.

#### 10. Long-Term Maintainability

- **Why it exists:** XETROIT is being built for a long operating horizon,
  not a single launch. Short-term speed that damages long-term
  maintainability is a false economy.
- **Practical implications:** Prefer designs that are easy to change,
  test, and extend over designs that are merely fast to write once. Code
  and documentation should assume a future maintainer with no memory of
  today's context.

#### 11. Progressive Enhancement

- **Why it exists:** Building the full, final version of a capability
  before validating its core value wastes effort and delays learning.
- **Practical implications:** Start with the smallest coherent version of
  a capability that is still correct and secure, then extend it in
  documented, reviewed increments. This does not excuse skipping
  documentation or security — it governs scope, not rigor.

#### 12. Measurable Quality

- **Why it exists:** "It seems fine" is not a quality bar an AI-assisted
  engineering process can rely on; quality claims must be checkable by
  someone other than the author.
- **Practical implications:** Every capability should have a way to
  verify it works as specified — tests, checks, or explicit manual
  verification steps recorded in its documentation. See the AI Decision
  Checklist (`xp-0008`) — "Is this testable?" is a mandatory check.

## AI Agent Notes

- These principles are the second layer of the Engineering Decision
  Pyramid (`xp-0006`), directly below Founder Vision. When a task's
  instructions are ambiguous, resolve the ambiguity in the direction these
  principles point, then flag the ambiguity rather than silently guessing.
- If a task requires violating one of these principles, treat that as a
  signal to pause and propose an ADR (`xp-0004`) rather than proceeding —
  see `xp-0008-ai-decision-checklist.md` for exactly when to stop.
- Do not treat these principles as platform architecture. They must never
  be used to justify describing or implementing a specific module,
  business rule, or technology stack detail within this document.

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
| 0.1 | 2026-07-02 | Claude Code | Initial draft: twelve engineering principles with rationale and practical implications. |
