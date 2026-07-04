# XETROIT Platform Architecture Map

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0014 |
| **Title** | XETROIT Platform Architecture Map |
| **Version** | 1.0 |
| **Status** | Approved |
| **Owner** | Founder |
| **Category** | Platform |
| **Priority** | Critical |
| **Audience** | Founder / Investors / Architects / Developers / AI Coding Agents |
| **Last Updated** | 2026-07-02 |
| **Related Documents** | XP-0000, XP-0002, XP-0009, XP-0010, XP-0011, XP-0012, XP-0013 |

**Frozen:** This document is `Approved` and **Frozen** as of 2026-07-02
(Codex Approved). Further changes require a new revision and a fresh
approval cycle per `xp-0002-approval-workflow.md` — it is not edited
casually while frozen.

---

> **A note on this document's nature:** This follows the Narrative/Vision
> pattern defined in `../00-governance/xp-0010-documentation-writing-standard.md`.
> It is the master architectural **navigation map** for the XETROIT
> Platform — a guide to how architecture documentation is organized and in
> what order it must be produced. It is **not** implementation, not module
> design, not database design, not Laravel or any other technology
> planning, and not a feature specification. It introduces no new folder,
> renames no existing document, and does not modify the Platform
> Constitution (`XP-0009`, `XP-0011`, `XP-0012`, `XP-0013`) it builds on.
>
> Sections: Document Status; Purpose; Constitutional Alignment;
> Architecture Vocabulary; Canonical Platform Hierarchy; Major
> Architectural Domains; Relationship Between Domains; Documentation
> Dependency Order; Future Architecture Document Roadmap; What XP-0014
> Does Not Define; Governance Note; Revision History.

## 1. Document Status

This document is `Approved` and **Frozen** (Codex Approved, 2026-07-02).
It joins the documents it builds on — the Platform Constitution:
`XP-0009` (Why XETROIT Exists), `XP-0011` (XETROIT Unified Digital
Platform), `XP-0012` (How XETROIT Works), and `XP-0013` (Who XETROIT
Serves), together **Platform Constitution v1.0** — as fully authoritative,
per the lifecycle defined in `xp-0000-documentation-governance.md` and
the Approval Gate defined in `xp-0002-approval-workflow.md`.

With `XP-0014` now `Approved`, the dependency order and roadmap it
defines (Sections 8–9) are binding: a Domain Architecture document for
any of the five domains in Section 6 may now be planned against this map
as its authoritative reference. This document being Frozen means its own
content does not change casually going forward — any future revision to
it requires a new version, a new review, and re-approval, per
`xp-0002-approval-workflow.md`, exactly as for any other Approved
document. This closeout initiates the Platform Architecture phase: the
production of the Domain Architecture documents anticipated in Section 9.

## 2. Purpose

The Platform Constitution (`XP-0009`, `XP-0011`, `XP-0012`, `XP-0013`)
establishes why XETROIT exists, what it is, how it works conceptually, and
who it serves. It does not, by itself, tell an architect, developer, or AI
agent where to find — or where to create — the next, more detailed layer
of documentation for a specific domain.

`XP-0014` closes that gap. It is the master map of how XETROIT's
architecture documentation is organized: the vocabulary used to describe
different tiers of architectural detail, the major domains that
documentation is organized around, how those domains relate to one
another, and the order in which more detailed documents must be written
and approved. It answers "where do I go next," not "what do I build."

## 3. Constitutional Alignment

`XP-0014` sits directly beneath the Platform Constitution and is
subordinate to it. It does not restate, redesign, or reinterpret the
Constitution — it translates the shape the Constitution already
establishes into a navigable structure for the documentation that will
follow:

- `XP-0009` (why) and `XP-0013` (who) give this map its purpose: the
  domains described below exist to serve the audiences and vision those
  documents describe.
- `XP-0011` (what) and `XP-0012` (how) give this map its structure: the
  canonical platform hierarchy restated in Section 5 is taken directly
  from those documents, unchanged.

Now that both Platform Constitution v1.0 and `XP-0014` itself are
`Approved`, this ordering of authority is not merely stylistic: if
anything in this document ever appears to conflict with the Constitution,
the Constitution is correct and this document must be revised to match —
never the reverse.

## 4. Architecture Vocabulary

XETROIT documentation uses six precise terms to describe different tiers
of architectural detail, from timeless and platform-wide to concrete and
narrow. Every future architecture document should be identifiable as
exactly one of these:

| Term | Definition |
|---|---|
| **Constitution** | The foundational documents defining why the platform exists, what it is, how it works conceptually, and who it serves (`XP-0009`, `XP-0011`, `XP-0012`, `XP-0013` — `Approved` as Platform Constitution v1.0). Timeless; revised rarely and deliberately. |
| **Architecture Map** | A navigational document (this document is the first) showing how architectural domains and documents relate to one another and in what order they must be produced. Defines no domain's internals. |
| **Domain Architecture** | A document defining the conceptual architecture of one major domain (see Section 6) — its internal shape and boundaries — without naming any technology or implementation detail. |
| **Module Architecture** | A document defining the architecture of a specific module within a domain: a finer-grained subdivision of a Domain Architecture. |
| **Feature Specification** | A document defining the behavior and rules of a specific feature within a module, at a business-rule level. |
| **Implementation Plan** | A document defining how an approved Feature Specification is actually built — the only tier where technology and implementation detail belong. |

Each tier is narrower and more concrete than the one before it, and each
depends on the tier above it already existing and being `Approved`
(Section 8).

## 5. Canonical Platform Hierarchy

This map uses the same canonical five-layer platform hierarchy already
established in `XP-0011` and `XP-0012`, restated here unchanged so that
this document stays consistent with them:

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

Business OS, Community OS, Life OS, and Future Vertical OS are categories
within the Digital Operating Systems layer, not layers of their own —
consistent with the Architecture Checkpoint #1 correction already applied
to `XP-0011` and `XP-0012`. This document does not alter that hierarchy;
it uses it as the fixed backdrop against which the architectural domains
in Section 6 are organized.

## 6. Major Architectural Domains

**XETROIT Platform is the umbrella term for the entire ecosystem — it is
not itself a domain.** It names the whole described by the Platform
Constitution; it does not sit beside the domains below as a peer, and it
does not require, or receive, a Domain Architecture document of its own
(see Section 9). Everything in this section is a domain *within* the
XETROIT Platform umbrella, not alongside it.

For the purpose of organizing architecture documentation, the XETROIT
Platform umbrella is divided into exactly five major architectural
domains, using these terms consistently and exclusively:

- **Core Platform** — the shared, foundational capabilities every other
  domain depends on (identity, permissions, communication, and the rest,
  as described in `XP-0011`). Corresponds to the Core Platform layer in
  Section 5.
- **Business OS** — the business operating system domain: the
  architecture supporting how organizations run their operations.
- **Community OS** — the community operating system domain: the
  architecture supporting how groups of people organize and connect.
- **Life OS** — the individual/family operating system domain: the
  architecture supporting how a person or household manages their own
  affairs.
- **Future Vertical OS** — future, domain-specific operating systems not
  yet built, following the same relationship to the Core Platform that
  Business OS, Community OS, and Life OS already do.

Business OS, Community OS, Life OS, and Future Vertical OS are domains
within the Digital Operating Systems layer; Core Platform is the domain
corresponding to the Core Platform layer. Each of these five domains —
and only these five — is expected to receive its own Domain Architecture
document in the future (Section 9).

## 7. Relationship Between Domains

Core Platform underlies every other domain: Business OS, Community OS,
Life OS, and any Future Vertical OS all depend on Core Platform's shared
capabilities rather than building their own versions of them, exactly as
described in `XP-0011` and `XP-0012`.

Business OS, Community OS, Life OS, and Future Vertical OS are peer
domains relative to one another — none is built on top of another — and
where they need to interact, they do so through the Shared Ecosystem
Services layer (Marketplace, Payments, AI Assistant, and similar
services), not through direct dependencies on each other. This keeps each
domain's architecture independently understandable, while still allowing
the domains to interoperate as one platform.

## 8. Documentation Dependency Order

Consistent with the Docs-First Rule (`XP-0000`) and the Approval Gate
(`XP-0002`), each architecture vocabulary tier from Section 4 depends on
the tier above it already existing and reaching `Approved` status before
work on the next tier begins:

```
Constitution
      ↓  (must exist and be Approved)
Architecture Map
      ↓  (must exist and be Approved)
Domain Architecture
      ↓  (must exist and be Approved, per domain)
Module Architecture
      ↓  (must exist and be Approved, per module)
Feature Specification
      ↓  (must exist and be Approved)
Implementation Plan
```

Concretely: a Module Architecture document for a module inside Business
OS cannot be authored as authoritative before Business OS has an
`Approved` Domain Architecture document; a Feature Specification cannot
be authored as authoritative before its Module Architecture is `Approved`;
and — per the Approval Gate already defined in `XP-0002` — no
implementation begins before its governing Feature Specification and
Implementation Plan are both `Approved`. This document does not create a
new approval mechanism; it applies the existing one across the vocabulary
defined in Section 4.

## 9. Future Architecture Document Roadmap

The following Domain Architecture documents are anticipated — exactly
one per major architectural domain from Section 6, and no more — in no
particular required order beyond what Section 8 requires:

- Core Platform — Domain Architecture
- Business OS — Domain Architecture
- Community OS — Domain Architecture
- Life OS — Domain Architecture
- Future Vertical OS — Domain Architecture (a shared pattern document,
  rather than one per hypothetical future vertical)

This is a stable, five-item roadmap. XETROIT Platform does **not** appear
in this list and is not expected to: as the umbrella term for the whole
ecosystem (Section 6), it is described by the Platform Constitution
already in place, not by a Domain Architecture document of its own. This
roadmap should not grow to include it, and should not otherwise expand
beyond these five items without a corresponding update to Section 6's
domain list.

None of the five are numbered, registered, or authored by this document.
Per `xp-0000-documentation-governance.md`'s numbering rule, an `XP-NNNN`
identifier is assigned only when a document is actually registered in
`DOCUMENT-INDEX.md` — this roadmap is a statement of anticipated future
work, not a reservation of numbers or a commitment to a specific
sequence or timeline.

Shared Ecosystem Services and Infrastructure (Section 5) are not listed
among the Section 6 domains and do not yet have anticipated Domain
Architecture documents of their own in this roadmap; whether they warrant
one is left open for a future update to this map rather than decided
here.

## 10. What XP-0014 Does Not Define

To keep this map's scope unambiguous, it explicitly does not define:

- The internal architecture of any specific domain (Core Platform,
  Business OS, Community OS, Life OS, or any Future Vertical OS) — that
  belongs to each domain's own future Domain Architecture document.
- Any module, feature, or implementation detail whatsoever.
- Any technology choice, including but not limited to Laravel, any
  database, any API design, or any user-interface detail.
- Any change to the repository's folder structure, which this document
  treats as locked, per this task's instructions.
- Any revision to the Platform Constitution (`XP-0009`, `XP-0011`,
  `XP-0012`, `XP-0013`) — this map is downstream of those documents, not a
  replacement or amendment to them.

## 11. Governance Note

This document operates entirely within existing governance: it was
authored, versioned, and approved under the lifecycle and approval rules
defined in `XP-0000` and `XP-0002`, and follows the writing standard
defined in `XP-0010`. It does not modify any governance document,
does not alter the numbering rules those documents define, and does not
propose any change to the locked repository structure. Where this map
anticipates future documents (Section 9), those documents will be
registered in `DOCUMENT-INDEX.md` and assigned `XP-NNNN` identifiers only
when their own work is explicitly authorized — not by virtue of appearing
in this roadmap.

## Revision History

| Version | Date | Author | Summary of Change |
|---|---|---|---|
| 0.1 | 2026-07-02 | Claude Code | Initial draft: document status, purpose, constitutional alignment, six-term architecture vocabulary, restatement of the canonical five-layer platform hierarchy, five major architectural domains, relationships between domains, a six-tier documentation dependency order, a future Domain Architecture roadmap (unnumbered), an explicit non-scope statement, and a governance note. |
| 0.2 | 2026-07-02 | Claude Code | Codex-required fixes: corrected Section 1 to recognize Platform Constitution v1.0 (`XP-0009`, `XP-0011`, `XP-0012`, `XP-0013`) as `Approved`, with only `XP-0014` itself remaining `Draft` (previously implied the whole `XP-0000`–`XP-0013` range was at the same stage). Restructured Section 6 so XETROIT Platform is explicitly described as the umbrella term for the ecosystem, not a sixth peer domain — the section now names exactly five major architectural domains (Core Platform, Business OS, Community OS, Life OS, Future Vertical OS). Aligned Section 9's roadmap language to confirm it is a stable, five-item list that does not include XETROIT Platform and should not expand without a corresponding Section 6 update. No new domains, technology, or implementation detail introduced. |
| 1.0 | 2026-07-02 | Claude Code | Governance closeout: **Codex Approved**; status changed `Draft` → `Approved`; document marked **Frozen** as of 2026-07-02. Updated status-related language in Sections 1, 3, and 11, and the metadata table (Version 0.2 → 1.0, Status → Approved, added a Frozen notice), to reflect the approved/frozen state. No architectural content (Sections 4–10: vocabulary, hierarchy, domains, relationships, dependency order, roadmap, non-scope statement) was changed. This closeout initiates the Platform Architecture phase. |
