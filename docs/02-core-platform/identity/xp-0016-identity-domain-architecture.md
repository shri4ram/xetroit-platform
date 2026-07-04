# XP-0016 — Identity Domain Architecture

## 1. Purpose

This document defines the constitutional architecture of the Identity
Domain, a domain within the Core Platform established by
`XP-0015 — Core Platform Domain Architecture`. It elaborates the
Identity foundation named in `XP-0015`'s Capability Map at the level of
constitutional architecture — principles, responsibilities, and
boundaries — without design, protocol, or implementation detail. It is
subordinate to, and does not modify, `XP-0015` or any other frozen
document. This document is intended to become the constitutional
reference for all future Identity architecture.

## 2. Why Identity Exists

Every interaction on the platform, in every Digital Operating System,
depends on being able to recognize that the same actor is the same actor
wherever they appear — in a business context, a community context, a
personal context, or any future vertical context. Without one shared
foundation for this, each Digital Operating System would invent its own
notion of "who someone is," producing fragmented, duplicated, and
inconsistent representations of the same person across the platform.

Identity exists to be that one, minimal, universal foundation —
consistent with Reuse Before Duplication and Platform Before Product
(`XP-0005`, `XP-0011`, `XP-0012`), and with `XP-0015`'s naming of Identity
as a Core Platform foundation.

## 3. Scope

Identity's scope is deliberately narrow. It owns exactly two things:

- The universal, product-agnostic concept of **an identity** — a single,
  canonical way of recognizing that the same person or actor is the same
  actor everywhere they appear on the platform.
- **Authentication** — the foundation for verifying that recognition.

That is the entire scope of the Identity Domain. It does not extend into
anything context-specific, business-specific, or Digital Operating
System–specific.

## 4. Out of Scope

The following are explicitly outside the Identity Domain:

- **Authorization** — what an identity is permitted to do. This is a
  separate domain in its own right, depending on Identity but not part
  of it.
- **User Management** — broader account, profile, and preference
  concerns beyond the minimal identity concept.
- **Organizations, memberships, roles, permissions.**
- **Business-context concepts** describing what an identity *is* within
  a specific Digital Operating System — employee, customer, vendor,
  student, patient, resident, or any similar concept.

Each of these belongs to a different Core Platform domain or to an
individual Digital Operating System — never to Identity.

## 5. Architectural Principles

- **Domain Minimalism.** Identity remains intentionally minimal. Any
  future expansion of the Identity Domain shall follow the platform's
  formal architecture governance process — never informally, and never
  as a side effect of convenience.
- **Product-Agnosticism.** Identity has no awareness of any specific
  Digital Operating System's business concepts, workflows, or
  terminology.
- **One Identity, Many Contexts.** A single identity may participate in
  many contexts, across many Digital Operating Systems, simultaneously —
  without Identity itself needing to know what any of those contexts
  are.
- **Reuse Before Duplication / Platform Before Product (`XP-0005`).**
  Identity is built once, as a shared foundation, precisely so that no
  Digital Operating System builds its own version.
- **Loose Coupling (`XP-0012`).** Identity exposes a stable boundary to
  everything above it; it does not reach into Authorization,
  Organizations, or any Digital Operating System's concerns, and nothing
  above it reaches into Identity's internal shape.

## 6. Core Responsibilities

Identity owns:

- The universal, minimal concept of an identity — a consistent way of
  recognizing that the same actor is the same actor, everywhere on the
  platform.
- Authentication — the foundation for verifying an identity.

Deliberately, nothing more. This minimalism is itself a constitutional
commitment, not an oversight.

## 7. Non-Responsibilities

Identity is not responsible for:

- Authorization — permissions and what an identity may do.
- User Management — profiles, preferences, and account settings beyond
  the minimal identity concept.
- Organizations or Memberships.
- Any business-context concept — employee, customer, vendor, student,
  patient, resident, or similar.

Identity is not User Management, and it must not be treated as such by
any future document or design.

## 8. Architectural Dependencies

The Identity Domain must remain consistent with, and may not contradict:

- The Platform Constitution (`XP-0009`, `XP-0011`, `XP-0012`, `XP-0013`).
- `XP-0014 — Platform Architecture Map` — its Architecture Vocabulary and
  canonical five-layer hierarchy.
- `XP-0015 — Core Platform Domain Architecture` — Identity's parent
  domain, its placement in the Capability Map, and its foundation/
  experience boundary principle.
- The platform's formal architecture governance process, which governs
  any future expansion of the Identity Domain's scope.

## 9. Downstream Consumers

- Every Digital Operating System (Business OS, Community OS, Life OS,
  and any Future Vertical OS) depends on Identity to recognize who is
  acting, consistent with `XP-0012` and `XP-0015`.
- A future Authorization domain will depend on Identity to establish
  *who* before deciding *what they are permitted to do* — Authorization
  itself remains out of scope here.
- A future domain covering Organizations and Memberships will reference
  Identity to represent who belongs where, without Identity needing to
  know about organizations.
- Any Digital Operating System–specific business concept (employee,
  customer, patient, or similar) will reference an Identity — it will
  never extend or redefine one.

## 10. Identity Within Platform Architecture

Identity's position follows the canonical five-layer platform hierarchy
already established in `XP-0011`, `XP-0012`, and `XP-0014`, restated here
unchanged:

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

Identity is a domain within the Core Platform layer — part of the
Identity & Access grouping named in `XP-0015`'s Capability Map. This
document narrows that grouping: Identity, as defined here, covers the
identity concept and Authentication only. Authorization, also named
alongside Identity in `XP-0015`'s Capability Map, is treated as a
distinct future domain that depends on Identity rather than being part
of it — consistent with `XP-0015` Section 21, which already lists
Identity and Authorization / Permissions as separate downstream
candidates.

## 11. Future Documents Unlocked

Once this document is `Approved`:

- An Authorization domain architecture becomes plannable, with Identity
  as one of its named dependencies.
- Module Architecture, Feature Specification, or Implementation Plan
  documents for Identity itself become authorizable, per the
  Documentation Dependency Order established in `XP-0014`.
- Digital Operating System–specific documents may reference an
  `Approved` Identity foundation wherever they need to represent who is
  acting.

No `XP-NNNN` identifier is assigned to any of these here; per
`xp-0000-documentation-governance.md`, a number is assigned only when a
document is registered in `DOCUMENT-INDEX.md`, at the point its work is
explicitly authorized.

## 12. Risks

- **Scope creep.** The greatest risk to this domain is the informal
  return of Authorization, User Management, or business-context
  concepts into Identity for convenience. Guardrail: any such expansion
  shall follow the platform's formal architecture governance process,
  never an informal addition.
- **Premature protocol framing.** Discussing Authentication in the
  abstract risks implicitly assuming a specific mechanism. Guardrail:
  all such detail is deferred to a future Module Architecture or
  Implementation Plan document.
- **Identity / User Management conflation.** "Identity" risks being used
  loosely to mean a user account or profile. Guardrail: this document
  draws that distinction explicitly, and future documents must preserve
  it.
- **Multi-context complexity.** Because one identity participates in
  many contexts, context-specific concerns could gradually leak into
  Identity's definition without a deliberate decision. Guardrail: the
  same formal architecture governance process applies.

## 13. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
and `XP-0015`. Where anything here ever appears to conflict with any of
them, that document is correct and this one must be revised to match —
never the reverse.

Any future expansion of the Identity Domain shall follow the platform's
formal architecture governance process, not an informal revision of
this document.

This document follows the established review workflow — CTO, Founder
Review, Claude, CTO Review, Codex, CTO Review, Claude Fixes, Final CTO
Review, Governance Closeout, Freeze — and does not become authoritative
until it completes that process and is registered `Approved` in
`DOCUMENT-INDEX.md`, per `XP-0002`.
