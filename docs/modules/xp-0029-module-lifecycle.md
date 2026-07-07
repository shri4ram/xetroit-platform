# XP-0029 — Module Lifecycle

## 1. Purpose

This document defines how an already-classified, already-composed
Module — one that satisfies `XP-0026 — Module Architecture`'s
definition, `XP-0027 — Module Classification Principles`'s criteria, and
`XP-0028 — Module Composition Principles`'s structure — evolves through
its architectural life, while preserving the Platform Constitution and
the Module foundation those three documents establish. It answers *how a
Module's own architectural existence progresses over time*, at the level
of principle only — without redefining what a Module is, when something
qualifies as one, or how it is composed, and without describing any
software development process, release mechanism, or implementation
detail. It is subordinate to, and does not modify, the Platform
Constitution (`XP-0009`, `XP-0011`, `XP-0012`, `XP-0013`), `XP-0014`, the
Core Platform Domain Architecture (`XP-0015`–`XP-0025`), `XP-0026`,
`XP-0027`, `XP-0028`, or any other frozen document.

## 2. Why Module Lifecycle Exists

A Module does not appear fully formed. It begins as a proposal, becomes
authoritative once approved, may evolve in composition over time, and
may eventually be retired once it no longer serves the function it was
approved for. Without one shared, constitutional understanding of these
stages, future architects would form inconsistent judgments about
whether a proposed Module is real yet, whether an existing Module may
still change, and what happens architecturally when a Module is no
longer needed — risking silent drift, boundary confusion, or the loss of
why a past architectural decision was made.

Module Lifecycle exists to give one shared model for a Module's
architectural existence over time, consistent with Reuse Before
Duplication and Platform Before Product (`XP-0011`, `XP-0012`), and with
the Module Architecture tier `XP-0026`, `XP-0027`, and `XP-0028` already
elaborate.

## 3. Relationship to XP-0026

`XP-0026` defines what a Module is: its identity, boundary, ownership,
and dependency principles. This document does not redefine any of that.
It describes how a Module of that kind moves through its own
architectural life stages — its identity, once established per
`XP-0026`, does not change as it moves through the stages this document
defines.

The relationship runs in one direction only: this document depends on
`XP-0026`'s definitions; `XP-0026` does not depend on this document.

## 4. Relationship to XP-0027

`XP-0027` defines when a proposed piece of work qualifies as a Module.
This document does not redefine that classification test. A Module's
classification must continue to hold at every lifecycle stage this
document defines — it is re-tested wherever this document requires it,
never re-litigated or replaced by it.

The relationship runs in one direction only: this document depends on
`XP-0027`'s classification criteria; `XP-0027` does not depend on this
document.

## 5. Relationship to XP-0028

`XP-0028` defines how a Module is composed, including when it should
decompose or aggregate, and explicitly deferred the question of how such
changes are approved, scheduled, or governed over time to this document.
This document is that deferred document. It does not redefine `XP-0028`'s
composition criteria; it defines when, in a Module's architectural life,
a composition change constitutes legitimate evolution (Section 9) rather
than a new proposal or a boundary violation.

The relationship runs in one direction only: this document depends on
`XP-0028`'s composition criteria; `XP-0028` does not depend on this
document.

## 6. Lifecycle Principles

- A Module's architectural lifecycle is distinct from, though naturally
  correlated with, the document lifecycle status already used throughout
  this repository (Planned, Draft, In Review, Approved, Deprecated,
  Archived, per `DOCUMENT-INDEX.md`'s Status Legend). This document does
  not redefine that status system; it describes a Module's own
  architectural existence, which that system's `Approved`,
  `Deprecated`, and `Archived` states track for its governing document.
- A Module's architectural life has four stages: **Candidate** (Section
  7), **Approved** (Section 8), **Evolving** (Section 9), and **Retired**
  (Section 10).
- Progression between stages follows the platform's formal architecture
  governance process; it is never informal, and never assumed from a
  proposal's existence alone.
- A Module's classification (`XP-0027`) and composition (`XP-0028`) must
  hold at every stage; a stage transition that would violate either is
  not a legitimate transition. At the Candidate stage (Section 7), this
  means the proposal is evaluated against `XP-0027`'s classification
  criteria, and its proposed composition is evaluated against `XP-0028`'s
  composition principles — but nothing about a Candidate becomes
  architecturally authoritative until it reaches Approved (Section 8).

## 7. Candidate Modules

A Candidate Module is a proposed piece of work that appears to satisfy
`XP-0027`'s Module Classification Criteria but has not yet been
formally authorized through an `Approved` Module Architecture document.

A Candidate Module:

- Has no ownership authority — nothing may yet depend on its boundary.
- Enforces no boundary of its own — its proposed boundary is a proposal,
  not yet a constitutional fact.
- May be rejected per `XP-0027` Section 12 at any point before reaching
  `Approved` status, without that rejection constituting retirement
  (Section 10), since a Candidate that is rejected never became a Module
  in the first place.

## 8. Approved Modules

A Module becomes Approved when its own Module Architecture document
reaches `Approved` status in `DOCUMENT-INDEX.md`, consistent with its
parent Domain Architecture already being `Approved`, per `XP-0026`
Section 3.

Once Approved, a Module's boundary, ownership, and classification become
authoritative only as permitted by `XP-0026` and its approved parent
Domain Architecture: it may be referenced exactly to the extent
`XP-0026`'s own dependency principles allow — never as a general license
for arbitrary Module-to-Module dependency, and never implying that a
parent Domain Architecture, Core Platform domain, or Digital Operating
System depends upward on any Module. It remains held to the same
non-negotiable ownership distinctions `XP-0026` Section 10 and `XP-0028`
Section 11 already establish.

## 9. Module Evolution

A Module evolves through refinement, decomposition, or aggregation, per
`XP-0028`. These three cases are not identical in what they preserve:

- **Refinement** — adjusting a Module's internal Capabilities without
  changing its boundary — preserves that Module's identity outright.
- **Decomposition or aggregation** preserve architectural lineage, not
  necessarily the exact prior Module's identity: the resulting Module or
  Modules trace back to what preceded them, but each is its own
  architectural fact, not simply a continuation of the same one under a
  new name.

Every resulting Module, however it arose, must independently satisfy
`XP-0026`'s definition, `XP-0027`'s classification criteria, and
`XP-0028`'s composition principles on its own terms — this document does
not redefine what `XP-0028` already requires of a decomposition or
aggregation, it only states that the result must stand on its own.
Where a resulting Module does not yet have its own `Approved` Module
Architecture document, it re-enters this document's lifecycle as a
Candidate Module (Section 7), and becomes Approved (Section 8) only once
formally authorized in its own right — evolution never grants Approved
status to a resulting Module by inheritance from its predecessor.

Every evolution step must be re-validated against `XP-0026`'s
definition, `XP-0027`'s classification criteria, and `XP-0028`'s
composition principles. A change that fails any of these is not
evolution. Depending on the nature of the failure, it may be rejected
outright, per `XP-0027` Section 12, or, where appropriate, treated as a
new Candidate Module (Section 7) subject to `XP-0027`'s classification
criteria in its own right — a failed evolution does not automatically
become a new proposal in every case.

This section defines only the architectural condition under which a
composition change counts as legitimate evolution. It does not define
how that change is scheduled, migrated, or carried out operationally —
those remain outside this document's scope entirely.

## 10. Module Retirement

A Module is retired when it no longer satisfies `XP-0027`'s Module
Classification Criteria — because its function has been fully absorbed
through aggregation (`XP-0028` Section 10), superseded, or is no longer
needed — or, should future approved architecture ever retire its parent
Domain Architecture, as a consequence of that. No Domain Architecture
lifecycle is defined, assumed, or implied by this document; this
clause is stated only to remain consistent with such a lifecycle, should
one ever be constitutionally established.

Retirement is an architectural determination, not an operational event:
this document does not define any release, deployment, migration, or
operational process for retiring a Module. Once retired, a Module's
boundary is no longer authoritative for new dependencies, but its
historical record is preserved, per Section 11.

## 11. Architectural Continuity

Evolving or retiring a Module does not erase its constitutional history.
Consistent with the `Deprecated` and `Archived` states already available
in `DOCUMENT-INDEX.md`'s Status Legend, a Module's prior `Approved`
architecture remains part of the platform's historical record after
evolution or retirement — a future architect or AI agent can trace why a
boundary changed, not only that it changed.

This document does not define a new mechanism for capturing that
history; `DOCUMENT-INDEX.md` and `CHANGELOG.md` remain the existing
repository mechanisms for it, unchanged by this document.

## 12. Future Documents Guided

No further Phase 3 foundation document is anticipated by this document.
Should one become necessary in the future, it would follow the same
formal architecture governance process `XP-0026` through `XP-0029`
already have, and would be registered in `DOCUMENT-INDEX.md` only once
its work is explicitly authorized.

## 13. Risks

- **Lifecycle-as-process drift.** "Module Lifecycle" invites the
  temptation to describe a software development, release, or project
  management process. Guardrail: Section 1 excludes this explicitly, and
  no section of this document names any development methodology,
  version control system, release mechanism, testing process, or
  deployment pipeline.
- **Silent Candidate promotion.** A Candidate Module could be treated as
  though it were already authoritative before reaching `Approved`
  status. Guardrail: Section 7 states explicitly that a Candidate has no
  ownership authority and enforces no boundary.
- **Evolution used to smuggle boundary violations.** A composition
  change could be labeled "evolution" without being re-validated against
  `XP-0026`–`XP-0028`. Guardrail: Section 9 requires re-validation
  explicitly, and treats a failing change as a new proposal or a
  rejection, never as evolution.
- **Retirement without continuity.** A retired Module's history could be
  lost along with its authority. Guardrail: Section 11 states
  continuity is preserved explicitly, using mechanisms the repository
  already has.
- **Document/architectural lifecycle conflation.** A Module's
  architectural stage could be confused with its governing document's
  lifecycle status. Guardrail: Section 6 states the distinction
  explicitly.

## 14. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
the Core Platform Domain Architecture (`XP-0015`–`XP-0025`), `XP-0026`,
`XP-0027`, and `XP-0028`. Where anything here ever appears to conflict
with any of them, that document is correct and this one must be revised
to match — never the reverse. This document does not weaken, reopen, or
reorder `XP-0014`'s frozen Documentation Dependency Order or Domain
Architecture roadmap, and does not redefine anything `XP-0026`,
`XP-0027`, or `XP-0028` already establish.

Domain Minimalism and Document Minimalism apply: any future expansion of
these lifecycle principles, or of this document's own scope, shall
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
