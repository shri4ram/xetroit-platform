# 00 — Governance

**Status:** Draft

## Purpose

This folder is the constitutional layer of the XETROIT documentation
system. Before any product, platform, or module documentation is written,
the rules for *how documentation and engineering decisions are made,
reviewed, and approved* must exist and be authoritative. This folder holds
those rules.

Where `00-company/` defines *who XETROIT is* (vision, mission, philosophy),
`00-governance/` defines *how XETROIT decides and builds* — the process
authority that every other folder in this repository operates under.

## Documents That Belong Here

- The documentation governance charter (lifecycle, numbering, ownership)
- AI engineering governance: roles, responsibilities, and approval
  authority for every human and AI participant in the engineering process
- The approval workflow and approval gate rules that block implementation
  until documentation is Approved
- Repository-wide standards (file naming, structure, conventions) that
  apply across every other folder
- The Architecture Decision Record (ADR) standard used platform-wide
- Engineering principles, the engineering decision authority hierarchy,
  the repository constitution, and the AI pre-flight decision checklist —
  the "Engineering Operating System" layer (Milestone 0.3)

Module or platform-specific architecture decisions do not belong here —
only the governance rules that make those decisions possible and
accountable. Once platform architecture work begins, individual
architecture decisions are recorded as ADRs per the standard defined in
`xp-0004-architecture-decision-records.md`, not as new governance
documents.

## Documents in This Folder

| File | XP ID | Title |
|---|---|---|
| `xp-0000-documentation-governance.md` | XP-0000 | Documentation Governance |
| `xp-0001-ai-engineering-governance.md` | XP-0001 | AI Engineering Governance |
| `xp-0002-approval-workflow.md` | XP-0002 | Approval Workflow |
| `xp-0003-repository-standards.md` | XP-0003 | Repository Standards |
| `xp-0004-architecture-decision-records.md` | XP-0004 | Architecture Decision Records |
| `xp-0005-engineering-principles.md` | XP-0005 | Engineering Principles |
| `xp-0006-engineering-decision-pyramid.md` | XP-0006 | Engineering Decision Pyramid |
| `xp-0007-repository-constitution.md` | XP-0007 | Repository Constitution |
| `xp-0008-ai-decision-checklist.md` | XP-0008 | AI Decision Checklist |

## Current Status

**Draft** — all nine governance documents (`XP-0000`–`XP-0008`) have real,
substantive content and are registered in `../DOCUMENT-INDEX.md`. They are
not yet `Approved`; until the Founder approves each one, they are
authoritative for planning and discussion only, per the lifecycle defined
in `xp-0000-documentation-governance.md`. No implementation work of any
kind may begin on the basis of these documents while they remain in
`Draft`.
