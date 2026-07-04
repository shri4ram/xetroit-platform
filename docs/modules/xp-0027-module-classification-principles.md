# XP-0027 — Module Classification Principles

## 1. Purpose

This document defines how XETROIT decides whether a proposed piece of
platform work is a Module, a Capability, a Feature, a Workflow,
Configuration, a Shared Ecosystem Service, or a Core Platform
responsibility. It builds directly on `XP-0026 — Module Architecture`,
which defines what a Module is; this document defines *when* a proposed
thing qualifies as one, at the level of classification principle only —
without designing any specific module, capability, feature, workflow, or
configuration, and without introducing any implementation, technology,
or documentation-standard content. It is subordinate to, and does not
modify, the Platform Constitution (`XP-0009`, `XP-0011`, `XP-0012`,
`XP-0013`), `XP-0014`, the Core Platform Domain Architecture
(`XP-0015`–`XP-0025`), `XP-0026`, or any other frozen document.

## 2. Why Module Classification Exists

`XP-0026` establishes what a Module is — a bounded, cohesive
architectural subdivision within a single, `Approved` Domain
Architecture. It does not, by itself, tell a future architect how to
decide whether a specific proposed piece of work actually meets that
definition, or whether it is better described as something narrower
(a Capability, a Feature, a Workflow, or Configuration) or something
broader (a Shared Ecosystem Service or a Core Platform responsibility).

Without one shared, constitutional classification procedure, each future
architect — human or AI — would apply their own judgment inconsistently,
producing Modules that duplicate Core Platform responsibility, Modules
that are really just a Feature or a Workflow dressed up as a new
architectural unit, or Shared Ecosystem Services reinvented separately
inside individual Digital Operating Systems. Module Classification
Principles exists to prevent that fragmentation once, consistent with
Reuse Before Duplication and Platform Before Product (`XP-0011`,
`XP-0012`), and with the Module Architecture tier `XP-0026` already
elaborates.

## 3. Relationship to XP-0026

`XP-0026` defines what a Module is: its boundary, its ownership
principles, its dependency principles, and its two legitimate
categories — Digital Operating System Modules and Core Platform Modules.
This document does not restate or redefine any of that. It adds exactly
one thing `XP-0026` does not: a repeatable classification procedure for
deciding, given a proposed piece of platform work, whether it meets
`XP-0026`'s definition of a Module at all, or whether it belongs to one
of the other classification categories this document defines instead.

The relationship runs in one direction only: this document depends on
`XP-0026`'s definitions; `XP-0026` does not depend on this document, and
remains fully correct and complete without it.

## 4. Classification Vocabulary

For the purpose of consistent classification, this document uses the
following terms:

- **Module** — as defined by `XP-0026`: a bounded, cohesive architectural
  subdivision within a single, `Approved` Domain Architecture.
- **Capability** — a distinct ability or behavior that a Module, a Core
  Platform domain, or a Shared Ecosystem Service provides. Every Module
  has one or more Capabilities; not every Capability warrants its own
  Module.
- **Feature** — a specific piece of behavior and business rule within an
  existing Module, at the level `XP-0014` Section 4 names as the Feature
  Specification tier — one level finer-grained than a Module, never a
  replacement for one.
- **Workflow** — a specific, multi-step business process or approval
  sequence, built using the Process & Events foundation (`XP-0020`) and
  the Workflow capability already named in `XP-0011`, within an existing
  Module or Digital Operating System — not a bounded architectural unit
  of its own.
- **Configuration** — a value, threshold, or setting that is adjustable
  within a governed context, never a new piece of architecture.
  Platform-wide configuration, governed consistently across every
  Digital Operating System, belongs to the Configuration & Policy
  foundation (`XP-0018`). A product-specific setting, a Module-local
  setting, or a Digital Operating System's own business setting remains
  owned by its parent Module or Digital Operating System — not by
  `XP-0018` — unless intentionally elevated to platform-wide
  configuration through approved architecture.
- **Shared Ecosystem Service** — a cross-cutting, ecosystem-wide
  experience, as already described in `XP-0011`, available as an
  ecosystem-wide capability to every Digital Operating System that
  requires it, rather than being exclusively scoped to one.
- **Core Platform responsibility** — a universal, platform-wide
  foundation already owned by one of the ten Core Platform domains
  (`XP-0015`–`XP-0025`).

A proposed piece of work receives one primary architectural
classification from the categories above. This does not mean the
categories never co-occur in practice — a Capability, for instance, may
exist within a Module, a Core Platform domain, or a Shared Ecosystem
Service simultaneously, as a description of what that Module, domain, or
service does — only that the proposal itself, when classified under this
document, is classified once, as the single category that best describes
what is being proposed.

## 5. Module Classification Criteria

A proposed piece of work qualifies as a Module when all of the following
hold:

- It has independent business cohesion — a single, coherent function,
  not a loose bundle of unrelated behaviors.
- Its ownership boundary is distinct from every other Module and from
  any Shared Ecosystem Service, per `XP-0026` Section 11. Where its
  parent Domain Architecture belongs to a Digital Operating System, that
  boundary must also be distinct from every Core Platform domain, and
  must not redefine or expand any of them. Where its parent Domain
  Architecture is a Core Platform domain, it may refine that one,
  approved parent domain — per `XP-0026` Sections 3 and 9 — provided it
  does not redefine, duplicate, or expand that parent domain's own
  boundary.
- It fits within exactly one `Approved` parent Domain Architecture —
  a Digital Operating System's or a Core Platform domain's — per
  `XP-0026` Section 3.
- It is not better described as a Capability, a Feature, a Workflow, or
  Configuration within an existing Module (Sections 6–9), and it is not
  a Shared Ecosystem Service or a Core Platform responsibility instead
  (Sections 10–11).

If a proposed piece of work fails any of these, it is not a Module — see
Section 12.

## 6. Capability Classification Criteria

A proposed piece of work is only a Capability, not a Module, when:

- It describes a single ability or behavior that makes sense as part of
  an existing Module, Core Platform domain, or Shared Ecosystem Service,
  rather than warranting its own bounded architectural unit.
- It lacks independent business cohesion on its own — it is one ability
  among several that together constitute an existing or already-proposed
  Module.
- Naming it as a Module would fragment a single cohesive function across
  multiple architectural units for no reason beyond convenience.

## 7. Feature Classification Criteria

A proposed piece of work is only a Feature, not a Module, when:

- It is a specific behavior or business rule that operates entirely
  within an existing Module's already-established boundary.
- It belongs at the Feature Specification tier `XP-0014` Section 4
  already names, not at the Module Architecture tier.
- Formalizing it as a Module would duplicate the parent Module's
  boundary rather than adding a new one.

## 8. Workflow Classification Criteria

A proposed piece of work is only a Workflow, not a Module, when:

- It is a specific, multi-step business process or approval sequence,
  expressible using the Process & Events foundation (`XP-0020`) and the
  Workflow capability already named in `XP-0011`.
- It coordinates existing capabilities, Modules, or Core Platform
  responsibilities in sequence, rather than introducing a new bounded
  area of ownership.
- Its cohesion comes from the sequence and coordination it performs, not
  from owning a distinct business function of its own.

## 9. Configuration Classification Criteria

A proposed piece of work is only Configuration, not a Module, when:

- It is a value, threshold, rule, or setting, rather than new business
  logic, a new ownership boundary, or a new dependency relationship.
- Where the value is platform-wide and must be governed consistently
  across every Digital Operating System, it belongs to the
  Configuration & Policy foundation (`XP-0018`) — this document does not
  broaden `XP-0018`'s own scope, only recognizes its existing boundary.
- Where the value is product-specific, Module-local, or a Digital
  Operating System's own business setting, it remains owned by its
  parent Module or Digital Operating System, not by `XP-0018`, unless it
  is intentionally elevated to platform-wide configuration through
  approved architecture.
- Treating it as a Module would introduce architecture where a
  configurable value already suffices, regardless of which of the above
  owns it.

## 10. Shared Ecosystem Service Classification

A proposed piece of work is a Shared Ecosystem Service, not a Module,
when:

- It must be available as an ecosystem-wide capability to every Digital
  Operating System that requires it, rather than being exclusively
  scoped to one — shared means universally available, not universally
  consumed.
- It mediates interaction between Digital Operating Systems, or between
  the platform and the world beyond it, consistent with the Shared
  Ecosystem Services layer already described in `XP-0011`.
- Scoping it to a single Digital Operating System as a Module would
  either duplicate it across every other Digital Operating System that
  also needs it, or deny the rest of the platform access to it.

## 11. Core Platform Responsibility Classification

A proposed piece of work is a Core Platform responsibility — not a
Module of any kind — when it would sit at the Core Platform domain
level itself, or would redefine, extend, or expand an existing Core
Platform domain's own boundary (`XP-0015`–`XP-0025`). This is true when:

- It concerns identity, organizational or tenant context, configuration
  or policy, accountability, cross-cutting process or event
  coordination, communication or content infrastructure, external
  connectivity governance, platform-wide insight or governance,
  commercial infrastructure, or the shared experience frame, at the
  level of the domain's own boundary — not a finer-grained piece already
  within an existing domain's authorized scope.
- Every, or nearly every, Digital Operating System needs it, and needs
  it to behave identically, and no existing Core Platform domain already
  owns it.
- Treating it as a Module of any kind would fragment a universal,
  platform-wide concern, or would require expanding a Core Platform
  domain's frozen boundary beyond what `XP-0015`–`XP-0025` already
  authorize.

This is distinct from a **Core Platform Module**, which `XP-0026`
already permits: a finer-grained sub-scope inside an already-`Approved`
Core Platform domain, authorized by that domain's own document,
refining rather than expanding or redefining it (`XP-0026` Sections 3
and 9). A proposed piece of work meeting that description is classified
as a Module (Section 5) — specifically a Core Platform Module — not
rejected as a Core Platform responsibility under this section.

A Digital Operating System Module must never own any Core Platform
responsibility described above, per `XP-0026` Section 10. That
restriction is unaffected by the existence of Core Platform Modules,
which belong to the Core Platform, never to any Digital Operating
System.

## 12. Rejection Criteria

A proposed Module should be rejected — and reclassified per Sections
6–11 — when any of the following apply:

- It is better classified as a Capability, a Feature, a Workflow, or
  Configuration within an existing Module, per Sections 6–9.
- It claims unauthorized Core Platform ownership, duplicates a Core
  Platform domain's responsibility inside a Digital Operating System
  Module, or redefines or expands an existing Core Platform domain's own
  boundary or an existing Shared Ecosystem Service, per Sections 10–11 —
  this does not apply to a Core Platform Module that merely refines an
  already-`Approved` Core Platform domain's own authorized scope, which
  `XP-0026` and Section 11 permit.
- It has no `Approved` parent Domain Architecture to belong to — per
  `XP-0026` Section 3, a Module cannot exist without one.
- Its proposed boundary is defined by implementation convenience rather
  than business cohesion, per `XP-0026` Section 11.
- It would overlap another Module's ownership within the same parent
  Domain Architecture.
- It names a specific product, industry, or vertical as if that naming
  alone justified Module status, without first satisfying Section 5's
  criteria.

## 13. Classification Examples

These examples are illustrative and hypothetical only — they name no
real module, capability, feature, or product, and authorize nothing:

- A proposed piece of work that only adjusts a numeric threshold used
  elsewhere in an existing Module is Configuration (Section 9), not a
  Module.
- A proposed piece of work that only sequences three already-existing
  capabilities through an approval step is a Workflow (Section 8), not a
  Module.
- A proposed piece of work that is available as an ecosystem-wide
  capability to every Digital Operating System that requires it, rather
  than being exclusively scoped to one, and lets them exchange something
  with each other, is a Shared Ecosystem Service (Section 10), not a
  Module.
- A proposed piece of work that governs who is recognized as acting,
  regardless of which Digital Operating System they are in, is a Core
  Platform responsibility (Section 11), not a Module.
- A proposed piece of work with a single cohesive business function,
  its own ownership boundary, and an `Approved` parent Domain
  Architecture to belong to is a Module (Section 5).

## 14. Future Documents Guided

This document guides, without designing, two anticipated next Phase 3
foundation documents:

- **Module Composition** — how multiple Modules relate to and coordinate
  with one another once classified. Not defined here; deferred entirely
  to that future document.
- **Module Lifecycle** — how a Module is proposed, approved, evolved, and
  retired over time. Not defined here; deferred entirely to that future
  document.

No `XP-NNNN` identifier is assigned to any future document by this one;
per `DOCUMENT-INDEX.md`'s own registration convention, a number is
assigned only when a document is registered there, at the point its
work is explicitly authorized.

## 15. Risks

- **Classification drift.** Different architects could apply Sections
  5–11 inconsistently over time. Guardrail: this document states the
  criteria once, constitutionally, rather than leaving classification to
  ad hoc judgment.
- **Module-as-default.** Proposers may default to calling everything a
  Module because it sounds more significant than Capability, Feature,
  Workflow, or Configuration. Guardrail: Section 12's rejection criteria
  exist specifically to catch this.
- **Premature specificity.** Classification Examples (Section 13) could
  drift into naming a real product or vertical. Guardrail: Section 13
  states explicitly that its examples are hypothetical and authorize
  nothing.
- **Composition/lifecycle creep.** This document could be tempted to
  define how Modules relate to each other or evolve over time. Guardrail:
  Section 14 defers both explicitly to future documents.
- **Core Platform/Shared Ecosystem Service misclassification.** A
  proposal that is genuinely platform-wide could be scoped as a Module to
  avoid the scrutiny of Core Platform or Shared Ecosystem Service review.
  Guardrail: Sections 10–11 state the test explicitly, and Section 12
  names this as rejection grounds.

## 16. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
the Core Platform Domain Architecture (`XP-0015`–`XP-0025`), and
`XP-0026`. Where anything here ever appears to conflict with any of
them, that document is correct and this one must be revised to match —
never the reverse.

Domain Minimalism and Document Minimalism apply: any future expansion of
these classification criteria, or of this document's own scope, shall
follow the platform's formal architecture governance process, not an
informal revision of this document. This document does not weaken,
reopen, or reorder `XP-0014`'s frozen Documentation Dependency Order or
Domain Architecture roadmap, and does not redefine anything `XP-0026`
already establishes.

This document follows the established review workflow — CTO, Founder
Review, Claude, CTO Review, Codex, CTO Review, Claude Fixes, Final CTO
Review, Governance Closeout, Freeze — and does not become authoritative
until it completes that process and is registered `Approved` in
`DOCUMENT-INDEX.md`.
