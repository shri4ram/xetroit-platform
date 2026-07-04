# AI Engineering Governance

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0001 |
| **Title** | AI Engineering Governance |
| **Version** | 0.1 |
| **Status** | Draft |
| **Owner** | Founder |
| **Category** | Governance |
| **Priority** | Critical |
| **Audience** | Investors / Developers / Architects / AI Agents |
| **Last Updated** | 2026-07-02 |
| **Related Documents** | XP-0000, XP-0002, XP-0004 |

---

## Purpose

XETROIT is built by a mixed team of one human founder and multiple AI
agents, each with a different role, different tools, and different blast
radius when they act. Without an explicit governance model, it is
ambiguous who may propose an idea, who may design architecture, who may
write code, who may review it, and — most importantly — who may declare a
decision final. This document removes that ambiguity.

## Scope

Defines the official roles participating in XETROIT engineering, their
responsibilities, their approval authority (or lack of it), and the
end-to-end workflow an idea follows from conception to implemented,
documented reality. Applies to all documentation and implementation work
across every module.

## Goals

- Name every role with a decision-making function in the platform.
- Make approval authority explicit and non-transferable except by the
  Founder's own decision.
- Define one canonical workflow so "who does what, in what order" is never
  re-litigated per task.
- Allow future AI agents to be added to the team without rewriting this
  document's structure.

## Non-Goals

- Does not define the detailed mechanics of a review/approval cycle for a
  single document — see `xp-0002-approval-workflow.md`.
- Does not grant any AI agent standing authority to approve architecture,
  documentation, or code merges. No AI agent has that authority under this
  document, now or by default in the future.

## Dependencies

`xp-0000-documentation-governance.md` (lifecycle and numbering this
document's roles operate within).

## Architecture Notes

N/A.

## Business Rules

### Official Roles

| Role | Who / What | Primary Function |
|---|---|---|
| **Founder** | Human, sole principal of XETROIT | Final authority on all decisions: product direction, architecture approval, document approval, and role changes. |
| **ChatGPT (CTO / Product Architect)** | AI, acting in a standing advisory/design capacity | Translates ideas into product and architecture direction; drafts and refines architecture and platform documents; recommends approval or rejection. |
| **Claude Code** | AI coding agent, this repository's primary hands-on engineer | Authors and structures documentation; scaffolds and implements code once a document is Approved; performs engineering tasks assigned by the Founder or ChatGPT. |
| **Codex** | AI review/audit agent | Independent review of documentation and code for correctness, consistency, security, and governance compliance; files findings; does not author primary content it is reviewing. |
| **Future AI Agents** | Any AI agent not yet named above | Operate strictly within a role explicitly defined by an update to this document before being granted any responsibility or authority. No standing authority by default. |

### Responsibilities

- **Founder**
  - Sets product vision and priorities.
  - Is the only role permitted to move a document's status to `Approved`.
  - Resolves disagreements between AI agents or between a review finding
    and an author's response.
  - Can grant, restrict, or revoke any role's responsibilities at any time
    by updating this document.

- **ChatGPT (CTO / Product Architect)**
  - Proposes architecture and product direction in response to Founder
    ideas.
  - Drafts or directs the drafting of architecture-level documentation
    content.
  - Moves documents from `Draft` to `In Review` when content is complete
    from an architecture standpoint.
  - Recommends approval or rejection to the Founder — recommendation is
    not approval.

- **Claude Code**
  - Authors and maintains documentation structure and content inside this
    repository.
  - Implements application code, but **only** against documents with
    status `Approved` (see the Approval Gate in `xp-0002`).
  - Never marks any document `Approved`.
  - Never modifies production code as an incidental side effect of a
    documentation task.

- **Codex**
  - Independently reviews documentation and, later, implementation for
    correctness, internal consistency, security issues, and governance
    compliance (e.g. lifecycle/numbering rules from `xp-0000`).
  - Produces findings; does not resolve its own findings unilaterally —
    resolution and re-review follow the workflow below.
  - Does not implement production code and does not approve documents.

- **Future AI Agents**
  - May be introduced for a specialized function (e.g. a design agent, a
    QA agent). Before being used, this document must be updated with a new
    row defining the agent's responsibilities and explicitly stating it
    has no approval authority unless the Founder decides otherwise in
    writing, here.

### Approval Authority Matrix

| Action | Founder | ChatGPT | Claude Code | Codex | Future Agents |
|---|:---:|:---:|:---:|:---:|:---:|
| Propose an idea | Yes | Yes | Yes | Yes | Only if role defined |
| Draft architecture content | Yes | Yes | Yes | No | Only if role defined |
| Draft documentation content | Yes | Yes | Yes | No | Only if role defined |
| Move `Draft` → `In Review` | Yes | Yes | Yes | No | No |
| Review / file findings | Yes | Yes | Yes | Yes | Only if role defined |
| Move `In Review` → `Approved` | **Yes (only)** | No | No | No | No |
| Implement application code | No (delegates) | No (delegates) | Yes, only against `Approved` docs | No | Only if role defined |
| Update docs after implementation | Yes | Yes | Yes | No (may flag drift) | Only if role defined |

## Technical Rules

### AI Engineering Workflow

Every non-trivial engineering effort — from a new idea to shipped,
documented functionality — follows this fixed sequence. Steps may not be
skipped or reordered:

```
Idea → Architecture → Documentation → Claude → Codex → Approval → Implementation → Documentation Update
```

1. **Idea** — Founder (or ChatGPT, subject to Founder sign-off) identifies
   a need or opportunity.
2. **Architecture** — ChatGPT, acting as CTO / Product Architect, designs
   the approach at an architecture level.
3. **Documentation** — The architecture is written up as a formal `XP-NNNN`
   document (or ADR, per `xp-0004`), status `Draft`.
4. **Claude** — Claude Code reviews, structures, and refines the
   documentation for completeness, consistency with existing Approved
   documents, and implementability; may raise Open Questions.
5. **Codex** — Codex independently reviews the documentation for
   correctness, internal consistency, security, and governance compliance,
   and files findings.
6. **Approval** — All Codex findings are resolved (fixed or explicitly
   deferred with reasoning); the Founder reviews and, if satisfied, moves
   the document to `Approved`.
7. **Implementation** — Claude Code (or another engineering agent scoped
   for the task) implements strictly against the Approved document.
8. **Documentation Update** — The document's Revision History and status
   are updated to reflect what was actually built; any deviation discovered
   during implementation is corrected in the document, not silently left
   in the code.

A step may loop backward (e.g. Codex findings send documentation back to
step 3) but the sequence itself is never bypassed.

## AI Agent Notes

- Claude Code and Codex must both treat this document as the source of
  truth for "am I allowed to do this." When in doubt about authority,
  default to *not* taking the action and surface the question to the
  Founder instead of assuming permission.
- If a task appears to require skipping a step in the AI Engineering
  Workflow (e.g. "just implement it, skip the doc"), that instruction
  conflicts with `XP-0000`'s Docs-First Rule and this document's workflow;
  Claude Code should flag the conflict rather than silently comply, unless
  the Founder explicitly and knowingly overrides it for that specific
  instance.
- "Resolve all Codex review findings" means: for each finding, either fix
  the underlying issue or record an explicit, reasoned deferral — silence
  is not resolution.

## Open Questions

- Should Codex have the ability to block a document from reaching
  `Approved` outright, or only to file findings that the Founder weighs?
  Current model: findings-only, Founder retains sole approval authority.
  Revisit if this proves insufficient in practice.

## Approval Checklist

- [ ] Content reviewed by Founder
- [ ] Reviewed by ChatGPT (CTO / Product Architect)
- [ ] Reviewed by Codex
- [ ] No open blocking questions remain
- [ ] Cross-references updated in `DOCUMENT-INDEX.md`
- [ ] Status updated in document metadata and `DOCUMENT-INDEX.md`

## Revision History

| Version | Date | Author | Summary of Change |
|---|---|---|---|
| 0.1 | 2026-07-02 | Claude Code | Initial draft: roles, responsibilities, approval authority matrix, AI engineering workflow. |
