# XP-0017 — Organization & Tenancy Domain Architecture

## 1. Purpose

This document defines the constitutional architecture of the
Organization & Tenancy Domain, a domain within the Core Platform
established by `XP-0015 — Core Platform Domain Architecture`. It
continues directly from `XP-0016 — Identity Domain Architecture`: where
`XP-0016` answers *who is this identity*, this document answers *where
does this identity belong, and in what organizational or tenant context
is it operating*. It defines principles, responsibilities, and
boundaries only, without design, implementation, or protocol detail. It
is subordinate to, and does not modify, `XP-0015`, `XP-0016`, or any
other frozen document.

## 2. Why Organization & Tenancy Exists

Every Digital Operating System needs a consistent way to represent a
bounded group — a business, a community, a household, or a future
vertical context — and who belongs to it. Without one shared foundation
for this, each Digital Operating System would invent its own notion of
organizational boundary and membership, producing fragmented and
inconsistent representations of belonging across the platform, in the
same way fragmented identity representation would occur without
`XP-0016`.

Organization & Tenancy exists to be that one, shared foundation for
contextual belonging — consistent with Reuse Before Duplication and
Platform Before Product (`XP-0005`, `XP-0011`, `XP-0012`), and with
`XP-0015`'s naming of Organization & Tenancy as a Core Platform
foundation.

## 3. Scope

Organization & Tenancy owns the universal, platform-level concepts of:

- Organization
- Tenant
- Membership
- Account context
- Organizational boundary
- Tenant boundary
- Context switching
- Organization lifecycle
- Tenant lifecycle
- Invitation into an organization or tenant
- Membership status
- Organizational ownership, at a constitutional level (which identity is
  recognized as controlling an organization or tenant, in the abstract)

That is the entire scope of this domain. It does not extend into
anything context-specific, business-specific, or Digital Operating
System–specific.

## 4. Out of Scope

The following are explicitly outside the Organization & Tenancy Domain:

- **Universal identity and authentication** — these remain the Identity
  Domain (`XP-0016`); this domain does not redefine or extend Identity.
- **Business personas** — employee, customer, vendor, student, patient,
  resident, doctor, teacher, author, reviewer, citizen, or any
  member-specific vertical role.
- **Authorization, RBAC, and permission models or matrices.**
- **Billing ownership and commercial plans.**
- **Product-specific teams, departments, and workflows.**

Each of these belongs to a different Core Platform domain or to an
individual Digital Operating System — never to Organization & Tenancy.

## 5. Architectural Principles

- **Domain Minimalism.** This domain owns only universal platform-level
  organization and tenancy concerns. Any future expansion of its scope
  shall follow the platform's formal architecture governance process —
  never informally, and never as a side effect of convenience.
- **Identity Is Universal; Organization & Tenancy Is Contextual.**
  Identity answers who someone is, once, everywhere. Organization &
  Tenancy answers where they belong, which may differ by context.
- **One Identity, Many Organizations.** A single identity may belong to
  many organizations and tenants simultaneously, without either domain
  needing to model the other's internals.
- **One Organization, Many Digital Operating Systems.** A single
  organization may support multiple Digital Operating Systems at once —
  organizational boundary is not owned by, or specific to, any one of
  them.
- **Tenancy Is a Platform Boundary, Not a Database Strategy.** Tenancy
  is a conceptual boundary of what belongs together on the platform; it
  is not a statement about how data is technically partitioned.
- **Membership Is Not Persona.** Organization membership is not the same
  as employment, customer status, residency, student enrollment, patient
  relationship, or vendor relationship. Those are context-specific
  personas a Digital Operating System layers on top of membership; they
  are not membership itself.
- **Reuse Before Duplication / Loose Coupling (`XP-0005`, `XP-0012`).**
  Organization & Tenancy is built once, as a shared foundation, and
  exposes a stable boundary that other domains and Digital Operating
  Systems depend on without reaching into its internals.

## 6. Core Responsibilities

Organization & Tenancy owns:

- The concept of an organization and a tenant.
- Membership — the relationship between an identity and an organization
  or tenant.
- Account context and context switching between organizations or
  tenants.
- Organizational and tenant boundaries.
- Organization and tenant lifecycle.
- Invitation into an organization or tenant, and membership status.
- Organizational ownership at a constitutional level.

Deliberately, nothing more.

## 7. Non-Responsibilities

Organization & Tenancy is not responsible for:

- Universal identity or authentication (`XP-0016`).
- Any business persona — employee, customer, vendor, student, patient,
  resident, doctor, teacher, author, reviewer, citizen, or
  member-specific vertical role.
- Authorization, RBAC, or permission models.
- Billing ownership or commercial plans.
- Product-specific teams, departments, or workflows.

Roles and permissions are acknowledged as a related, downstream concern —
they are not designed in this document.

## 8. Relationship to Identity

`XP-0016` establishes *who this identity is*, once, universally.
`XP-0017` establishes *where that identity belongs*, contextually, and
that belonging may vary — differently in each organization or tenant an
identity participates in. Organization & Tenancy references Identity
through membership — an organization has members, each of which is an
identity — but it does not redefine, extend, or duplicate any part of
Identity's own concept or its authentication foundation.

The relationship runs in one direction only: Organization & Tenancy
depends on Identity to know who a member is; Identity does not depend on
Organization & Tenancy, and has no awareness of any organization or
tenant an identity may belong to.

## 9. Architectural Dependencies

Organization & Tenancy must remain consistent with, and may not
contradict:

- The Platform Constitution (`XP-0009`, `XP-0011`, `XP-0012`, `XP-0013`).
- `XP-0014 — Platform Architecture Map` — its Architecture Vocabulary and
  canonical five-layer hierarchy.
- `XP-0015 — Core Platform Domain Architecture` — Organization &
  Tenancy's parent domain, its placement in the Capability Map, and its
  foundation/experience boundary principle.
- `XP-0016 — Identity Domain Architecture` — the identity concept
  membership depends on.
- The platform's formal architecture governance process, which governs
  any future expansion of this domain's scope.

## 10. Downstream Consumers

- Every Digital Operating System (Business OS, Community OS, Life OS,
  and any Future Vertical OS) depends on Organization & Tenancy to
  represent bounded groups and membership context — a business in
  Business OS, a community in Community OS, a household context in Life
  OS — each built on the same underlying organization and membership
  foundation rather than a separate one per domain.
- A future Authorization domain will depend on both Identity and
  Organization & Tenancy to establish *who, in what context* before
  deciding what they are permitted to do — Authorization itself remains
  out of scope here.
- A future Commercial or Billing Entitlement domain will reference
  organizations and tenants to scope entitlement, without Organization &
  Tenancy owning billing itself.
- Any Digital Operating System–specific persona (employee, customer,
  patient, or similar) will reference a membership — it will never
  extend or redefine one.

## 11. Organization & Tenancy Within Platform Architecture

Organization & Tenancy's position follows the canonical five-layer
platform hierarchy already established in `XP-0011`, `XP-0012`, and
`XP-0014`, restated here unchanged:

```
Users
      ↓
Digital Operating Systems
      ↓
Shared Ecosystem Services
      ↓
Core Platform
      ↓
Infrastructure
```

Organization & Tenancy is a domain within the Core Platform layer,
corresponding to the Organization & Tenancy grouping named in `XP-0015`'s
Capability Map. It sits alongside Identity (`XP-0016`) at the same
layer — a peer domain, not a subordinate or superior one — depending on
Identity for membership while remaining architecturally distinct from
it.

## 12. Future Documents Unlocked

Once this document is `Approved`:

- An Authorization domain architecture becomes plannable, with Identity
  and Organization & Tenancy as named dependencies.
- A Commercial or Billing Entitlement domain architecture becomes
  plannable, referencing organizations and tenants for entitlement scope.
- Digital Operating System–specific documents describing a business
  persona (employee, resident, customer, or similar) may reference an
  `Approved` Organization & Tenancy foundation for membership.
- Module Architecture, Feature Specification, or Implementation Plan
  documents for Organization & Tenancy itself become authorizable, per
  the Documentation Dependency Order established in `XP-0014`.

No `XP-NNNN` identifier is assigned to any of these here; per
`xp-0000-documentation-governance.md`, a number is assigned only when a
document is registered in `DOCUMENT-INDEX.md`, at the point its work is
explicitly authorized.

## 13. Risks

- **Persona creep.** The greatest risk to this domain is the informal
  addition of business personas — employee, customer, patient, or
  similar — into Organization & Tenancy for convenience. Guardrail: any
  such expansion shall follow the platform's formal architecture
  governance process, never an informal addition.
- **Authorization/RBAC creep.** Membership feels adjacent to permissions,
  creating a temptation to define access rules here. Guardrail:
  Authorization and RBAC remain a future, separate domain; this document
  only acknowledges them as related, downstream concerns.
- **Billing/ownership conflation.** "Organizational ownership" at a
  constitutional level could be mistaken for commercial or billing
  ownership. Guardrail: this document scopes ownership only to which
  identity is recognized as controlling an organization or tenant, in
  the abstract — commercial and billing concerns belong to a future
  Commercial domain.
- **Tenancy-as-implementation.** "Tenant" risks being read as a database
  or technical multi-tenancy strategy rather than a platform-level
  boundary. Guardrail: this document treats tenancy strictly as a
  conceptual boundary, per Section 5.
- **Membership/persona conflation.** "Membership" risks being treated as
  synonymous with a specific persona such as employee or resident.
  Guardrail: this document draws that distinction explicitly, and future
  documents must preserve it.

## 14. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
`XP-0015`, and `XP-0016`. Where anything here ever appears to conflict
with any of them, that document is correct and this one must be revised
to match — never the reverse.

Domain Minimalism applies: any future expansion of the Organization &
Tenancy Domain's scope shall follow the platform's formal architecture
governance process, not an informal revision of this document.

This document follows the established review workflow — CTO, Founder
Review, Claude, CTO Review, Codex, CTO Review, Claude Fixes, Final CTO
Review, Governance Closeout, Freeze — and does not become authoritative
until it completes that process and is registered `Approved` in
`DOCUMENT-INDEX.md`, per `XP-0002`.
