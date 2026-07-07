# Document Index

**Status:** Foundation Draft
**Last Updated:** 2026-07-07

This is the master index of all official XETROIT Platform documents. Every
document must be registered here at the moment it is identified as needed
(status `Planned`), and this index must be kept in sync with each document's
own lifecycle status. See `00-governance/xp-0000-documentation-governance.md`
for the authoritative lifecycle definition and numbering convention (this
file's own header retains the `Foundation Draft` bootstrap marker defined
there — see that document before assuming it means `Draft`).

## Status Legend

| Status | Meaning |
|---|---|
| Planned | Identified, not yet written |
| Draft | Being written, not authoritative |
| In Review | Complete draft under review |
| Approved | Authoritative — implementation may begin |
| Deprecated | Superseded, retained for reference |
| Archived | No longer relevant, retained for audit |

`Foundation Draft` (seen in this file's own header and in folder
`README.md` files) is **not** part of this legend — it is a temporary
repository-bootstrap marker, not a lifecycle status. See
`00-governance/xp-0000-documentation-governance.md` for its exact
definition.

## Registered Documents

| ID | Title | Folder | Status | Owner |
|---|---|---|---|---|
| XP-0000 | Documentation Governance | 00-governance/ | In Review | Founder |
| XP-0001 | AI Engineering Governance | 00-governance/ | In Review | Founder |
| XP-0002 | Approval Workflow | 00-governance/ | In Review | Founder |
| XP-0003 | Repository Standards | 00-governance/ | In Review | Founder |
| XP-0004 | Architecture Decision Records | 00-governance/ | In Review | Founder |
| XP-0005 | Engineering Principles | 00-governance/ | In Review | Founder |
| XP-0006 | Engineering Decision Pyramid | 00-governance/ | In Review | Founder |
| XP-0007 | Repository Constitution | 00-governance/ | In Review | Founder |
| XP-0008 | AI Decision Checklist | 00-governance/ | In Review | Founder |
| XP-0009 | Why XETROIT Exists | 00-company/ | Approved | Founder |
| XP-0010 | Documentation Writing Standard | 00-governance/ | Approved | Founder |
| XP-0011 | XETROIT — The Unified Digital Platform | 01-platform/ | Approved | Founder |
| XP-0012 | How XETROIT Works | 01-platform/ | Approved | Founder |
| XP-0013 | Who XETROIT Serves | 01-platform/ | Approved | Founder |
| XP-0014 | XETROIT Platform Architecture Map | 01-platform/ | Approved | Founder |
| XP-0015 | Core Platform Domain Architecture | 02-core-platform/blueprints/ | Approved | Founder |
| XP-0016 | Identity Domain Architecture | 02-core-platform/identity/ | Approved | Founder |
| XP-0017 | Organization & Tenancy Domain Architecture | 02-core-platform/organization-tenancy/ | Approved | Founder |
| XP-0018 | Configuration & Policy Domain Architecture | 02-core-platform/configuration-policy/ | Approved | Founder |
| XP-0019 | Trust & Accountability Domain Architecture | 02-core-platform/trust-accountability/ | Approved | Founder |
| XP-0020 | Process & Events Domain Architecture | 02-core-platform/process-events/ | Approved | Founder |
| XP-0021 | Communication & Content Domain Architecture | 02-core-platform/communication-content/ | Approved | Founder |
| XP-0022 | Connectivity Domain Architecture | 02-core-platform/connectivity/ | Approved | Founder |
| XP-0023 | Insight & Governance Domain Architecture | 02-core-platform/insight-governance/ | Approved | Founder |
| XP-0024 | Commercial Domain Architecture | 02-core-platform/commercial/ | Approved | Founder |
| XP-0025 | Platform Experience Domain Architecture | 02-core-platform/platform-experience/ | Approved | Founder |
| XP-0026 | Module Architecture | modules/ | In Review | Founder |
| XP-0027 | Module Classification Principles | modules/ | In Review | Founder |
| XP-0028 | Module Composition Principles | modules/ | In Review | Founder |
| XP-0029 | Module Lifecycle | modules/ | In Review | Founder |
| XP-0030 | Digital Operating System Architecture | digital-operating-systems/ | In Review | Founder |

> **XP-0030 — Digital Operating System Architecture: First Phase 4
> Document** (2026-07-04): `XP-0030 — Digital Operating System
> Architecture` establishes the constitutional contract every Digital
> Operating System's own Domain Architecture document must follow —
> responsibilities, non-responsibilities, and relationships to Users, the
> Core Platform, Shared Ecosystem Services, Infrastructure, and every
> other Digital Operating System — ahead of any specific Business OS,
> Community OS, Life OS, or future vertical Domain Architecture document.
> It does not modify the Platform Constitution, `XP-0014`, the Core
> Platform Domain Architecture (`XP-0015`–`XP-0025`), or the Module
> Foundation (`XP-0026`–`XP-0029`), and it designs no specific Digital
> Operating System. Filed in `digital-operating-systems/` — an unnumbered,
> cross-cutting top-level folder analogous to `modules/`, since this
> document spans every Digital Operating System rather than belonging to
> one numbered domain folder (see `xp-0003-repository-standards.md`).
> Registered here as `Draft`; `Approved` status is not asserted by this
> entry.

> **XP-0029 — Module Lifecycle: Fourth Phase 3 Document** (2026-07-04):
> `XP-0029 — Module Lifecycle` defines how an already-classified,
> already-composed Module evolves through its architectural life —
> Candidate, Approved, Evolving, and Retired — while preserving
> architectural continuity. It builds directly on `XP-0026` (what a
> Module is), `XP-0027` (when something qualifies as one), and `XP-0028`
> (how it is composed), without redefining any of them. It introduces no
> software development lifecycle, release, deployment, testing, or
> project-management concept — a Module's architectural lifecycle is
> explicitly distinguished from the document lifecycle status already
> used throughout `DOCUMENT-INDEX.md`. No further Phase 3 foundation
> document is currently anticipated. Filed alongside `XP-0026`–`XP-0028`
> in `modules/`. Registered here as `Draft`; `Approved` status is not
> asserted by this entry.

> **XP-0028 — Module Composition Principles: Third Phase 3 Document**
> (2026-07-04): `XP-0028 — Module Composition Principles` defines how an
> already-classified Module should be architecturally composed —
> cohesion, granularity, Capability placement, decomposition,
> aggregation, and boundary stability — so it remains cohesive,
> maintainable, and stable over time. It builds directly on `XP-0026`
> (what a Module is) and `XP-0027` (when something qualifies as one)
> without redefining either. It does not define Module Lifecycle, which
> remains deferred to a future document, and it does not describe
> implementation or runtime communication. Filed alongside `XP-0026` and
> `XP-0027` in `modules/`. Registered here as `Draft`; `Approved` status
> is not asserted by this entry.

> **XP-0027 — Module Classification Principles: Second Phase 3 Document**
> (2026-07-04): `XP-0027 — Module Classification Principles` defines how
> a proposed piece of platform work is classified as a Module, a
> Capability, a Feature, a Workflow, Configuration, a Shared Ecosystem
> Service, or a Core Platform responsibility. It builds directly on
> `XP-0026` — which defines what a Module is — without redefining any of
> it, and without designing any specific module, capability, feature,
> workflow, or configuration. It does not define Module composition or
> Module lifecycle, which remain deferred to future documents. Filed
> alongside `XP-0026` in `modules/`. Registered here as `Draft`;
> `Approved` status is not asserted by this entry.

> **XP-0026 — Module Architecture: First Phase 3 Document** (2026-07-04):
> `XP-0026 — Module Architecture` establishes the constitutional meaning
> of a Module — what qualifies, what does not, and how a Module relates
> to Digital Operating Systems, Shared Ecosystem Services, and the Core
> Platform — ahead of any individual Digital Operating System's own
> Domain Architecture or any specific Module Architecture document. It
> elaborates the Module Architecture tier already named in `XP-0014`
> Section 4 and does not modify the Platform Constitution, `XP-0014`, or
> the Core Platform Domain Architecture (`XP-0015`–`XP-0025`). Filed in
> `modules/` — a first-class architectural category rather than an
> `XP`-numbered folder, since Module Architecture is cross-cutting across
> every Digital Operating System rather than specific to any one of them.
> Registered here as `Draft`; `Approved` status is not asserted by this
> entry.

> **Core Platform Domain Architecture Complete — Index Synchronized**
> (2026-07-04): Registers `XP-0016` through `XP-0025` — Identity,
> Organization & Tenancy, Configuration & Policy, Trust & Accountability,
> Process & Events, Communication & Content, Connectivity, Insight &
> Governance, Commercial, and Platform Experience — as `Approved`,
> completing the Core Platform Domain Architecture set alongside `XP-0015`.
> Each is filed in its own subfolder under `02-core-platform/`. This closes
> out the Core Platform Domain Architecture phase initiated by `XP-0014`.
>
> This update also moves `XP-0009`, `XP-0011`, `XP-0012`, `XP-0013`
> (Platform Constitution), and `XP-0010` (Documentation Writing Standard)
> from `Draft` to `Approved` in this index, reflecting that all five have
> completed architecture review. The follow-up edit to each document's own
> internal Document Metadata table (Version → `1.0`, Status → `Approved`,
> per `00-governance/xp-0010-documentation-writing-standard.md` §12) noted
> here as outstanding has since been completed during Repository
> Navigation & Metadata Alignment (2026-07-04); all five now agree with
> this index.
>
> `xp-0015a-core-platform-interaction-model.md` (an early interaction-model
> draft superseded before this phase completed) was never registered in
> this index and is not part of the Core Platform Domain Architecture set —
> it is not a constitutional document and this update does not change that.
> It has since been archived to `archive/architecture-exploration/`
> (2026-07-04).
> `GLOSSARY.md` and `docs/02-core-platform/README.md` were also aligned in
> this phase; neither carries an `XP-NNNN` ID or a row in this table.

> **XP-0015 Approved and Frozen — First Domain Architecture Document**
> (2026-07-02): `XP-0015 — Core Platform Domain Architecture`
> (`02-core-platform/blueprints/xp-0015-core-platform-domain-architecture.md`)
> has received final CTO approval and is now `Approved` and **Frozen**. It
> is the first Domain Architecture document produced under the roadmap
> established in `XP-0014`, defining the Core Platform domain's purpose,
> responsibilities, non-responsibilities, boundaries, capability map, and
> relationships to Digital Operating Systems, Shared Ecosystem Services,
> and Infrastructure, consistent with the canonical five-layer hierarchy
> and the Platform Constitution. It fulfills the previously unnumbered
> "Core Platform Architecture" placeholder below, which is now marked
> superseded. This is a governance-tracking update only — the document
> itself was not modified as part of this closeout.

> **XP-0014 Approved and Frozen — Platform Architecture Phase Initiated**
> (2026-07-02): `XP-0014 — XETROIT Platform Architecture Map` is
> `Approved` (Codex Approved) and Frozen at version `1.0`. It is the
> master navigation map defining the architecture vocabulary (Constitution,
> Architecture Map, Domain Architecture, Module Architecture, Feature
> Specification, Implementation Plan), the five major architectural
> domains (Core Platform, Business OS, Community OS, Life OS, Future
> Vertical OS) under the XETROIT Platform umbrella, and the documentation
> dependency order that governs them. Its approval initiates the Platform
> Architecture phase: Domain Architecture documents for the five domains
> in its roadmap may now be planned against it. No new roadmap items or
> `XP-NNNN` numbers were reserved by this approval.

> **Architecture Checkpoint #1 — Layer Model Corrected** (2026-07-02):
> `XP-0011`, `XP-0012`, and `XP-0013` were revised (each to version `0.2`)
> to adopt one canonical five-layer platform model consistently: `Users →
> Digital Operating Systems → Shared Ecosystem Services → Core Platform →
> Infrastructure`. `XP-0011` previously used a different four-layer model
> that treated Future Vertical Operating Systems as a separate top layer;
> it now matches `XP-0012`'s model exactly, including in its diagrams.
> Future Vertical Operating Systems are now consistently treated as a
> category within the Digital Operating Systems layer, never a layer of
> their own. `XP-0011`'s "AI-first assistance" was renamed to
> "Human-Centered AI" to match the term already used elsewhere in that
> document and in `XP-0012`. `XP-0012` and `XP-0013` each gained an
> explicit clarification distinguishing **Audience** (who the platform
> serves) from **Operating System** (how it serves them). No governance
> document and no `XP-0009` content was modified in this pass.

> **Platform Constitution Complete** (2026-07-02): `XP-0013` is the fourth
> and final Platform Constitution document, completing the set alongside
> `XP-0009` (why), `XP-0011` (what), and `XP-0012` (how) with **who**:
> eleven primary audiences (Individuals, Families, Communities,
> Businesses, Enterprises, Government Organizations, Educational
> Institutions, Healthcare Organizations, Non-Profit Organizations,
> Partners, Developers), how they relate, a growth strategy, future
> audience expansion, guiding principles, and an audience relationship
> diagram. It is explicitly business-level, not technical: no permissions
> model, RBAC, authentication, onboarding design, or product feature
> appears in it.

> **Second Platform Document — Conceptual Architecture** (2026-07-02):
> `XP-0012` explains *how* the platform works, continuing directly from
> `XP-0011`'s *what*: a five-layer model (Users, Digital Operating
> Systems, Shared Ecosystem Services, Core Platform Services,
> Infrastructure as a concept only), how sharing works at the Core
> Platform and Shared Ecosystem Services layers, the future growth model,
> and architectural principles (Single Source of Truth, Shared Ownership,
> Loose Coupling, High Cohesion, Build Once, Reuse Everywhere, Platform
> Evolution). It is technology-independent — no Laravel, Flutter, Node.js,
> API, or database content appears in it. It substantially fulfills the
> previously unnumbered "Platform Architecture" placeholder below (that
> placeholder's own description — "top-level system architecture: how
> modules relate, shared services, cross-cutting concerns" — is exactly
> what this document delivers, at a conceptual level), which is now marked
> superseded. A future, more detailed **technology-specific** architecture
> document (naming actual technology choices) remains a distinct, not-yet
> -numbered document once those decisions are authorized — it is not the
> same scope as this one and should not reuse the "Platform Architecture"
> working title without a fresh entry.

> **First Platform Document** (2026-07-02): `XP-0011` is the executive
> overview of the XETROIT Platform — what it is, its four-layer model
> (Core Platform, Shared Ecosystem Services, Digital Operating Systems,
> Future Vertical Operating Systems), and its key architectural
> principles. It is explicitly non-technical: no technology choice,
> implementation detail, or feature specification appears in it. It
> substantially fulfills the previously unnumbered "XETROIT Platform
> Master Plan" placeholder below, which is now marked superseded. The
> separate "Platform Architecture" placeholder remains deferred — it is
> expected to be a more detailed, still-to-come technical/system
> architecture document, distinct in scope from this executive overview.

> **Documentation Writing Standard** (2026-07-02): `XP-0010` defines how
> every future XETROIT document is written — structure patterns, required
> metadata/sections, style, language, diagrams, tables, cross-references,
> versioning, review rules, and AI authoring/review rules. It is a new
> addition to the governance folder, not a modification of the frozen
> `XP-0000`–`XP-0008` content; it complements `xp-0003` (file/folder
> conventions) and `DOCUMENT-TEMPLATE.md` (specification skeleton) rather
> than replacing either.

> **Platform Constitution — First Entry** (2026-07-02, refined 2026-07-02):
> `XP-0009 — Why XETROIT Exists` is the first company/vision document
> created after the governance series. It fulfills the previously
> unnumbered "XETROIT Philosophy" placeholder below — that working title
> is now superseded by `XP-0009` and removed from the deferred list. The
> document was placed in `00-company/`, not `01-company/`, to stay
> consistent with the folder structure fixed by the frozen
> `xp-0003-repository-standards.md`. Its initial draft's
> `[FOUNDER INPUT NEEDED]` placeholders were resolved in v0.2, per the
> Founder's direction to proceed from the established company perspective
> (see `xp-0009-why-xetroit-exists.md` Revision History). It was authored
> ahead of `XP-0000`–`XP-0008` formally reaching `Approved` status (they
> remain `Draft`); see the recommendation in `CHANGELOG.md` to reconcile
> this formally.

> **Milestone 0.3 — Engineering Operating System** (2026-07-02): XP-0005
> through XP-0008 extend the governance series established by
> XP-0000–XP-0004. They remain governance-level documents (engineering
> principles, decision authority, constitution, AI pre-flight checklist)
> and do not describe platform architecture, modules, or implementation —
> see each document's Non-Goals section. This continues the governance
> `XP-NNNN` sequence; it does **not** reassign numbers to the deferred
> platform/module topics below, which remain unnumbered.

### Numbering Collision — Resolved

An earlier pass of this repository speculatively pre-registered
`XP-0000`–`XP-0010` against future platform/module documents (Philosophy,
Master Plan, Platform Architecture, etc.) before any governance process
existed to justify assigning permanent IDs. That collided with the numbers
now correctly claimed by the governance charter above, per
`xp-0000-documentation-governance.md` §4 ("No number may be assigned
speculatively for a document whose content has not yet been authored under
an approved governance process").

**Resolution:** those speculative registrations are withdrawn. The topics
are retained below as unnumbered, `Planned` entries. They will receive a
real `XP-NNNN` number — starting from the next unused number after the
governance series — only once governance itself reaches `Approved` and
platform architecture work is explicitly authorized. (At the time this
resolution was first written, no number beyond `XP-0004` had been
assigned; the governance series has since continued through `XP-0008`
with the Milestone 0.3 documents above — all still governance, not
platform/module content — so this deferral still holds.)

| Working Title | Target Folder | Status | Owner |
|---|---|---|---|
| ~~XETROIT Philosophy~~ | 00-company/ | Superseded by XP-0009 | — |
| ~~XETROIT Platform Master Plan~~ | 01-platform/ | Superseded by XP-0011 | — |
| ~~Platform Architecture~~ (conceptual) | 01-platform/ | Superseded by XP-0012 | — |
| Platform Architecture (technology-specific) | 01-platform/ | Planned | Unassigned |
| ~~Core Platform Architecture~~ | 02-core-platform/ | Superseded by XP-0015 | — |
| Business OS | 03-business-os/ | Planned | Unassigned |
| Community OS | 04-community-os/ | Planned | Unassigned |
| Life OS | 05-life-os/ | Planned | Unassigned |
| Marketplace | 06-marketplace/ | Planned | Unassigned |
| Payments | 07-payments/ | Planned | Unassigned |
| AI Platform | 08-ai/ | Planned | Unassigned |
| Mobile Architecture | 09-mobile/ | Planned | Unassigned |

> These are intentionally unnumbered. Do not assign them `XP-NNNN` IDs, and
> do not author their content, until governance documents XP-0000–XP-0008
> are `Approved` and platform architecture work is explicitly authorized.

## Adding a New Document

1. Assign the next sequential `XP-NNNN` ID (never reuse a retired number,
   and never assign one to a topic ahead of the governance process that
   authorizes it — see the collision note above).
2. Add a row to the Registered Documents table with status `Planned`.
3. Create the document file using `DOCUMENT-TEMPLATE.md`, named per the
   lowercase kebab-case convention in
   `00-governance/xp-0003-repository-standards.md`, inside the appropriate
   numbered folder.
4. Update this table's status as the document progresses through its
   lifecycle, per `00-governance/xp-0002-approval-workflow.md`.
