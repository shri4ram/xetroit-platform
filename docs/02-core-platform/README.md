# 02 — Core Platform

**Status:** Foundation Draft

## Purpose

This folder holds the Core Platform Domain Architecture: the shared,
foundational capabilities every Digital Operating System (Business OS,
Community OS, Life OS, and any future vertical Operating System) depends
on rather than rebuilding, as established by
`XP-0015 — Core Platform Domain Architecture` and elaborated by its ten
constituent Domain Architecture documents. Every document here defines
conceptual architecture only — purpose, scope, ownership boundaries, and
dependencies — never implementation, technology, or business-feature
detail. Business-domain-specific logic belongs in the relevant Digital
Operating System's own folder, not here.

## Documents That Belong Here

Each domain below is documented at the Domain Architecture tier defined
in `XP-0014 — Platform Architecture Map` and recognized as an official
document pattern in `xp-0010-documentation-writing-standard.md` §3.
`XP-0015` is the parent document naming and bounding all ten; it remains
the sole authoritative source for the Capability Map they elaborate.

- [`blueprints/xp-0015-core-platform-domain-architecture.md`](blueprints/xp-0015-core-platform-domain-architecture.md) — XP-0015, Core Platform Domain Architecture (parent document)

**Core Platform Domains** — foundational, establishing universal context:
- [`identity/xp-0016-identity-domain-architecture.md`](identity/xp-0016-identity-domain-architecture.md) — Identity
- [`organization-tenancy/xp-0017-organization-tenancy-domain-architecture.md`](organization-tenancy/xp-0017-organization-tenancy-domain-architecture.md) — Organization & Tenancy
- [`configuration-policy/xp-0018-configuration-policy-domain-architecture.md`](configuration-policy/xp-0018-configuration-policy-domain-architecture.md) — Configuration & Policy
- [`trust-accountability/xp-0019-trust-accountability-domain-architecture.md`](trust-accountability/xp-0019-trust-accountability-domain-architecture.md) — Trust & Accountability

**Cross-Cutting Platform Services** — coordinate business activity across the domains above:
- [`process-events/xp-0020-process-events-domain-architecture.md`](process-events/xp-0020-process-events-domain-architecture.md) — Process & Events
- [`communication-content/xp-0021-communication-content-domain-architecture.md`](communication-content/xp-0021-communication-content-domain-architecture.md) — Communication & Content
- [`connectivity/xp-0022-connectivity-domain-architecture.md`](connectivity/xp-0022-connectivity-domain-architecture.md) — Connectivity
- [`insight-governance/xp-0023-insight-governance-domain-architecture.md`](insight-governance/xp-0023-insight-governance-domain-architecture.md) — Insight & Governance

**Supporting Foundations** — reusable capability built on the domains and services above:
- [`commercial/xp-0024-commercial-domain-architecture.md`](commercial/xp-0024-commercial-domain-architecture.md) — Commercial
- [`platform-experience/xp-0025-platform-experience-domain-architecture.md`](platform-experience/xp-0025-platform-experience-domain-architecture.md) — Platform Experience

[`planning/`](planning/) holds internal planning artifacts (e.g. a
candidate architecture roadmap). Planning artifacts are non-authoritative
working aids, not constitutional architecture — they introduce no
capability, boundary, or decision of their own.

## Current Status

Ten Domain Architecture documents now exist for Core Platform, organized
into the three groupings above beneath their parent, `XP-0015`.
`../DOCUMENT-INDEX.md` remains the authoritative source for each
document's individual lifecycle status.
