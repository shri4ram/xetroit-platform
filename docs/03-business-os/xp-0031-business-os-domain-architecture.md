# XP-0031 — Business Operating System Domain Architecture

## 1. Purpose

This document establishes the Domain Architecture for **Business OS** —
one of the five major architectural domains `XP-0014` Section 6
identifies, and the first of the four Digital Operating System instances
its Section 9 roadmap anticipates. It applies the constitutional contract
`XP-0030 — Digital Operating System Architecture` establishes for every
Digital Operating System specifically to the domain of running a
business, at the level of purpose, architectural scope, responsibilities,
boundaries, relationships, dependency rules, composition rules, and
governance rules only — without designing any capability, workflow, API,
user interface, database, implementation, or deployment detail. It is
subordinate to, and does not modify, the Platform Constitution (`XP-0009`,
`XP-0011`, `XP-0012`, `XP-0013`), `XP-0014`, the Core Platform Domain
Architecture (`XP-0015`–`XP-0025`), the Module Foundation
(`XP-0026`–`XP-0029`), `XP-0030`, or any other frozen document.

## 2. Why This Domain Exists

`XP-0011` already names Business OS as one of the platform's Digital
Operating Systems — the one that "serves the domain of running a
business: the operational work an organization does to function and
grow." `XP-0013` names Businesses and Enterprises among the platform's
eleven primary audiences. `XP-0014` Section 9 anticipates a Domain
Architecture document for Business OS as one of exactly five major
architectural domains, and `XP-0030` establishes the constitutional
contract every such document must satisfy before it can become
authoritative.

Without this document, Business OS would have no `Approved` architecture
of its own: no stated boundary against the Core Platform, no stated
boundary against the other Digital Operating Systems, and no basis for
identifying its own Modules per `XP-0026`. `XP-0030` Section 2 already
warns that, absent one shared contract, each Digital Operating System's
own Domain Architecture would independently invent its own notion of
boundary and reuse — this document discharges that contract specifically
for Business OS, consistent with Reuse Before Duplication and Platform
Before Product (`XP-0005`, `XP-0011`, `XP-0012`).

## 3. Architectural Principles

This document introduces no principle of its own. It is governed by the
same principles already binding on every Digital Operating System and the
platform beneath it, applied here specifically to Business OS:

- **Platform Before Product** and **Reuse Before Duplication**
  (`XP-0005` Principles 2–3; `XP-0011`, `XP-0012`) — Business OS composes
  what the Core Platform and Shared Ecosystem Services already provide
  rather than rebuilding any of it.
- **Build Once, Reuse Everywhere** and **Composable Operating Systems**
  (`XP-0011`'s Key Architectural Principles) — Business OS is added to the
  platform by composition, not by re-architecting what already exists.
- **Domain Minimalism** and **Document Minimalism** (`XP-0010` Section 3,
  the Domain Architecture pattern's own governing characteristics) — this
  document owns only the universal, platform-level concerns of the
  Business OS domain, and no more.

## 4. Relationship to XP-0030

`XP-0030` establishes the constitutional contract every Digital Operating
System's own Domain Architecture document must satisfy: responsibilities,
non-responsibilities, and relationships to Users, the Core Platform,
Shared Ecosystem Services, Infrastructure, and every other Digital
Operating System, together with Module composition, extension,
architectural-freedom, and differentiation principles that apply
identically to every instance. This document does not restate, redefine,
or duplicate any of that contract. It applies it to exactly one instance
— Business OS, the domain of running a business — exactly as `XP-0030`
Section 15 anticipates a future Domain Architecture document doing for
each roadmapped Digital Operating System in turn.

The relationship runs in one direction only: this document depends on
`XP-0030`'s definitions and principles; `XP-0030` does not depend on this
document, and remains fully correct and complete without it. Where
anything in this document ever appears to conflict with `XP-0030`,
`XP-0030` is correct and this document must be revised to match — never
the reverse.

## 5. Definition and Scope of Business OS

Business OS is the Digital Operating System instance serving the domain
`XP-0011` already names: **the operational work an organization does to
function and grow.** Per `XP-0030` Section 3, it occupies exactly one
position in the canonical five-layer hierarchy — beneath Users, and above
Shared Ecosystem Services, the Core Platform, and Infrastructure — as a
peer of Community OS, Life OS, and any Future Vertical Operating System,
none architecturally privileged over another.

Business OS's scope is the domain-specific business experience, business
logic, and data model for organizations operating a business, built
entirely on Core Platform capabilities and, where relevant, Shared
Ecosystem Services, without rebuilding any foundation those already
provide (`XP-0030` Sections 3–4). Once this document is `Approved`,
Business OS is composed of one or more Modules, per `XP-0026`'s
definition; Business OS is never itself a Module, and is never a Module's
parent in the way a Domain Architecture is (`XP-0026` Section 3).

This document does not define what running a business consists of at any
finer grain than this — no specific business capability, function, or
process is named, designed, or bounded here (see Section 13).

## 6. Responsibilities

Applying `XP-0030` Section 4 to this domain, Business OS:

- Owns the domain-specific business experience, business logic, and data
  model for the one distinct domain of work it serves: running a
  business.
- Composes Core Platform capabilities (`XP-0015`–`XP-0025`) and, where
  relevant, Shared Ecosystem Services (`XP-0011`) into that
  domain-specific experience, rather than rebuilding equivalent
  capability.
- Identifies and bounds the Modules that make up its own scope, per
  `XP-0026`, once this document itself reaches `Approved` (`XP-0030`
  Section 11; Section 13 below).
- Defines what makes running a business distinct as a domain — the
  audience it serves (Businesses and Enterprises, per `XP-0013`), the
  outcomes it exists to produce (operating and growing a business), and
  the experience built around them — within the shared contract `XP-0030`
  establishes.

## 7. Non-Responsibilities

Applying `XP-0030` Section 5 to this domain, Business OS must never own:

- **Any Core Platform responsibility** — identity, organizational or
  tenant boundaries, platform-wide configuration or policy rules,
  accountability or audit responsibility, cross-cutting process or event
  coordination, communication or content infrastructure, external
  connectivity governance, platform-wide insight or governance, commercial
  infrastructure, or the shared experience frame — all of which remain the
  Core Platform's, per `XP-0015`–`XP-0025`, regardless of how convenient it
  might be to duplicate a piece of one inside Business OS.
- **Any Shared Ecosystem Service** — Marketplace, the ecosystem-wide
  Payments experience, AI Assistant, Automation, Recommendations, or a
  future service (`XP-0011`) — Business OS may consume one, per Section 9,
  but never rebuilds, redefines, or forks it.
- **Another Digital Operating System's domain, Modules, data, or
  experience** — Community OS, Life OS, and any Future Vertical Operating
  System remain their own; cross-Operating-System interaction happens
  through Shared Ecosystem Services (Section 11), never through Business
  OS reaching directly into another Operating System's internals.
- **Infrastructure of any kind** — no technology, deployment model, or
  runtime detail belongs to this document or to Business OS (Section 10).
- **The Digital Operating Systems layer itself, or `XP-0030`'s own
  contract** — this document does not redefine what a Digital Operating
  System is, only what Business OS's own domain contains.
- **Any specific business capability, module, workflow, feature, API,
  user interface, database, implementation, or deployment decision** — all
  remain deferred to Business OS's own future Module Architecture,
  Feature Specification, and Implementation Plan documents (Section 13),
  once each is separately authorized.

## 8. Relationship to Users

Businesses and Enterprises — two of the eleven primary audiences `XP-0013`
names — sit directly above Business OS in the canonical hierarchy already
established by `XP-0011`, `XP-0012`, and `XP-0014` Section 5, consistent
with `XP-0030` Section 6. Business OS exists to give those audiences a
coherent, domain-specific experience of the shared platform beneath it:
the layer where the platform becomes legible to an organization as "the
thing I use to run my business," rather than a set of underlying
capabilities. This document does not redefine `XP-0013`'s audience model;
it describes only how Business OS relates to it.

## 9. Relationship to the Core Platform

Business OS depends on the Core Platform — Identity, Organization &
Tenancy, Configuration & Policy, Trust & Accountability, Process &
Events, Communication & Content, Connectivity, Insight & Governance,
Commercial, and Platform Experience (`XP-0015`–`XP-0025`) — exactly as
`XP-0030` Section 7 establishes for every Digital Operating System.
Business OS consumes each Core Platform capability as-is, through the
boundary each domain's own document already defines, rather than
reimplementing, forking, or working around any of them: a business
approval sequence still runs on the Process & Events foundation
(`XP-0020`); Business OS's own organizational and tenant structure still
runs on Organization & Tenancy (`XP-0017`); its accountability and audit
trail still runs on Trust & Accountability (`XP-0019`); its commercial
activity — moving and recording money, tracking entitlement — still runs
on the Core Platform's Commercial domain (`XP-0024`).

The relationship runs in one direction only: Business OS depends on the
Core Platform; no Core Platform domain depends on, or has any awareness
of, Business OS.

## 10. Relationship to Shared Ecosystem Services

Business OS may consume a Shared Ecosystem Service — Marketplace, the
ecosystem-wide Payments experience, AI Assistant, Automation,
Recommendations, or a future service (`XP-0011`) — rather than rebuilding
equivalent capability itself, exactly as `XP-0030` Section 8 establishes.
Business OS never owns, redefines, or forks a Shared Ecosystem Service.
Where Business OS appears to need functionality similar to what another
Digital Operating System needs, that shared need belongs at the Shared
Ecosystem Services or Core Platform layer — it is not solved by
duplicating parallel capability inside Business OS.

The relationship runs in one direction only: Business OS may depend on a
Shared Ecosystem Service; a Shared Ecosystem Service has no awareness of
Business OS specifically.

## 11. Relationship to Infrastructure

Business OS has no direct relationship to Infrastructure at all — it
reaches Infrastructure exclusively through the Core Platform and, where
applicable, Shared Ecosystem Services beneath it, never around them,
exactly as `XP-0030` Section 9 establishes. No technology, deployment
model, hosting decision, or runtime detail belongs to this document; any
such decision remains deferred to a future Implementation Plan, per the
tier `XP-0014` Section 4 names.

## 12. Relationship to Other Digital Operating Systems

Business OS is a peer of Community OS, Life OS, and any Future Vertical
Operating System — none built on top of, or subordinate to, another
(`XP-0030` Section 10; `XP-0014` Section 7). Where Business OS needs to
interact with another Digital Operating System, that interaction happens
exclusively through Shared Ecosystem Services (Section 10) — never
through a direct dependency of Business OS on another Operating System's
internals.

## 13. Module Composition Intent

Once this document reaches `Approved`, Business OS's own Domain
Architecture identifies and bounds its Modules, per `XP-0026`'s
definition, `XP-0027`'s classification criteria, and `XP-0028`'s
composition principles — consistent with `XP-0030` Section 11's own
deferral of Module identification until a Digital Operating System's own
Domain Architecture is `Approved`. Each identified Module belongs to
exactly one Digital Operating System (`XP-0026` Section 7) and is never
shared across more than one. Where a capability appears needed by more
than one Digital Operating System, it is reclassified per `XP-0027`, not
duplicated as a parallel Module inside Business OS.

This document identifies, names, or bounds no specific Business OS
Module, capability, feature, or workflow. That identification is deferred
entirely to Business OS's own future Module Architecture documents, each
authorized and authored separately once this document is `Approved`,
consistent with the Documentation Dependency Order (`XP-0014` Section 8).

## 14. Downstream Documents Enabled

Once this document reaches `Approved`, it becomes the reference for:

- Business OS's own future **Module Architecture** documents, identifying
  and bounding the specific Modules within its scope, per `XP-0026`
  Section 7 and Section 13 above.
- Business OS's own future **Feature Specification** documents,
  subordinate to those Module Architecture documents, per the
  Documentation Dependency Order (`XP-0014` Section 8).
- Business OS's own future **Implementation Plan** documents, the only
  tier at which technology and implementation detail belong, per
  `XP-0014` Section 4.
- Any other Digital Operating System's Domain Architecture document, only
  as an illustration of how `XP-0030`'s shared contract has been applied
  once — per `XP-0014` Section 7 and `XP-0030` Section 10, no Digital
  Operating System depends directly on another's internals, so this is
  precedent, not a dependency.

This document does not itself author, number, or reserve any of the
documents it enables — each is registered in `DOCUMENT-INDEX.md`, and
assigned its own `XP-NNNN` identifier, only once its own work is
explicitly authorized, per `xp-0000-documentation-governance.md`.

## 15. Risks

- **Core Platform duplication.** Business OS could absorb a Core Platform
  responsibility for domain-specific convenience. Guardrail: Section 7
  states this explicitly, consistent with `XP-0015`–`XP-0025`.
- **Shared Ecosystem Service duplication.** Business OS could rebuild a
  Shared Ecosystem Service rather than consuming it. Guardrail: Sections
  7 and 10 state this explicitly.
- **Premature capability or Module naming.** This document could be
  tempted to name a real Business OS capability, Module, or workflow to
  make its scope concrete. Guardrail: Sections 5, 7, and 13 exclude this
  explicitly and defer it to Business OS's own future Module Architecture
  documents.
- **Cross-Operating-System coupling.** Business OS could develop a direct
  dependency on Community OS, Life OS, or a Future Vertical Operating
  System for convenience. Guardrail: Section 12 forbids this explicitly
  and routes interaction through Shared Ecosystem Services.
- **Technology or implementation drift.** Describing Business OS's
  boundary invites the temptation to describe its data model, API, user
  interface, or deployment shape. Guardrail: Sections 7 and 11 state that
  no such detail belongs to this document or this tier; it remains
  deferred to a future Implementation Plan.
- **`XP-0030` restatement.** This document could drift into restating
  `XP-0030`'s generic contract instead of applying it specifically to
  Business OS. Guardrail: Section 4 states the one-directional dependency
  explicitly and defers anything generic to `XP-0030` itself.

## 16. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
the Core Platform Domain Architecture (`XP-0015`–`XP-0025`), the Module
Foundation (`XP-0026`–`XP-0029`), and `XP-0030`. Where anything here ever
appears to conflict with any of them, that document is correct and this
one must be revised to match — never the reverse. `XP-0014`'s
Documentation Dependency Order and Domain Architecture roadmap remain
frozen and unchanged; this document neither reopens, weakens, nor
reorders them, and does not redefine anything `XP-0026`–`XP-0030` already
establish.

Domain Minimalism and Document Minimalism apply: any future expansion of
Business OS's own scope, or of what qualifies as one of its Modules,
shall follow the platform's formal architecture governance process, not
an informal revision of this document.

This document follows the established review workflow — CTO, Founder
Review, Claude, CTO Review, Codex, CTO Review, Claude Fixes, Final CTO
Review, Governance Closeout, Freeze — and does not become authoritative
until it completes that process and is registered `Approved` in
`DOCUMENT-INDEX.md`, per `XP-0002`.
