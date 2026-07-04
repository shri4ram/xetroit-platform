# XP-0018 — Configuration & Policy Domain Architecture

## 1. Purpose

This document defines the constitutional architecture of the
Configuration & Policy Domain, a domain within the Core Platform
established by `XP-0015 — Core Platform Domain Architecture`. It
continues directly from `XP-0016 — Identity Domain Architecture` and
`XP-0017 — Organization & Tenancy Domain Architecture`: where `XP-0016`
answers *who is this identity*, and `XP-0017` answers *where does this
identity belong, and in what organizational or tenant context is it
operating*, this document answers *what rules and configurable
conditions apply within that context*. It defines principles,
responsibilities, and boundaries only, without design, implementation,
or protocol detail. It is subordinate to, and does not modify, `XP-0015`,
`XP-0016`, `XP-0017`, or any other frozen document.

## 2. Why Configuration & Policy Exists

Every Digital Operating System needs a consistent way to represent
platform-controlled adjustable values and enforceable platform rules
that apply within a valid identity and organizational context. Without
one shared foundation for this, each Digital Operating System would
invent its own notion of a setting and its own notion of a rule,
producing fragmented and inconsistently enforced configuration and
policy across the platform, in the same way fragmented identity or
fragmented organizational representation would occur without `XP-0016`
and `XP-0017`.

Configuration & Policy exists to be that one, shared foundation for
platform-level configurable conditions and platform-governed rules —
consistent with Reuse Before Duplication and Platform Before Product
(`XP-0005`, `XP-0011`, `XP-0012`), and with `XP-0015`'s naming of
Configuration & Policy as a Core Platform foundation, formed from the
Shared Configuration and Policy Enforcement foundations described in
`XP-0015` Section 12.

## 3. Scope

Configuration & Policy owns the universal, platform-level concepts of:

- Configuration boundary
- Policy boundary
- Default values
- Inherited configuration
- Tenant-scoped configuration
- Organization-scoped configuration
- Override rules
- Policy applicability
- Policy enforcement responsibility, at a constitutional level (which
  layer of the platform is recognized as responsible for enforcing a
  policy, in the abstract)
- Configuration governance
- Policy governance

That is the entire scope of this domain. It does not extend into
anything context-specific, business-specific, or Digital Operating
System–specific.

## 4. Out of Scope

The following are explicitly outside the Configuration & Policy Domain:

- **Universal identity and authentication** — these remain the Identity
  Domain (`XP-0016`); this domain does not redefine or extend Identity.
- **Organizations, tenants, and membership** — these remain the
  Organization & Tenancy Domain (`XP-0017`); this domain does not
  redefine organizational or tenant boundaries, only references them as
  the context configuration and policy may be scoped within.
- **Authorization, RBAC, roles, and permission models or matrices.**
- **Workflow design or workflow implementation.**
- **Notification design or implementation.**
- **Billing plans and commercial entitlements.**
- **AI behavior, prompts, or AI-specific configuration.**
- **Product-specific settings** — any setting whose meaning only exists
  within one Digital Operating System.
- **User preferences**, except to the extent a universal, platform-level
  preference is already defined by another frozen document; this domain
  does not itself define user preferences.
- **Domain-specific business rules** — any rule whose meaning only
  exists within one Core Platform domain or one Digital Operating
  System.

Each of these belongs to a different Core Platform domain, a future
domain, or an individual Digital Operating System — never to
Configuration & Policy.

## 5. Architectural Principles

- **Domain Minimalism.** This domain owns only universal platform-level
  configuration and policy concerns. Any future expansion of its scope
  shall follow the platform's formal architecture governance process —
  never informally, and never as a side effect of convenience.
- **Identity Is Universal; Organization & Tenancy Is Contextual;
  Configuration & Policy Is Conditional.** Identity answers who someone
  is, once, everywhere. Organization & Tenancy answers where they
  belong, which may differ by context. Configuration & Policy answers
  what rules and configurable conditions apply once identity and context
  are established — it presupposes both and adds neither.
- **Configuration Is Not Arbitrary Settings.** A configuration is a
  platform-controlled, adjustable value that shapes behavior within a
  valid platform context — not any value any domain wishes to store.
  This domain does not become a generic settings bucket for concerns
  that belong elsewhere.
- **Policy Is Not RBAC.** A policy is a platform-governed rule
  determining what is allowed, required, restricted, or enforced. Roles
  and permissions decide what a specific identity may do; that decision
  belongs to a future Authorization domain, not to this one.
- **Policy Is Not Workflow.** A policy states a constraint or
  requirement; it does not define the sequence of steps, states, or
  automation that carries a process forward. Workflow remains a separate
  foundation.
- **Context Determines Applicability.** Configuration and policy have no
  meaning in isolation — they apply within a context that Identity and
  Organization & Tenancy establish. This domain depends on that context;
  it does not create it.
- **Reuse Before Duplication / Loose Coupling (`XP-0005`, `XP-0012`).**
  Configuration & Policy is built once, as a shared foundation, and
  exposes a stable boundary that other domains and Digital Operating
  Systems depend on without reaching into its internals.

## 6. Core Responsibilities

Configuration & Policy owns:

- The concept of a configuration boundary and a policy boundary.
- Default values, and the concept of inherited configuration.
- Tenant-scoped and organization-scoped configuration, as configurable
  conditions applying within the boundaries `XP-0017` defines.
- Override rules, at a constitutional level.
- Policy applicability — the concept of what a policy may govern.
- Policy enforcement responsibility, at a constitutional level.
- Configuration governance and policy governance.

Deliberately, nothing more.

## 7. Non-Responsibilities

Configuration & Policy is not responsible for:

- Universal identity or authentication (`XP-0016`).
- Organizations, tenants, or membership (`XP-0017`).
- Authorization, RBAC, roles, or permission models.
- Workflow design or implementation.
- Notification design or implementation.
- Billing plans or commercial entitlements.
- AI behavior, prompts, or AI-specific configuration.
- Product-specific settings owned by a Digital Operating System.
- User preferences, beyond universal platform-level preferences already
  defined by another frozen document.
- Domain-specific business rules owned by another Core Platform domain
  or a Digital Operating System.

Roles and permissions are acknowledged as a related, downstream concern —
they are not designed in this document. Policy may, in the future,
constrain authorization or workflow; designing authorization or workflow
themselves is not part of this document.

## 8. Relationship to Identity

`XP-0016` establishes *who this identity is*, once, universally.
Configuration and policy may apply differently depending on who is
acting, but this domain does not redefine, extend, or duplicate any part
of Identity's own concept or its authentication foundation. Where a
policy's applicability depends on identity, this domain references
Identity only as established context — it does not decide who an
identity is, and it does not decide what a specific identity is
authorized to do.

The relationship runs in one direction only: Configuration & Policy may
reference Identity to know that a configuration or policy applies to an
identity's action; Identity does not depend on Configuration & Policy,
and has no awareness of any configuration or policy that may apply to
it.

## 9. Relationship to Organization & Tenancy

`XP-0017` establishes *where an identity belongs, and in what
organizational or tenant context it is operating*. Configuration &
Policy defines the rules and configurable conditions that may apply
within that context — tenant-scoped and organization-scoped
configuration are configurable values scoped to the boundaries `XP-0017`
defines, not a redefinition of those boundaries. This domain does not
create organizational or tenant boundaries; it presupposes them.

The relationship runs in one direction only: Configuration & Policy
depends on Organization & Tenancy to know what context a configuration
or policy is scoped to; Organization & Tenancy does not depend on
Configuration & Policy, and has no awareness of any configuration or
policy that may apply within its boundaries.

## 10. Architectural Dependencies

Configuration & Policy must remain consistent with, and may not
contradict:

- The Platform Constitution (`XP-0009`, `XP-0011`, `XP-0012`, `XP-0013`).
- `XP-0014 — Platform Architecture Map` — its Architecture Vocabulary and
  canonical five-layer hierarchy.
- `XP-0015 — Core Platform Domain Architecture` — Configuration &
  Policy's parent domain, its placement in the Capability Map, its
  foundation/experience boundary principle, and its Section 12
  description of the Configuration and Policy Foundation.
- `XP-0016 — Identity Domain Architecture` — the identity concept
  configuration and policy applicability may reference as context.
- `XP-0017 — Organization & Tenancy Domain Architecture` — the
  organizational and tenant boundaries configuration and policy may be
  scoped within.
- The platform's formal architecture governance process, which governs
  any future expansion of this domain's scope.

## 11. Downstream Consumers

- Every Digital Operating System (Business OS, Community OS, Life OS,
  and any Future Vertical OS) depends on Configuration & Policy for a
  shared configuration and policy boundary, each built on the same
  underlying foundation rather than a separate one per domain.
  Product-specific settings remain owned by the Digital Operating System
  that defines them, layered on top of this foundation rather than
  replacing it.
- A future Authorization domain will reference policy applicability to
  understand what constraints a policy may impose, without
  Configuration & Policy designing authorization or RBAC itself.
- A future Workflow foundation will reference policy enforcement
  responsibility where a workflow must respect a platform rule, without
  Configuration & Policy designing workflow itself.
- A future Commercial or Billing Entitlement domain may reference
  tenant-scoped or organization-scoped configuration to determine what
  configurable conditions an entitlement affects, without Configuration
  & Policy owning billing or entitlement itself.
- Any Digital Operating System–specific setting or business rule will
  reference the configuration or policy boundary defined here — it will
  never extend or redefine it.

## 12. Configuration & Policy Within Platform Architecture

Configuration & Policy's position follows the canonical five-layer
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

Configuration & Policy is a domain within the Core Platform layer,
corresponding to the Configuration & Policy grouping named in
`XP-0015`'s Capability Map. It sits alongside Identity (`XP-0016`) and
Organization & Tenancy (`XP-0017`) at the same layer — a peer domain,
not a subordinate or superior one — depending on both for the context it
conditions, while remaining architecturally distinct from each.

## 13. Future Documents Unlocked

Once this document is `Approved`:

- An Authorization domain architecture becomes plannable, with Identity,
  Organization & Tenancy, and Configuration & Policy as named
  dependencies.
- A Workflow foundation architecture becomes plannable, referencing
  policy enforcement responsibility as a named dependency.
- A Commercial or Billing Entitlement domain architecture becomes
  plannable, referencing tenant-scoped and organization-scoped
  configuration for entitlement-driven configuration.
- Digital Operating System–specific documents describing product-specific
  settings may reference an `Approved` Configuration & Policy foundation
  for the configuration and policy boundary they build on top of.
- Module Architecture, Feature Specification, or Implementation Plan
  documents for Configuration & Policy itself become authorizable, per
  the Documentation Dependency Order established in `XP-0014`.

No `XP-NNNN` identifier is assigned to any of these here; per
`xp-0000-documentation-governance.md`, a number is assigned only when a
document is registered in `DOCUMENT-INDEX.md`, at the point its work is
explicitly authorized.

## 14. Risks

- **Generic settings bucket.** The greatest risk to this domain is
  becoming a catch-all for any value any domain wishes to store.
  Guardrail: a configuration is a platform-controlled, adjustable value
  that shapes behavior within a valid platform context, per Section 5 —
  not an arbitrary setting, and any expansion of what qualifies shall
  follow the platform's formal architecture governance process.
- **RBAC/policy conflation.** Policy applicability feels adjacent to
  permissions, creating a temptation to define access rules here.
  Guardrail: Authorization and RBAC remain a future, separate domain;
  this document only acknowledges them as a related, downstream concern.
- **Workflow conflation.** Policy enforcement responsibility feels
  adjacent to process design, creating a temptation to define workflow
  steps or automation here. Guardrail: this document states policy as a
  constraint only, never a sequence of steps or states.
- **User preference creep.** "Configuration" risks being read broadly
  enough to absorb user-level preferences. Guardrail: user preferences
  remain out of scope except where a universal, platform-level
  preference is already defined by another frozen document, per Section
  4.
- **Product-specific settings creep.** Convenience may tempt a Digital
  Operating System's product-specific setting to be defined here instead
  of within that Digital Operating System. Guardrail: product-specific
  settings belong to the relevant Digital Operating System; this domain
  owns only the universal boundary they are layered on top of.
- **Configuration-as-implementation.** "Configuration boundary,"
  "inherited configuration," and "override rules" risk being read as a
  database schema or config file design rather than constitutional
  concepts. Guardrail: this document treats each strictly as a
  conceptual boundary; schema, file format, and implementation mechanism
  are deferred to a future Module Architecture or Implementation Plan
  document.

## 15. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
`XP-0015`, `XP-0016`, and `XP-0017`. Where anything here ever appears to
conflict with any of them, that document is correct and this one must be
revised to match — never the reverse.

Domain Minimalism applies: any future expansion of the Configuration &
Policy Domain's scope shall follow the platform's formal architecture
governance process, not an informal revision of this document.

This document follows the established review workflow — CTO, Founder
Review, Claude, CTO Review, Codex, CTO Review, Claude Fixes, Final CTO
Review, Governance Closeout, Freeze — and does not become authoritative
until it completes that process and is registered `Approved` in
`DOCUMENT-INDEX.md`, per `XP-0002`.
