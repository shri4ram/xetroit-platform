# XP-0020 — Process & Events Domain Architecture

## 1. Purpose

This document defines the constitutional architecture of the Process &
Events Domain, a domain within the Core Platform established by
`XP-0015 — Core Platform Domain Architecture`. It elaborates the Process
Foundation named in `XP-0015`'s Capability Map, and the Workflow
capability already named at the Constitution tier in `XP-0011` and
reconciled in `XP-0015` Section 7, at the level of constitutional
architecture — principles, responsibilities, and boundaries — without
design, protocol, or implementation detail. Unlike `XP-0016` through
`XP-0019`, Process & Events is a cross-cutting Core Platform service
domain: it coordinates business activity across other domains rather
than establishing a new foundational context of its own. It is
subordinate to, and does not modify, `XP-0015`, `XP-0016`, `XP-0017`,
`XP-0018`, `XP-0019`, or any other frozen document.

## 2. Why Process & Events Exists

Every Digital Operating System needs a consistent way to represent
governed, multi-step business progression, and a consistent way to
recognize that something meaningful has happened on the platform, so
that other domains and systems can coordinate around it. Without one
shared foundation for this, each Digital Operating System would build
its own ad hoc notion of a process and its own notion of what counts as
a meaningful occurrence, producing fragmented, duplicated coordination
logic across the platform — the same fragmentation `XP-0016` through
`XP-0019` already guard against for identity, context, rules, and
accountability.

Process & Events exists to be that one, shared foundation for governed
process progression and meaningful platform facts — consistent with
Reuse Before Duplication and Platform Before Product (`XP-0005`,
`XP-0011`, `XP-0012`), with the Workflow capability already named in
`XP-0011`, and with `XP-0015`'s naming of the Process Foundation as a
Core Platform foundation.

## 3. Scope

Process & Events owns the universal, platform-level concepts of:

- Process boundary — what constitutes a governed unit of business
  progression, in the abstract.
- Process progression — the concept of a process moving through
  meaningful stages toward completion.
- Event boundary — what constitutes a meaningful platform fact, in the
  abstract.
- Event meaning — the constitutional distinction between a meaningful
  platform fact and an arbitrary technical signal.
- The relationship between process and event — that a process
  progresses through, and is marked by, meaningful events.
- Cross-domain coordination responsibility, at a constitutional level —
  which layer of the platform is responsible for recognizing that
  business activity spans more than one domain or Digital Operating
  System.
- The boundary between platform-level, reusable coordination
  infrastructure and business-specific workflow logic.

That is the entire scope of this domain. It does not extend into
anything context-specific, business-specific, or Digital Operating
System–specific.

## 4. Out of Scope

The following are explicitly outside the Process & Events Domain:

- **Universal identity and authentication** — these remain the Identity
  Domain (`XP-0016`); this domain does not redefine or extend Identity.
- **Organizations, tenants, and membership** — these remain the
  Organization & Tenancy Domain (`XP-0017`); this domain does not
  redefine organizational or tenant boundaries.
- **Configuration and policy definition** — these remain the
  Configuration & Policy Domain (`XP-0018`); this domain does not decide
  what rules apply.
- **Accountability, auditability, and evidence** — these remain the
  Trust & Accountability Domain (`XP-0019`); this domain does not decide
  what remains attributable or traceable, it only participates within
  that boundary.
- **Business-specific workflows** — any workflow whose steps, stages, or
  rules only make sense within one Digital Operating System's domain.
- **UI flow and screen sequencing** — the order in which a person
  navigates an interface is a presentation concern, not a governed
  business process.
- **Queue, broker, or messaging infrastructure** — any specific
  technology for transporting or delivering an event.
- **Event schema or payload design.**
- **Workflow engine or automation mechanism implementation.**
- **Approval engine implementation.**
- **Notification delivery** — reaching a person with information about
  an event remains a separate communication concern.
- **Billing, commercial, or entitlement processes** — the commercial
  meaning of a process remains outside this domain.

Each of these belongs to a different Core Platform domain, a future
domain, or an individual Digital Operating System — never to Process &
Events.

## 5. Core Responsibilities

Process & Events owns:

- The concept of a process boundary and governed process progression.
- The concept of an event boundary and what qualifies, architecturally,
  as a meaningful platform fact.
- The constitutional relationship between process and event.
- Cross-domain coordination responsibility, at a constitutional level.
- The boundary between platform-level, reusable coordination
  infrastructure and Digital Operating System–specific workflow logic.

Deliberately, nothing more.

## 6. Non-Responsibilities

Process & Events is not responsible for:

- Universal identity or authentication (`XP-0016`).
- Organizations, tenants, or membership (`XP-0017`).
- Configuration or policy definition (`XP-0018`).
- Accountability, auditability, or evidence (`XP-0019`).
- Business-specific workflows owned by a Digital Operating System.
- UI flow or screen sequencing.
- Queue, broker, or messaging infrastructure.
- Event schema or payload design.
- Workflow engine or automation mechanism implementation.
- Approval engine implementation.
- Notification delivery.
- Billing, commercial, or entitlement processes.

Process & Events coordinates business activity; it does not own any
individual domain's business logic, and it must not become a dumping
ground into which any domain's workflow is placed for convenience.

## 7. Relationship to Foundational Domains

Process & Events depends on all four foundational Core Platform domains
as established context. It does not bypass any of them, and it does not
redefine, extend, or duplicate any part of what they own.

- **Identity (`XP-0016`).** Every process is attributable to an identity
  that initiates or progresses it, and every event is attributable to
  the identity, if any, responsible for the fact it represents. Process
  & Events references Identity to know who a process or event is
  attributable to; it does not decide who an identity is.
- **Organization & Tenancy (`XP-0017`).** Every process is scoped to an
  organizational or tenant context, and every event occurs within one.
  Process & Events references that context to know where a process or
  event belongs; it does not define organizational or tenant boundaries.
- **Configuration & Policy (`XP-0018`).** A process's progression and an
  event's recognition may be conditioned by applicable configuration and
  policy. Process & Events references those rules as a governing
  condition; it does not decide what the rules are.
- **Trust & Accountability (`XP-0019`).** A process's progression and
  the events that mark it remain attributable and traceable. Process &
  Events relies on that accountability boundary; it does not decide what
  remains attributable, and it does not own evidence responsibility.

The relationship runs in one direction only: Process & Events depends on
all four foundational domains to coordinate governed business activity;
none of them depends on Process & Events, and none has any awareness of
the process or event coordination that may occur on top of it.

## 8. Process Model

A process, as this domain defines it, is a governed unit of business
progression — a bounded sequence of meaningful stages moving toward a
recognized outcome, always attributable to an identity, scoped to an
organizational or tenant context, subject to applicable configuration
and policy, and accountable throughout its progression. A process
represents governed business progression, not a UI flow: the order in
which a person navigates screens is a presentation concern, while a
process is the underlying business progression that presentation may
reflect, but which exists independently of any particular interface.

This domain owns only the constitutional concept that a process exists,
progresses through stages, and reaches an outcome, and that this
progression is always grounded in the foundational domains named in
Section 7. It does not define what any specific process's stages are,
how many processes exist, or what any particular Digital Operating
System's process looks like — those remain business-specific concerns
owned by the Digital Operating System, or implementation concerns
deferred to a future Module Architecture or Implementation Plan
document.

## 9. Event Model

An event, as this domain defines it, is a meaningful platform fact — a
discrete, attributable occurrence recognized as significant enough that
another domain or Digital Operating System may need to coordinate
around it. An event describes that something happened, not how it was
transported, stored, or delivered; it is a platform fact, not a
technical implementation message such as a queue entry, a log line, or
a database change notification.

Not every internal occurrence within a domain's own implementation
qualifies as an event in this domain's sense — only a fact recognized as
meaningful across a domain or Digital Operating System boundary does.
Each domain remains the authoritative source of the meaning of a fact
that arises within its own boundary; Process & Events does not redefine
what a fact means to the domain it originates from. This domain owns
only the cross-cutting model for how such facts are recognized as
meaningful and how they relate to governed process progression — that a
process may progress through, and be marked by, a sequence of events —
not the ownership, content, or delivery of any specific event.

## 10. Workflow and Automation Boundaries

Process & Events owns the platform-level, reusable boundary for
coordinating governed business progression — the constitutional concepts
established in Sections 3, 8, and 9 — as a foundation every Digital
Operating System may build on. It does not own business-specific
workflow logic. Vertical Operating Systems may define their own
workflows, with their own stages, rules, and automation, on top of this
foundation; what belongs here is only the platform-level coordination
rules that apply regardless of which Digital Operating System is
involved — what qualifies as a process, what qualifies as an event, and
how both remain grounded in the foundational domains named in Section 7.

Where automation, including AI-driven automation, contributes to a
process's progression or to the recognition of an event, that
contribution remains subject to the accountability boundary already
established by `XP-0019` — automation does not grant itself decision
authority beyond what remains attributable to a human or a responsible
platform layer. This document defines no workflow engine, automation
mechanism, or specific automation capability; those remain deferred to a
future Module Architecture or Implementation Plan document.

## 11. Cross-Domain Coordination Rules

- Process & Events may reference another domain's declared
  constitutional boundary — an identity, an organizational or tenant
  context, an applicable configuration or policy, an accountability
  boundary — as context for coordinating a process or recognizing an
  event, but it may never redefine what that boundary means to the
  domain that owns it.
- Process & Events may recognize that a meaningful fact occurred within
  another domain's boundary, without owning that domain's data, logic,
  or internal design.
- Coordination is scoped to what is genuinely cross-cutting — business
  activity that spans more than one domain or more than one Digital
  Operating System. A concern that is entirely internal to a single
  domain's own boundary does not become a process merely because it is
  sequential or stage-like.
- Process & Events must not become a dumping ground for another domain's
  workflow. A workflow concern that belongs entirely within one domain's
  boundary is not elevated into this domain for convenience.
- No domain depends on Process & Events for its own internal
  correctness. Each foundational domain named in Section 7 remains fully
  correct and complete on its own; Process & Events adds coordination on
  top of them, and is never a required intermediary for a domain to
  fulfill its own responsibility.

## 12. Risks

- **Workflow dumping ground.** The greatest risk to this domain is
  absorbing business-specific workflow logic that belongs to a Digital
  Operating System, simply because it is process-shaped. Guardrail:
  Section 6 and Section 11 state this explicitly; any such expansion
  shall follow the platform's formal architecture governance process,
  never an informal addition.
- **Technical-message conflation.** "Event" risks being read as a queue
  message, a log entry, or a database change notification rather than a
  meaningful platform fact. Guardrail: Section 9 draws this distinction
  explicitly, and future documents must preserve it.
- **UI-flow conflation.** "Process" risks being read as screen
  sequencing or navigation order. Guardrail: Section 8 states explicitly
  that a process represents governed business progression, not a UI
  flow.
- **Foundational bypass.** Coordinating a process or recognizing an
  event without properly grounding it in Identity, Organization &
  Tenancy, Configuration & Policy, or Trust & Accountability would
  produce ungoverned, unaccountable coordination. Guardrail: Section 7
  states that this domain depends on all four foundational domains and
  must never bypass them.
- **Automation authority creep.** Automation contributing to a process
  or an event could be mistaken as having decision authority of its own.
  Guardrail: Section 10 states that any automation remains subject to
  the accountability boundary already established by `XP-0019`.
- **Cross-domain overreach.** The coordination role of this domain could
  be mistaken as license to reach into another domain's internal design.
  Guardrail: Section 11 permits reference to another domain's declared
  boundary only, never to its internals.

## 13. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
`XP-0015`, `XP-0016`, `XP-0017`, `XP-0018`, and `XP-0019`. Where anything
here ever appears to conflict with any of them, that document is correct
and this one must be revised to match — never the reverse.

Domain Minimalism applies: any future expansion of the Process & Events
Domain's scope shall follow the platform's formal architecture
governance process, not an informal revision of this document.

This document follows the established review workflow — CTO, Founder
Review, Claude, CTO Review, Codex, CTO Review, Claude Fixes, Final CTO
Review, Governance Closeout, Freeze — and does not become authoritative
until it completes that process and is registered `Approved` in
`DOCUMENT-INDEX.md`, per `XP-0002`.
