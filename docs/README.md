# XETROIT Platform Documentation

**Status:** Foundation Draft — see [note](#0-a-note-on-this-files-status)
**Owner:** XETROIT Architecture Team
**Last Updated:** 2026-07-04

---

## 0. A Note on This File's Status

This file is repository scaffolding, not a governed specification — it
carries the non-lifecycle `Foundation Draft` marker defined in
[`00-governance/xp-0000-documentation-governance.md`](00-governance/xp-0000-documentation-governance.md).
The authoritative, versioned content behind everything summarized below
now lives in `00-governance/`:

| Topic | Authoritative Document |
|---|---|
| Docs-first rule, lifecycle, numbering | [XP-0000 — Documentation Governance](00-governance/xp-0000-documentation-governance.md) |
| Roles, responsibilities, approval authority, AI workflow | [XP-0001 — AI Engineering Governance](00-governance/xp-0001-ai-engineering-governance.md) |
| Approval Gate, status transitions | [XP-0002 — Approval Workflow](00-governance/xp-0002-approval-workflow.md) |
| File naming, folder rules | [XP-0003 — Repository Standards](00-governance/xp-0003-repository-standards.md) |
| Architecture Decision Record standard | [XP-0004 — Architecture Decision Records](00-governance/xp-0004-architecture-decision-records.md) |

If anything below ever appears to disagree with one of those documents,
the `00-governance/` document wins, and this file should be corrected.

## 1. Purpose

This directory is the single source of truth for the XETROIT Platform — its
philosophy, architecture, product modules, operations, and engineering
standards. It exists to serve four audiences simultaneously:

- **Investors** — understanding the vision, scope, and business model.
- **Developers** — understanding what to build and how to build it correctly.
- **Architects** — understanding system boundaries, contracts, and rationale.
- **AI Coding Agents** — understanding structured, unambiguous context needed
  to generate correct, compliant code without guessing intent.

If a decision, rule, or design is not written here, it is not considered
official.

## 2. Docs-First Rule

**No feature, module, or service may be implemented before its corresponding
document exists and has reached `Approved` status.**

This applies equally to human engineers and AI coding agents. Documentation
is not a byproduct of engineering — it is the specification engineering must
follow. Code that contradicts an Approved document is considered a defect in
the code, not the document.

## 3. No Coding Before Approved Architecture

Implementation work (application code, database schemas, infrastructure
changes) **must not begin** until:

1. The relevant document(s) exist under the correct numbered folder.
2. The document has passed through the full [Document Lifecycle](#4-document-lifecycle).
3. The document status is `Approved`.

Draft or In Review documents may be used for discussion and planning only.
AI coding agents must treat any document not marked `Approved` as
non-authoritative for code generation purposes.

## 4. Document Lifecycle

Every document in this repository moves through the following states, in
order. States may not be skipped.

| Status | Meaning |
|---|---|
| **Planned** | Document has been identified as necessary and registered in `DOCUMENT-INDEX.md`, but writing has not started. |
| **Draft** | Actively being written. Content is incomplete or unverified. Not authoritative. |
| **In Review** | Complete draft under review by owner(s) and relevant stakeholders. |
| **Approved** | Reviewed, accepted, and authoritative. Implementation may begin. |
| **Deprecated** | Superseded by a newer document but retained for historical/reference purposes. |
| **Archived** | No longer relevant to the current platform. Retained for audit history only. |

Status changes must be reflected in both the document's own metadata header
(see `DOCUMENT-TEMPLATE.md`) and its entry in `DOCUMENT-INDEX.md`.

**`Foundation Draft` (as seen at the top of this file) is not one of the
six statuses above.** It is a temporary marker used only on repository
scaffolding files that describe the shape of the documentation system
itself, not a governed decision. See
[XP-0000](00-governance/xp-0000-documentation-governance.md) for the full
definition. Only the Founder may set `Approved`; see
[XP-0001](00-governance/xp-0001-ai-engineering-governance.md) for the full
approval authority matrix.

## 4a. Roles and Approval Authority

XETROIT engineering involves one human and several AI agents, each with a
distinct role and a distinct amount of authority. Full definitions,
responsibilities, and the approval authority matrix live in
[XP-0001 — AI Engineering Governance](00-governance/xp-0001-ai-engineering-governance.md).
In summary:

| Role | Function | Can Approve Documents? |
|---|---|---|
| **Founder** | Final authority on product, architecture, and document approval | **Yes — sole authority** |
| **ChatGPT (CTO / Product Architect)** | Designs architecture, drafts documentation, recommends approval | No |
| **Claude Code** | Authors documentation, implements code once Approved | No |
| **Codex** | Independently reviews documentation and code, files findings | No |
| **Future AI Agents** | Role defined only when added to XP-0001 | No, by default |

## 4b. Approval Gate

Implementation of any kind must not begin until all three conditions in
[XP-0002 — Approval Workflow](00-governance/xp-0002-approval-workflow.md)
are met:

1. The relevant `XP-NNNN` document exists.
2. The architecture it depends on is Approved.
3. The document's own status is `Approved`.

## 4c. AI Engineering Workflow

Every engineering effort follows one fixed sequence, defined in full in
[XP-0001](00-governance/xp-0001-ai-engineering-governance.md):

```
Idea → Architecture → Documentation → Claude → Codex → Approval → Implementation → Documentation Update
```

## 4d. Architecture Decision Records

Point-in-time technical decisions supporting an `XP-NNNN` specification are
captured as ADRs once platform architecture work begins. The ADR
numbering, template, status values, and review requirements are defined in
[XP-0004 — Architecture Decision Records](00-governance/xp-0004-architecture-decision-records.md).
No ADRs exist yet — only the standard is defined at this stage.

## 5. Document Numbering Convention

All formal platform documents use the prefix `XP` (XETROIT Platform) followed
by a zero-padded four-digit sequence number, assigned in order of creation
and never reused:

```
XP-0000, XP-0001, XP-0002, ... XP-9999
```

Numbers are permanent identifiers. If a document is deprecated or archived,
its number is retired with it — it is never reassigned to a new document.
Folder placement (e.g. `03-business-os/`) indicates domain, not numbering
order; the `XP-NNNN` ID is the canonical reference used in cross-links,
commits, and AI agent context.

## 6. Documentation Governance

- **Ownership** — every document has a named Owner responsible for its
  accuracy and lifecycle progression.
- **Single Source of Truth** — the `docs/` directory supersedes tribal
  knowledge, chat threads, and verbal decisions. If it's not written down,
  it doesn't govern the platform.
- **Change Control** — approved documents may only move to a new revision
  through a reviewed change (see `CONTRIBUTING.md`), with the change logged
  in the document's Revision History and in `CHANGELOG.md`.
- **Consistency** — all documents must use `DOCUMENT-TEMPLATE.md` as their
  structural basis so that both humans and AI agents can parse them
  predictably.
- **Technology Independence** — documentation at the Constitution,
  Architecture Map, and Domain Architecture tiers remains
  technology-independent; no framework, language, or vendor is assumed at
  these tiers. Technology-specific decisions belong to a separate, later
  Implementation Plan document, authored only once the architecture it
  builds on is `Approved`, per `XP-0014`'s Architecture Vocabulary.

## 7. Repository Structure

```
docs/
├── README.md                 This file — governance and rules
├── DOCUMENT-INDEX.md          Master index of all documents and their status
├── DOCUMENT-TEMPLATE.md       Canonical template for new documents
├── CHANGELOG.md               Log of documentation-level changes
├── CONTRIBUTING.md            How to propose, write, and review documents
├── GLOSSARY.md                Shared vocabulary across the platform
├── 00-governance/               Documentation & AI engineering governance (XP-0000–XP-0008, XP-0010; XP-0009 lives in `00-company/`)
├── 00-company/                 Company vision, mission, philosophy
├── 01-platform/                 Platform-wide architecture and master plan
├── 02-core-platform/            Core Platform Domain Architecture — shared
│                                foundation every Digital Operating System
│                                depends on (XP-0015–XP-0025)
├── modules/                     Module Architecture — the constitutional
│                                meaning of a Module, how proposed work is
│                                classified as one, how it is composed
│                                internally, and how it evolves over time,
│                                shared across every Digital Operating
│                                System (XP-0026, XP-0027, XP-0028, XP-0029)
├── 03-business-os/              Business OS module
├── 04-community-os/             Community OS module
├── 05-life-os/                  Life OS module
├── 06-marketplace/              Marketplace module
├── 07-payments/                 Payments architecture
├── 08-ai/                       AI platform and agent architecture
├── 09-mobile/                   Mobile application architecture
├── 10-devops/                   Infrastructure, CI/CD, environments
├── 11-security/                 Security architecture and policy
├── 12-ui-ux/                    Design system and UX standards
├── 13-api/                      API contracts and standards
├── 14-database/                 Data architecture and schema standards
├── 15-development/              Engineering standards and workflow
├── 16-future-verticals/         Exploratory/future product lines
├── 99-ai-context/               Structured context for AI coding agents
└── archive/                     Superseded or exploratory documents kept
                                 for history (e.g. architecture-exploration/)
```

## 8. How to Use This Documentation

- **Starting new work?** Check `DOCUMENT-INDEX.md` first for an existing or
  planned document covering the area.
- **Writing a new document?** Copy `DOCUMENT-TEMPLATE.md` and follow
  `CONTRIBUTING.md`.
- **Unfamiliar term?** Check `GLOSSARY.md` before assuming meaning.
- **An AI coding agent?** Start at `99-ai-context/README.md`.

---

*This document is itself governed by the lifecycle described above.*
