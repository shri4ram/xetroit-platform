# XP-0024 — Commercial Domain Architecture

## 1. Purpose

This document defines the constitutional architecture of the Commercial
Domain, a domain within the Core Platform established by `XP-0015 —
Core Platform Domain Architecture`. It elaborates the Commercial
Foundation named in `XP-0015`'s Capability Map — the Payments foundation
and the Billing Entitlement foundation — and the Payments capability
already named at the Constitution tier in `XP-0011`, at the level of
constitutional architecture — principles, responsibilities, and
boundaries — without design, implementation, or tooling detail.
Commercial is a Supporting Foundation of the Core Platform: like
`XP-0020` through `XP-0023`, it provides reusable capability that
Digital Operating Systems draw on rather than establishing a new
foundational context of its own, and it depends on the foundational and
service-oriented domains that precede it without redefining any of
them. It is subordinate to, and does not modify, `XP-0015`, `XP-0016`,
`XP-0017`, `XP-0018`, `XP-0019`, `XP-0020`, `XP-0021`, `XP-0022`,
`XP-0023`, or any other frozen document.

## 2. Why Commercial Exists

Every Digital Operating System needs a consistent way to move and record
money safely, and a consistent way to track what an organization or
person is entitled to as a result of commercial activity. Without one
shared foundation for this, each Digital Operating System would build
its own notion of a payment and its own notion of entitlement,
producing fragmented and inconsistent commercial capability across the
platform — the same fragmentation `XP-0016` through `XP-0023` already
guard against for identity, context, rules, accountability, process,
communication, connectivity, and insight.

Commercial exists to be that one, shared foundation for reusable
commercial capability — consistent with Reuse Before Duplication and
Platform Before Product (`XP-0005`, `XP-0011`, `XP-0012`), with the
Payments capability already named in `XP-0011`, and with `XP-0015`'s
naming of the Payments Foundation and Billing Entitlement Foundation as
Core Platform foundations, reconciled in `XP-0015` Section 7: Payments
Foundation moves and records money; Billing Entitlement Foundation
manages what an organization or person is entitled to as a result.

## 3. Scope

Commercial owns the universal, platform-level concepts of:

- Commercial capability boundary — what constitutes a governed, reusable
  commercial capability, in the abstract.
- Payment infrastructure boundary — the concept that money may be moved
  and recorded safely, as a reusable foundation, independent of what
  business activity it supports.
- Billing entitlement boundary — the concept of tracking what an
  organization or person is entitled to as a result of commercial
  activity, independent of what that entitlement is used for.
- Commercial actor reference — that commercial activity is always
  attributable to an actor, grounded in Identity.
- Commercial ownership reference — that commercial activity is always
  scoped to an organizational or tenant boundary, grounded in
  Organization & Tenancy.
- Reusable commercial capability responsibility, at a constitutional
  level — that commercial capability exists once, shared across every
  current and future Digital Operating System, rather than rebuilt by
  each.

That is the entire scope of this domain. It does not extend into
anything context-specific, business-specific, or Digital Operating
System–specific.

## 4. Out of Scope

The following are explicitly outside the Commercial Domain:

- **Universal identity and authentication** — these remain the Identity
  Domain (`XP-0016`); this domain does not redefine or extend Identity.
- **Organizations, tenants, and membership** — these remain the
  Organization & Tenancy Domain (`XP-0017`); this domain does not
  redefine organizational or tenant boundaries.
- **Configuration and policy definition** — these remain the
  Configuration & Policy Domain (`XP-0018`); this domain does not decide
  what commercial rules apply.
- **Accountability, auditability, and evidence** — these remain the
  Trust & Accountability Domain (`XP-0019`); this domain does not decide
  what remains attributable or traceable.
- **Process and event coordination** — these remain the Process & Events
  Domain (`XP-0020`); this domain does not decide what qualifies as a
  process or an event.
- **Communication and content** — these remain the Communication &
  Content Domain (`XP-0021`); commercial communications such as
  invoices, receipts, reminders, and notices are governed there, not
  here.
- **External connection governance** — this remains the Connectivity
  Domain (`XP-0022`); external commercial integrations are governed
  there, not here.
- **Commercial visibility and decision support** — these remain the
  Insight & Governance Domain (`XP-0023`); this domain does not own
  reporting or governance of commercial activity.
- **Business strategy** — what business model a Digital Operating System
  runs is never decided here.
- **Pricing strategy for Vertical Operating Systems** — what a Digital
  Operating System charges, and how, is never decided here.
- **Accounting or ERP** — general ledger, financial reporting, and
  enterprise resource planning remain outside this domain.
- **Payment gateway implementation.**
- **Legal or tax implementation.**
- **Inventory, procurement, payroll, or operational finance.**
- **The ecosystem-wide commerce experience** — per `XP-0015` Section 7
  and Section 20, this domain provides reusable payment and entitlement
  infrastructure only; any ecosystem-wide commerce or marketplace
  experience remains at the Shared Ecosystem Services layer, a distinct
  layer this document does not reach into.

Each of these belongs to a different Core Platform domain, a different
platform layer, a future domain, or an individual Digital Operating
System — never to Commercial.

## 5. Core Responsibilities

Commercial owns:

- The concept of a commercial capability boundary.
- The payment infrastructure boundary — that money may be moved and
  recorded safely, as a reusable foundation.
- The billing entitlement boundary — that entitlement resulting from
  commercial activity may be tracked, as a reusable foundation.
- Reusable commercial capability responsibility, at a constitutional
  level.

Deliberately, nothing more.

## 6. Non-Responsibilities

Commercial is not responsible for:

- Universal identity or authentication (`XP-0016`).
- Organizations, tenants, or membership (`XP-0017`).
- Configuration or policy definition (`XP-0018`).
- Accountability, auditability, or evidence (`XP-0019`).
- Process or event coordination (`XP-0020`).
- Communication or content, including commercial communications
  (`XP-0021`).
- External connection governance (`XP-0022`).
- Commercial visibility or decision support (`XP-0023`).
- Business strategy or pricing strategy for any Digital Operating
  System.
- Accounting, ERP, payment gateway implementation, legal or tax
  implementation, inventory, procurement, payroll, or operational
  finance.

Commercial provides reusable commercial capability; it does not own
business strategy, pricing strategy, accounting, ERP, payment gateway
implementation, legal or tax implementation, or operational finance, and
it must not absorb any of these for convenience.

## 7. Relationship to Foundational Domains

Commercial depends on all four foundational Core Platform domains as
established context. It does not bypass any of them, and it does not
redefine, extend, or duplicate any part of what they own.

- **Identity (`XP-0016`).** Identity governs commercial actors.
  Commercial references Identity to know who a commercial actor is; it
  does not decide who an identity is.
- **Organization & Tenancy (`XP-0017`).** Organization & Tenancy governs
  commercial ownership boundaries. Commercial references that boundary
  to know which organization or tenant commercial activity is scoped to;
  it does not define organizational or tenant boundaries.
- **Configuration & Policy (`XP-0018`).** Configuration & Policy governs
  configurable commercial rules and policies. Commercial operates within
  those rules; it does not decide what the rules are.
- **Trust & Accountability (`XP-0019`).** Trust & Accountability governs
  commercial accountability and auditability. Commercial relies on that
  accountability boundary; it does not decide what remains attributable
  or traceable, and it does not own evidence responsibility.

The relationship runs in one direction only: Commercial depends on all
four foundational domains to provide governed commercial capability;
none of them depends on Commercial, and none has any awareness of the
commercial activity that may occur on top of it.

## 8. Relationship to Process & Events

`XP-0020` establishes that Process & Events governs business
progression. Commercial provides capability — moving and recording
money, tracking entitlement — that a process may use, but Process &
Events governs commercial process progression: the stages a billing
cycle, a payment, or an entitlement change moves through. Commercial
does not decide what qualifies as a process or an event, and Process &
Events does not decide what a commercial capability is or how it is
provided.

The relationship runs in one direction only: a process may progress
using Commercial's capability; Process & Events does not depend on
Commercial for its own correctness, and Commercial does not own the
progression of any process that uses it.

## 9. Relationship to Communication & Content

`XP-0021` establishes that Communication & Content governs messages and
reusable content. Commercial activity may create a need for commercial
communication — an invoice, a receipt, a reminder, a notice — but
Communication & Content governs the structure, delivery boundary, and
consistency of that communication. Commercial does not own message or
content structure, and Communication & Content does not own the
commercial fact that created the need for the communication.

The relationship runs in one direction only: Commercial may create a
need for communication; Communication & Content does not depend on
Commercial for its own correctness, and has no awareness of the
commercial capability that created the need.

## 10. Relationship to Connectivity

`XP-0022` establishes that Connectivity governs external connection
trust, ownership, and rules. Commercial activity may require reaching an
external commercial capability or service, but Connectivity governs
that connection. Commercial does not own connection trust, ownership, or
rules, and Connectivity does not own what commercial capability the
connection is used for.

The relationship runs in one direction only: Commercial may rely on a
connection Connectivity governs; Connectivity does not depend on
Commercial, and has no awareness of the commercial activity a connection
may support.

## 11. Relationship to Insight & Governance

`XP-0023` establishes that Insight & Governance governs platform-level
visibility and decision support. Insight & Governance may observe and
aggregate commercial activity into a governed view, but Commercial
retains ownership of the meaning of its own data. Commercial does not
own reporting, dashboards, or governance of commercial activity, and
Insight & Governance does not own or redefine any commercial capability.

The relationship runs in one direction only: Insight & Governance may
observe commercial activity; Commercial does not depend on Insight &
Governance for its own correctness, and has no awareness of any governed
view built from it.

## 12. Commercial Model

Commercial, as this domain defines it, is reusable, platform-level
infrastructure for two related concerns: moving and recording money
safely, and tracking what an organization or person is entitled to as a
result. Both are grounded in the foundational domains named in Section
7 — always attributable to an actor, scoped to an organizational or
tenant boundary, subject to applicable configuration and policy, and
accountable throughout.

Commercial does not own business strategy or pricing strategy. What
business model a Digital Operating System runs, and what it charges, are
decisions that Digital Operating System makes for itself, consuming the
shared commercial capability this domain provides rather than building
its own version of payment movement or entitlement tracking. This domain
owns only the reusable capability boundary; it does not own what any
Digital Operating System does with it.

## 13. Commercial Capability Boundaries

Commercial owns the platform-level, reusable boundary for payment
infrastructure and billing entitlement — the constitutional concepts
established in Sections 3 and 12 — as a foundation every current and
future Digital Operating System may build on. It does not own any
specific implementation of that capability. Accounting, ERP, payment
gateway selection, tax engines, and legal or compliance procedure are
not designed here, and are not owned by this domain at all — they belong
to a Digital Operating System, a future specialized domain, or an
implementation concern deferred to a future Module Architecture or
Implementation Plan document.

Commercial capabilities must remain reusable across every current and
future Digital Operating System. A capability that only makes sense for
one Digital Operating System's business model does not belong in this
domain, regardless of how commercial it appears.

## 14. Cross-Domain Coordination Rules

- Commercial may reference another domain's declared constitutional
  boundary — an identity, an organizational or tenant context, an
  applicable configuration or policy, an accountability boundary, a
  triggering process or event, a communication need, a connection, a
  governed view — as context for providing commercial capability, but it
  may never redefine what that boundary means to the domain that owns
  it.
- Commercial may create a need that another domain fulfills — a
  communication, a connection, a governed view — without owning what
  that domain provides in response.
- Coordination is scoped to what is genuinely reusable commercial
  capability — payment infrastructure and entitlement tracking that
  applies regardless of which Digital Operating System is involved. A
  concern that is entirely internal to one Digital Operating System's
  business model does not become Commercial merely because money is
  involved.
- Commercial must not become the owner of business strategy, pricing
  strategy, accounting, ERP, payment gateway implementation, legal or
  tax implementation, or operational finance. A concern that belongs
  entirely within another domain's or Digital Operating System's
  boundary is not elevated into this domain for convenience.
- No domain depends on Commercial for its own internal correctness. Each
  foundational domain named in Section 7, Process & Events, Communication
  & Content, Connectivity, and Insight & Governance remain fully correct
  and complete on their own; Commercial adds reusable commercial
  capability on top of them, and is never a required intermediary for a
  domain to fulfill its own responsibility.

## 15. Risks

- **Business/pricing strategy absorption.** The greatest risk to this
  domain is drifting from reusable commercial infrastructure into
  deciding business strategy or pricing strategy on behalf of a Digital
  Operating System. Guardrail: Section 6, Section 12, and Section 13
  state this explicitly; any such expansion shall follow the platform's
  formal architecture governance process, never an informal addition.
- **Accounting/ERP creep.** "Commercial" invites the informal addition
  of general ledger, financial reporting, or enterprise resource
  planning ownership. Guardrail: Section 4 and Section 13 exclude
  accounting and ERP explicitly.
- **Payment gateway implementation drift.** Providing payment
  infrastructure invites the temptation to select or design a specific
  gateway. Guardrail: Section 13 states that implementation, including
  gateway selection, is deferred to a future Module Architecture or
  Implementation Plan document.
- **Legal/tax implementation creep.** Commercial activity is adjacent to
  legal and tax obligations, creating a temptation to own their
  implementation. Guardrail: Section 4 excludes legal and tax
  implementation explicitly; this domain provides infrastructure only.
- **Operational finance absorption.** Inventory, procurement, and
  payroll are adjacent to money movement, creating a temptation to fold
  them in. Guardrail: Section 4 and Section 6 exclude these explicitly.
- **Ecosystem-commerce conflation.** This domain's reusable payment and
  entitlement infrastructure could be mistaken for the ecosystem-wide
  commerce experience described in `XP-0011`. Guardrail: Section 4
  states explicitly, per `XP-0015` Section 7 and Section 20, that the
  ecosystem-wide commerce experience remains at the Shared Ecosystem
  Services layer, outside this domain.
- **Foundational bypass.** Providing commercial capability without
  properly grounding it in Identity, Organization & Tenancy,
  Configuration & Policy, or Trust & Accountability would produce
  unattributed, unowned, ungoverned, or unaccountable commercial
  activity. Guardrail: Section 7 states that this domain depends on all
  four foundational domains and must never bypass them.

## 16. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
`XP-0015`, `XP-0016`, `XP-0017`, `XP-0018`, `XP-0019`, `XP-0020`,
`XP-0021`, `XP-0022`, and `XP-0023`. Where anything here ever appears to
conflict with any of them, that document is correct and this one must be
revised to match — never the reverse.

Domain Minimalism applies: any future expansion of the Commercial
Domain's scope shall follow the platform's formal architecture
governance process, not an informal revision of this document.

This document follows the established review workflow — CTO, Founder
Review, Claude, CTO Review, Codex, CTO Review, Claude Fixes, Final CTO
Review, Governance Closeout, Freeze — and does not become authoritative
until it completes that process and is registered `Approved` in
`DOCUMENT-INDEX.md`, per `XP-0002`.
