# XP-0028 — Module Composition Principles

## 1. Purpose

This document defines how an already-classified Module — one that
satisfies `XP-0026 — Module Architecture`'s definition and `XP-0027 —
Module Classification Principles`'s criteria — should be architecturally
composed internally, so that it remains cohesive, maintainable, and
stable over the life of the platform. It answers *how* a Module is
structured, at the level of principle only, without redefining what a
Module is, without reclassifying anything, without defining how a
Module is proposed, approved, or retired, and without describing any
implementation, runtime communication, or technology. It is subordinate
to, and does not modify, the Platform Constitution (`XP-0009`,
`XP-0011`, `XP-0012`, `XP-0013`), `XP-0014`, the Core Platform Domain
Architecture (`XP-0015`–`XP-0025`), `XP-0026`, `XP-0027`, or any other
frozen document.

## 2. Why Module Composition Exists

`XP-0026` establishes what a Module is and its boundary, ownership, and
dependency principles. `XP-0027` establishes when a proposed piece of
work qualifies as one. Neither answers how a Module, once it exists,
should be structured internally so that it stays cohesive as it grows —
without one shared understanding of composition, a Module could drift
into absorbing unrelated functions for convenience, or fragment into
pieces too small to be independently meaningful, eroding the very
cohesion `XP-0026` requires and the classification discipline `XP-0027`
establishes.

Module Composition Principles exists to give future architects a
consistent way to structure, decompose, and aggregate Modules — so that
composition decisions are made deliberately, against shared principles,
rather than ad hoc — consistent with Reuse Before Duplication and
Platform Before Product (`XP-0011`, `XP-0012`), and with the Module
Architecture tier `XP-0026` and `XP-0027` already elaborate.

## 3. Relationship to XP-0026

`XP-0026` defines what a Module is: a bounded, cohesive architectural
subdivision within a single, `Approved` Domain Architecture, with its own
ownership, boundary, and dependency principles. This document does not
restate or redefine any of that. It assumes a Module has already been
correctly identified per `XP-0026`, and addresses only how that Module's
internal composition should be shaped and kept stable over time.

The relationship runs in one direction only: this document depends on
`XP-0026`'s definitions; `XP-0026` does not depend on this document, and
remains fully correct and complete without it.

## 4. Relationship to XP-0027

`XP-0027` defines the classification vocabulary — Module, Capability,
Feature, Workflow, Configuration, Shared Ecosystem Service, Core Platform
responsibility — and the criteria for classifying a proposed piece of
work as one of them. This document does not redefine that vocabulary or
those criteria. It builds on them directly: composition is fundamentally
about how a Module's own Capabilities, as `XP-0027` Section 4 defines
them, are placed, grouped, and bounded within it, and about re-applying
`XP-0027`'s classification criteria whenever a Module's composition
changes enough to raise the question of whether its boundary still
holds.

The relationship runs in one direction only: this document depends on
`XP-0027`'s classification vocabulary and criteria; `XP-0027` does not
depend on this document.

## 5. Composition Principles

- A Module is composed of one or more Capabilities, each contributing to
  the single, cohesive function `XP-0026` requires a Module to have.
- Composition describes how a Module's Capabilities relate to and
  reinforce one another within its boundary — it is a structural,
  conceptual description, never an implementation, deployment, or
  runtime-communication design.
- A well-composed Module's Capabilities are mutually reinforcing: removing
  one should weaken the Module's cohesive function, not leave an unrelated
  remainder untouched.
- Composition decisions are architecture decisions. They are made
  deliberately, against the principles in this document, not as an
  incidental byproduct of convenience.

## 6. Cohesion Principles

- Every Capability within a Module must clearly serve that Module's one,
  stated cohesive function, per `XP-0026` Section 3's definition of a
  Module and Section 10's ownership principles.
- A Capability that does not clearly serve the Module's cohesive function
  is a signal, not a foregone conclusion — it does not automatically mean
  the Capability is misplaced, but it warrants re-examination against
  Section 8 (Capability Placement) and, where relevant, Section 9
  (Decomposition).
- Cohesion is judged by business function, per `XP-0026` Section 11's
  boundary test — never by what is easiest to build together.

## 7. Granularity Principles

- Healthy Module granularity sits between two failure modes: a Module
  that has absorbed more than one independently cohesive function
  (too coarse), and a Capability or Feature elevated to full Module
  status when `XP-0027`'s Module Classification Criteria do not support
  it (too fine).
- `XP-0027` Section 5's Module Classification Criteria remain the test
  for granularity: a piece of composition is correctly its own Module
  only if it independently satisfies those criteria, not merely because
  it could be described separately.
- Granularity is re-tested, not assumed permanent — a Module's
  composition may reveal, over time, that its granularity no longer
  fits, which Sections 9 and 10 address.

## 8. Capability Placement Principles

- Before any placement rule below applies, a Capability must first be run
  through `XP-0027`'s full classification criteria, to rule out that it
  is instead a Shared Ecosystem Service, a Core Platform responsibility,
  a Core Platform Module, a separate Module in its own right, a Feature,
  a Workflow, or Configuration. "Place in the most direct Module" is the
  outcome only once all of those have been ruled out — it is never a
  shortcut around them.
- A Capability belongs within the existing Module whose cohesive
  function it serves.
- Where a Capability could plausibly serve more than one existing
  Module's function, and `XP-0027` classification has already ruled out
  the categories above, it belongs within the Module whose cohesive
  function it serves most directly — it is not duplicated across more
  than one.
- A Capability that is genuinely cross-Module, cross-Digital-Operating-
  System, platform-wide, or ecosystem-wide in scope must be reclassified
  through `XP-0027` — it is never forced into a single Module merely
  because it happens to be used from more than one place.
- A Capability becomes a new Module only when it independently satisfies
  `XP-0027`'s Module Classification Criteria on its own terms — never
  because placing it inside an existing Module is inconvenient.
- Capability placement is never decided by implementation, technology,
  or deployment convenience, per `XP-0026` Section 11's boundary
  principle.

## 9. Decomposition Principles

A Module should decompose into two or more Modules when:

- It has accumulated more than one independently cohesive function,
  each of which would independently satisfy `XP-0027`'s Module
  Classification Criteria on its own.
- Different parts of it have diverged in ownership, business purpose, or
  rate of change, such that treating them as one Module obscures rather
  than clarifies their boundary.
- The coupling between its parts is looser than the coupling within each
  part — a sign the "one Module" is really several, per Section 6's
  cohesion test.

Each Module resulting from a decomposition must independently satisfy
`XP-0026`'s definition and `XP-0027`'s classification criteria — a
Module does not decompose into pieces that themselves fail to qualify as
Modules.

This section defines only the architectural criteria for deciding that a
Module should decompose. It does not define how that decomposition is
approved, scheduled, migrated, or governed as a change — those remain
deferred entirely to Module Lifecycle, per Section 12.

## 10. Aggregation Principles

Two or more Modules should aggregate into one when:

- Their apparent independent cohesion turns out to be artificial — they
  consistently change together and serve one combined business function
  rather than two distinct ones.
- Keeping them separate creates coordination overhead between them
  without a genuine ownership or boundary benefit.
- Together, they would still independently satisfy `XP-0026`'s
  definition and `XP-0027`'s classification criteria as a single Module,
  per Sections 6 and 7.

Modules may aggregate only when the resulting Module fits within exactly
one `Approved` parent Domain Architecture, per `XP-0026` Section 3.
Aggregation must never cross a Digital Operating System boundary, a Core
Platform domain boundary, a Digital Operating System/Core Platform
boundary, or a Shared Ecosystem Service boundary — Modules whose parent
Domain Architectures differ do not aggregate, regardless of how related
their functions may appear.

Aggregation is the mirror of decomposition (Section 9), not its
opposite in principle: both are corrections applied when a Module's
granularity no longer matches its actual cohesion, judged by the same
tests.

This section defines only the architectural criteria for deciding that
Modules should aggregate. It does not define how that aggregation is
approved, scheduled, migrated, or governed as a change — those remain
deferred entirely to Module Lifecycle, per Section 12.

## 11. Boundary Stability Principles

- A Module's boundary, once established per `XP-0026`, remains stable by
  default. Composition may refine a Module's internal Capabilities,
  decompose it, or aggregate it with another, but any such change is a
  deliberate architecture decision against Sections 9–10, never an
  incidental drift.
- Every resulting Module, after any composition change, must still
  satisfy `XP-0026`'s definition and `XP-0027`'s classification criteria
  — composition change never grandfathers a boundary that would no
  longer qualify.
- Domain Minimalism applies to composition as it does to definition: a
  Module does not quietly expand its boundary by accumulating
  Capabilities that belong elsewhere, one small addition at a time.
- The ownership distinctions `XP-0026` Section 10 already establishes —
  what a Digital Operating System Module must never own, and what a Core
  Platform Module may refine without redefining its parent — carry over
  unchanged through any composition change described in this document.

This section defines only the architectural criteria for keeping a
Module's boundary stable through composition change. It does not define
how a boundary change is approved, scheduled, migrated, or governed as a
change — those remain deferred entirely to Module Lifecycle, per
Section 12.

## 12. Future Documents Guided

This document guides, without designing, one anticipated next Phase 3
foundation document: **Module Lifecycle** — how a Module is proposed,
approved, evolved in status, and retired over time. Composition, as this
document defines it, describes a Module's internal structure at a point
in time; lifecycle describes the Module's own existence over time. This
document does not define lifecycle in any respect; it is deferred
entirely to that future document.

No `XP-NNNN` identifier is assigned to any future document by this one;
per `DOCUMENT-INDEX.md`'s own registration convention, a number is
assigned only when a document is registered there, at the point its
work is explicitly authorized.

## 13. Risks

- **Composition/lifecycle conflation.** Composition changes (refining,
  decomposing, aggregating) could be mistaken for lifecycle events
  (proposing, approving, retiring). Guardrail: Section 12 states this
  distinction explicitly, and defers lifecycle entirely.
- **Boundary drift through incremental placement.** A Module could
  absorb unrelated Capabilities one small, convenient addition at a
  time. Guardrail: Sections 6, 8, and 11 state the cohesion and
  placement tests explicitly, and Domain Minimalism applies throughout.
- **Premature or unjustified decomposition or aggregation.** Either could
  be applied without re-testing against `XP-0027`'s classification
  criteria. Guardrail: Sections 9 and 10 both require every resulting
  Module to independently satisfy `XP-0026` and `XP-0027`.
- **Coarse-Module risk.** A Module could absorb more than one cohesive
  function for convenience. Guardrail: Section 7 names this failure mode
  explicitly, with Section 9 as the correction.
- **Over-fragmentation risk.** A Capability or Feature could be elevated
  to Module status without independently satisfying `XP-0027`'s
  criteria. Guardrail: Section 7 names this failure mode explicitly,
  with Section 10 as the correction.
- **Implementation drift.** Describing composition invites the
  temptation to describe runtime communication, technology, or
  deployment structure. Guardrail: Section 5 states composition is a
  structural, conceptual description only; implementation remains
  deferred to a future Implementation Plan document.

## 14. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
the Core Platform Domain Architecture (`XP-0015`–`XP-0025`), `XP-0026`,
and `XP-0027`. Where anything here ever appears to conflict with any of
them, that document is correct and this one must be revised to match —
never the reverse. This document does not weaken, reopen, or reorder
`XP-0014`'s frozen Documentation Dependency Order or Domain Architecture
roadmap, and does not redefine anything `XP-0026` or `XP-0027` already
establish.

Domain Minimalism and Document Minimalism apply: any future expansion of
these composition principles, or of this document's own scope, shall
follow the platform's formal architecture governance process, not an
informal revision of this document.

This document follows the established review workflow — CTO, Founder
Review, Claude, CTO Review, Codex, CTO Review, Claude Fixes, Final CTO
Review, Governance Closeout, Freeze — and does not become authoritative
until it completes that process and is registered `Approved` in
`DOCUMENT-INDEX.md`.

**Governance Closeout (2026-07-08):** Having reached `Approved` as part
of the Phase 1 Foundation Closeout (2026-07-07), this document is now
**Frozen** as of 2026-07-08, per Founder decision, completing the review
workflow above as part of the Phase 1 Founder Freeze. Further change
requires a new revision and a fresh review cycle, per `XP-0002`.
