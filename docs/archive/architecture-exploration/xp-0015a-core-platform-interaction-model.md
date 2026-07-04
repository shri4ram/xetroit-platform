# XP-0015A — Core Platform Interaction Model

## 1. Purpose

This document is a lightweight constitutional bridge between
`XP-0015 — Core Platform Domain Architecture` and the individual Core
Platform Domain documents it names — `XP-0016 — Identity Domain
Architecture` onward. It defines how Core Platform Domains may relate
to, depend on, and interact with one another, at the level of principle
and pattern only, without domain-specific design or implementation
detail. It introduces no new domain, changes nothing in `XP-0015`, and
changes nothing in the approved meanings of `XP-0016` through `XP-0019`.
It is subordinate to, and does not modify, any frozen document.

## 2. Why This Interaction Model Exists

`XP-0015` names Core Platform's foundations and groups them in a
Capability Map. `XP-0016` through `XP-0019` each define one domain's own
purpose, scope, and boundary in isolation. Between them, no frozen
document yet states how these domains are permitted to relate to one
another as a system — what dependency direction is allowed, what kind of
reference between domains is legitimate, and what coupling is forbidden.

Without that shared model, each future domain document, and everything
built from it, would be left to invent its own assumption about how
domains connect — producing the same kind of fragmentation across the
Core Platform that `XP-0016` through `XP-0019` already guard against
within their own individual boundaries. This document exists to close
that gap once, as a shared interaction model, consistent with Reuse
Before Duplication, Loose Coupling, and Domain Minimalism (`XP-0005`,
`XP-0012`).

## 3. Relationship to XP-0015

This document does not redefine, duplicate, or extend `XP-0015`. It
presupposes `XP-0015`'s Capability Map (Section 8), its foundation/
experience boundary principle (Section 7), and its naming of each
foundation area, unchanged. Where `XP-0015` names *what* Core Platform
owns, this document names *how* the pieces `XP-0015` already named are
permitted to relate to one another. It sits one level below `XP-0015` —
narrower than the whole of Core Platform — and one level above each
individual domain document, which alone defines what a given domain is.
Nothing here overrides `XP-0015`'s Capability Map groupings or its
Section 21 list of future document candidates.

## 4. Foundational Core Platform Domains

Four Core Platform domains form the foundation the rest of the platform
is built on, each answering one constitutional question in sequence:

- **Identity** (`XP-0016`) — *Who are you?*
- **Organization & Tenancy** (`XP-0017`) — *Where do you belong?*
- **Configuration & Policy** (`XP-0018`) — *What rules apply?*
- **Trust & Accountability** (`XP-0019`) — *How is trust preserved and
  accountability maintained?*

Each of these four questions presupposes the answer to the one before
it: belonging is meaningless without an identity that belongs; rules
are meaningless without knowing whose context they apply within; and
accountability is meaningless without an identity, a context, and a rule
to be accountable to. This ordering is not introduced here — it is
already established individually in each domain's own "Relationship to"
sections. This document restates it once, as a single model, so it does
not need to be re-derived from four separate documents each time it
matters.

## 5. Behavioral and Service-Oriented Core Platform Domains

The remaining groups already named in `XP-0015`'s Capability Map
introduce platform *behavior* and platform *services*, rather than the
foundational context Section 4 describes:

- **Process & Events** — corresponding to the Process Foundation
  (Workflow foundation) grouping.
- **Communication & Content** — corresponding to the Communication &
  Content Foundation grouping.
- **Connectivity** — corresponding to the Connectivity (Integration
  foundation) grouping.
- **Insight & Governance** — corresponding to the Observability and
  Intelligence Governance groupings.
- **Commercial** — corresponding to the Commercial Foundation grouping.
- **Platform Experience** — corresponding to the Platform Experience
  Foundation grouping.

These are not new domains. Each is the same foundation area `XP-0015`
already named, referred to here by a consistent label so this document
can describe how it relates to the four foundation domains in Section 4.
None of them is designed, scoped, or bounded here — each remains a
candidate for its own future constitutional architecture document, per
`XP-0015` Section 21 and the Documentation Dependency Order established
in `XP-0014`.

## 6. Dependency Direction Principles

- **Foundation before behavior.** A behavioral or service-oriented
  domain (Section 5) may depend on a foundation domain (Section 4);
  a foundation domain may never depend on a behavioral or
  service-oriented domain.
- **Ordered foundation dependency.** Within the foundation layer,
  dependency flows in one direction, following the sequence in Section
  4: Identity depends on nothing; Organization & Tenancy depends on
  Identity; Configuration & Policy depends on Identity and Organization
  & Tenancy; Trust & Accountability depends on Identity, Organization &
  Tenancy, and Configuration & Policy. No step in this sequence depends
  on a step that follows it — each domain's own "Relationship to"
  sections already establish this individually; this principle only
  states it as one ordering.
- **Identity remains upstream.** Identity is depended upon by every
  other Core Platform domain and remains unaware of all of them,
  consistent with `XP-0016`.
- **No upward dependency beyond Core Platform.** No Core Platform
  domain, foundation or behavioral, may depend upward on a Shared
  Ecosystem Service or a Digital Operating System, consistent with
  `XP-0015` Section 7. Dependency flows downward through the platform
  hierarchy only.

## 7. Allowed Interaction Patterns

- A domain may reference another domain's declared constitutional
  boundary as context for its own responsibility — for example,
  referencing an identity, an organizational boundary, a configuration
  boundary, or an accountability boundary — without redefining it.
- A domain may depend on any domain positioned earlier in the dependency
  direction established in Section 6.
- A domain may be a named downstream consumer of another domain, exactly
  as already declared in that domain's own "Downstream Consumers"
  section.
- Two domains at the same layer — two foundation domains, or two
  behavioral/service-oriented domains — may coexist as peers without
  either depending on the other, each depending only on the foundation
  domains beneath it.

## 8. Forbidden Coupling Patterns

- No domain may redefine, extend, or duplicate another domain's core
  concept. A behavioral or service-oriented domain must never redefine
  what an identity, an organization, a configuration, or an
  accountability record is.
- No foundation domain may depend on a behavioral or service-oriented
  domain, in either direction.
- No domain may reach into another domain's internal design — only its
  declared constitutional boundary is a legitimate point of reference.
- No domain may absorb another domain's responsibility for convenience.
  A domain becoming a "dumping ground" for a responsibility that belongs
  to another domain is a forbidden pattern regardless of how minor the
  convenience appears.
- No circular dependency between any two domains is permitted, at any
  layer.

## 9. Domain Boundary Protection

Domain Minimalism, already established individually in `XP-0016`
through `XP-0019`, applies across the whole of Core Platform as a single
rule: each domain owns exactly what its own frozen document states, and
nothing else. Any expansion of a domain's scope, or any blending of two
domains' responsibilities, requires the platform's formal architecture
governance process — never an informal decision made in a future
domain document, an implementation detail, or this interaction model
itself. This document grants no exception to that rule for any domain
named in Section 4 or Section 5, and introduces none of its own.

## 10. Interaction Examples

The following examples are conceptual only, intended to illustrate the
patterns in Sections 6–8. They describe no implementation, schema,
service, or sequence of technical steps:

- An action taken by an identity, within an organization, is evaluated
  against the configuration and policy applicable to that context, and
  the outcome remains attributable and accountable afterward — Identity,
  Organization & Tenancy, Configuration & Policy, and Trust &
  Accountability are each referenced in the order established in
  Section 4, with none of them redefining another.
- A future Communication & Content domain reaching a recipient
  references an identity and an organizational context as the "who" and
  "where" it addresses, without redefining either concept.
- A future Commercial domain scoping an entitlement references an
  organization or tenant boundary already defined by Organization &
  Tenancy, without owning membership or redefining that boundary itself.
- A future Insight & Governance domain observing platform activity
  references the accountability boundary Trust & Accountability already
  defines, without owning evidence responsibility or redefining what
  counts as accountable.

## 11. Future Documents Guided

This document guides, without designing, the future constitutional
architecture documents for each behavioral and service-oriented domain
named in Section 5, and any future foundation-adjacent domain already
acknowledged as a related concern within `XP-0016` through `XP-0019`
(such as a future Authorization domain). Each such future document must
state its own relationship to the foundation domains consistent with the
dependency direction established in Section 6, in the same manner
`XP-0017` through `XP-0019` already do for the domains preceding them.

No `XP-NNNN` identifier is assigned to any of these here; per
`xp-0000-documentation-governance.md`, a number is assigned only when a
document is registered in `DOCUMENT-INDEX.md`, at the point its work is
explicitly authorized.

## 12. Risks

- **Dependency inversion.** The greatest risk to this model is a
  behavioral or service-oriented domain quietly redefining a foundation
  concept it depends on, inverting the dependency direction established
  in Section 6. Guardrail: Section 8 forbids this explicitly, and any
  future domain document must be checked against it before approval.
- **Convenience coupling.** A future domain may be tempted to absorb a
  responsibility that belongs to another domain because it is easier
  than referencing it. Guardrail: Section 8's prohibition on
  "dumping ground" coupling applies regardless of convenience.
- **Premature design.** Describing interaction patterns invites the
  temptation to sketch an API, event payload, or sequencing detail to
  illustrate them. Guardrail: Section 10's examples are held to a
  conceptual level only; any technical illustration belongs to a future
  Module Architecture or Implementation Plan document.
- **Relabeling confusion.** The six behavioral and service-oriented
  groupings in Section 5 could be mistaken for newly introduced domains
  rather than restatements of groupings `XP-0015` already named.
  Guardrail: Section 5 states explicitly that these are not new domains,
  and this document assigns none of them a number or a design.
- **Peer-domain circularity.** Two behavioral or service-oriented
  domains, once designed independently in the future, could each come to
  depend on the other. Guardrail: Section 8's prohibition on circular
  dependency applies at every layer, not only between foundation
  domains.

## 13. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
`XP-0015`, `XP-0016`, `XP-0017`, `XP-0018`, and `XP-0019`. Where anything
here ever appears to conflict with any of them, that document is correct
and this one must be revised to match — never the reverse.

Domain Minimalism applies: any future expansion of any Core Platform
domain's scope, or any change to the dependency direction and
interaction patterns established here, shall follow the platform's
formal architecture governance process, not an informal revision of this
document.

This document follows the established review workflow — CTO, Founder
Review, Claude, CTO Review, Codex, CTO Review, Claude Fixes, Final CTO
Review, Governance Closeout, Freeze — and does not become authoritative
until it completes that process and is registered `Approved` in
`DOCUMENT-INDEX.md`, per `XP-0002`.
