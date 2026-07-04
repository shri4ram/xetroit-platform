# Glossary

**Status:** Foundation Draft

Shared vocabulary for the XETROIT Platform. Any term that could be
ambiguous to a developer, architect, investor, or AI coding agent should be
defined here rather than assumed. Entries below are pointers to their
authoritative source, not a restatement of full domain architecture —
where a term is defined in detail by an `XP-NNNN` document, that document
remains the single source of truth.

## Platform Terms

| Term | Definition |
|---|---|
| **XETROIT Platform** | The overall product and technology platform documented in this repository; the umbrella term for the whole ecosystem, not itself a domain. See `XP-0014` §6. |
| **XP-NNNN** | The canonical document identifier format used across all official documents (e.g. `XP-0004`). |
| **Digital Operating System** | A domain-specific experience built on the shared Core Platform foundation — Business OS, Community OS, Life OS, or any future vertical Operating System. See `XP-0011`, `XP-0012`, `XP-0014` §6. |
| **Shared Ecosystem Services** | Ecosystem-wide, cross-cutting experiences (e.g. Marketplace) built on the Core Platform foundation, letting Digital Operating Systems interact with each other and with the world beyond the platform. See `XP-0011`. |
| **Core Platform** | The shared, foundational layer beneath every Digital Operating System, providing reusable capability — identity, organization & tenancy, configuration & policy, and more — built once and depended on, never duplicated per domain. See `XP-0011`, `XP-0015 — Core Platform Domain Architecture`. |
| **Canonical Five-Layer Hierarchy** | The platform's one fixed layer model: Users → Digital Operating Systems → Shared Ecosystem Services → Core Platform → Infrastructure. See `XP-0011`, `XP-0012`, `XP-0014` §5. |
| **Business OS** | A Digital Operating System serving the domain of running a business. See `XP-0011`. |
| **Community OS** | A Digital Operating System serving the domain of organizing and participating in a community. See `XP-0011`. |
| **Life OS** | A Digital Operating System serving the domain of managing a personal life. See `XP-0011`. |
| **Marketplace** | A Shared Ecosystem Service providing a shared way for value to be listed, discovered, and exchanged across the ecosystem. See `XP-0011`. |
| **AI Agent** | An AI coding agent (e.g. Claude Code) or AI platform feature that consumes this documentation as authoritative context. |

## Document Governance Terms

| Term | Definition |
|---|---|
| **Docs-First** | The governing rule that documentation must be Approved before implementation begins. See `00-governance/xp-0000-documentation-governance.md`. |
| **Lifecycle Status** | One of: Planned, Draft, In Review, Approved, Deprecated, Archived. See `00-governance/xp-0000-documentation-governance.md`. |
| **Foundation Draft** | A temporary, non-lifecycle marker used only on repository-scaffolding files (folder READMEs, navigation files) that describe the shape of the documentation system rather than a governed decision. Not one of the six Lifecycle Statuses and never registered with an `XP-NNNN` ID. See `00-governance/xp-0000-documentation-governance.md`. |
| **Owner** | The individual (currently always the Founder for governance documents) accountable for a document's accuracy and lifecycle progression. |
| **Approval Gate** | The rule that implementation cannot begin until an `XP-NNNN` document exists, its dependent architecture is Approved, and its own status is Approved. See `00-governance/xp-0002-approval-workflow.md`. |
| **ADR (Architecture Decision Record)** | A lightweight, dated record of a single point-in-time technical decision, numbered `ADR-NNNN` separately from `XP-NNNN`. See `00-governance/xp-0004-architecture-decision-records.md`. |
| **AI Engineering Workflow** | The fixed sequence every engineering effort follows: Idea → Architecture → Documentation → Claude → Codex → Approval → Implementation → Documentation Update. See `00-governance/xp-0001-ai-engineering-governance.md`. |
| **Constitutional Architecture** | The Platform Constitution (`XP-0009`, `XP-0011`, `XP-0012`, `XP-0013`) together with every `Approved`/Frozen Architecture Map and Domain Architecture document built on it — principle- and boundary-level documents that define no implementation detail. See `XP-0014` §4. |
| **Domain Architecture** | The document tier defining one Core Platform or Digital Operating System domain's conceptual architecture — purpose, scope, boundaries, and dependencies — without implementation detail. Established by `XP-0015`; recognized as an official document pattern in `00-governance/xp-0010-documentation-writing-standard.md` §3. |
| **Domain Minimalism** | The principle that a domain owns only its own universal, platform-level concerns and nothing more; any expansion of a domain's scope follows the platform's formal architecture governance process, never an informal addition. Applied throughout `XP-0016`–`XP-0025`. |
| **Document Minimalism** | The discipline that a document carries no section, detail, or scope beyond what its stated purpose requires — no redundant restatement, no premature design, no speculative content. Consistent with the writing philosophy and required-section rules in `00-governance/xp-0010-documentation-writing-standard.md` §2, §5–§6. |

## Roles

| Term | Definition |
|---|---|
| **Founder** | The human principal of XETROIT; sole authority able to move a document or ADR to `Approved`/`Accepted`. |
| **ChatGPT (CTO / Product Architect)** | AI role responsible for translating ideas into architecture and product direction and drafting related documentation. |
| **Claude Code** | AI coding agent responsible for authoring documentation and implementing code once a document is Approved. |
| **Codex** | AI review/audit agent responsible for independently reviewing documentation and code and filing findings. |
| **Future AI Agents** | Any AI agent not yet named above; holds no responsibility or authority until explicitly defined in `00-governance/xp-0001-ai-engineering-governance.md`. |

## Core Platform Domains

Each entry is a pointer only — the domain's own `XP-NNNN` document is the
authoritative definition of its purpose, scope, and boundaries.

| Term | Definition |
|---|---|
| **Identity Domain** | Establishes who an identity is and how it is authenticated, universally across the platform. See `XP-0016 — Identity Domain Architecture`. |
| **Organization & Tenancy Domain** | Establishes where an identity belongs and what organizational or tenant context it operates in. See `XP-0017 — Organization & Tenancy Domain Architecture`. |
| **Configuration & Policy Domain** | Establishes what rules and configurable conditions apply within a given identity and organizational context. See `XP-0018 — Configuration & Policy Domain Architecture`. |
| **Trust & Accountability Domain** | Establishes how platform-relevant actions, decisions, and outcomes remain attributable, traceable, and accountable. See `XP-0019 — Trust & Accountability Domain Architecture`. |
| **Process & Events Domain** | Coordinates governed business progression and meaningful platform facts across other domains. See `XP-0020 — Process & Events Domain Architecture`. |
| **Communication & Content Domain** | Governs platform-level communication and reusable content patterns. See `XP-0021 — Communication & Content Domain Architecture`. |
| **Connectivity Domain** | Governs how the platform connects to capabilities and services outside itself. See `XP-0022 — Connectivity Domain Architecture`. |
| **Insight & Governance Domain** | Observes, measures, and governs platform activity without owning source business data. See `XP-0023 — Insight & Governance Domain Architecture`. |
| **Commercial Domain** | Provides reusable payment infrastructure and billing entitlement capability. See `XP-0024 — Commercial Domain Architecture`. |
| **Platform Experience Domain** | Provides the shared frame every Digital Operating System presents its own experience within. See `XP-0025 — Platform Experience Domain Architecture`. |

## Core Platform Boundary & Concept Terms

| Term | Definition |
|---|---|
| **Ownership Boundary** | Which identity or organization is recognized as controlling a given resource or context, at a constitutional level. See `XP-0017`, `XP-0024`. |
| **Tenancy Boundary** | The conceptual boundary of what belongs together on the platform under a given tenant — not a database or technical partitioning strategy. See `XP-0017 — Organization & Tenancy Domain Architecture`. |
| **Configuration Boundary** | What constitutes a governed, platform-controlled adjustable value within a valid platform context. See `XP-0018 — Configuration & Policy Domain Architecture`. |
| **Policy Boundary** | What constitutes a platform-governed rule determining what is allowed, required, restricted, or enforced. See `XP-0018 — Configuration & Policy Domain Architecture`. |
| **Accountability Boundary** | What constitutes a governed unit of attribution, traceability, and accountability for a platform action or decision. See `XP-0019 — Trust & Accountability Domain Architecture`. |
| **Communication Boundary** | What constitutes a governed unit of communication between people or organizations, independent of delivery channel. See `XP-0021 — Communication & Content Domain Architecture`. |
| **Connectivity Boundary** | What constitutes a governed connection between the platform and a capability or service outside itself. See `XP-0022 — Connectivity Domain Architecture`. |
| **Insight Boundary** | What constitutes a governed, platform-level view of activity, built from facts that remain owned by the domain they originate from. See `XP-0023 — Insight & Governance Domain Architecture`. |
| **Governance Boundary** | What constitutes platform-level oversight of behavior and AI capability, distinct from ownership or enforcement. See `XP-0023 — Insight & Governance Domain Architecture`. |
| **Experience Consistency** | The principle that the platform feels coherent and trustworthy across every Digital Operating System. See "Consistency vs. Uniformity" below and `XP-0025 — Platform Experience Domain Architecture`. |
| **Consistency vs. Uniformity** | A Platform Experience principle: consistency means a shared, coherent expectation across Digital Operating Systems; uniformity would mean forcing every screen or interaction to look and behave identically. The platform requires the former, never the latter. See `XP-0025 — Platform Experience Domain Architecture`. |
| **Event** | A meaningful platform fact — a discrete, attributable occurrence significant enough for another domain or Digital Operating System to coordinate around; not a technical message such as a queue entry or log line. See `XP-0020 — Process & Events Domain Architecture`. |
| **Process** | A governed unit of business progression — a bounded sequence of meaningful stages toward a recognized outcome — distinct from a UI flow. See `XP-0020 — Process & Events Domain Architecture`. |
| **Notification** | A communication outcome that reaches a recipient; distinct from an Event, which it may be triggered by but is never identical to. See `XP-0021 — Communication & Content Domain Architecture`. |
| **Governed View** | A platform-level aggregated and interpreted view of activity originating in another domain; the source domain retains ownership of the underlying data's meaning. See `XP-0023 — Insight & Governance Domain Architecture`. |

## Non-Constitutional Implementation Notes (Deferred)

The entries below describe implementation-level candidates or historical
working assumptions only. **None is authorized by any frozen constitutional
document.** `XP-0012` and `XP-0014` §10 explicitly treat Infrastructure
and technology choice as a concept only, deferred to a separate, later
document; every Domain Architecture document (`XP-0015`–`XP-0025`)
independently excludes framework, database, and vendor decisions from its
own scope. These entries are retained for institutional context only and
carry no constitutional weight — they are not a default, a commitment, or
a "first" choice of any kind.

| Term | Definition |
|---|---|
| **Modular Monolith (Non-Constitutional / Deferred)** | A previously referenced candidate backend architectural style. No frozen document commits the platform to this or any other backend style; the decision remains open. |
| **Laravel (Non-Constitutional / Deferred)** | A previously referenced candidate backend technology. No frozen document commits the platform to Laravel or any other backend technology; the decision remains open. |
| **Flutter (Non-Constitutional / Deferred)** | A previously referenced candidate mobile framework. No frozen document commits the platform to Flutter or any other mobile technology; the decision remains open. |
| **Node.js (Non-Constitutional / Deferred)** | A previously referenced candidate for specialized, non-monolith services. No frozen document commits the platform to Node.js or any other technology for this purpose; the decision remains open. |

> This glossary will grow as documents are authored. Add terms here as soon
> as they are introduced in any document.
