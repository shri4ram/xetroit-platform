# Contributing to XETROIT Platform Documentation

**Status:** Foundation Draft

This guide explains how to propose, write, review, and approve documents in
this repository. It applies to human contributors and AI coding agents
alike. It is a practical how-to guide; the authoritative rules it follows
are defined in `00-governance/`:
[XP-0000](00-governance/xp-0000-documentation-governance.md) (lifecycle,
numbering), [XP-0001](00-governance/xp-0001-ai-engineering-governance.md)
(roles and approval authority), [XP-0002](00-governance/xp-0002-approval-workflow.md)
(approval mechanics), and [XP-0003](00-governance/xp-0003-repository-standards.md)
(file naming and structure).

## 1. Before You Write

1. Check `DOCUMENT-INDEX.md` to confirm the document doesn't already exist
   or isn't already `Planned`.
2. Confirm which numbered folder the topic belongs to. If none fit, raise
   this explicitly rather than forcing a placement.
3. Confirm you have (or are requesting) the next available `XP-NNNN` ID.

## 2. Creating a New Document

1. Copy `DOCUMENT-TEMPLATE.md` into the correct folder.
2. Name the file in lowercase kebab-case, e.g. `xp-0004-architecture-decision-records.md`
   (see `00-governance/xp-0003-repository-standards.md` — this replaces an
   earlier, inconsistent uppercase example that previously appeared here).
3. Fill in the metadata table completely — do not leave `Owner`, `Category`,
   or `Audience` blank.
4. Set `Status: Draft` once content writing begins.
5. Add/update the corresponding row in `DOCUMENT-INDEX.md`.

## 3. Writing Standards

- Write for **all four audiences** (investors, developers, architects, AI
  agents) — avoid jargon without definition; add unfamiliar terms to
  `GLOSSARY.md`.
- Be explicit and unambiguous. AI coding agents will implement exactly what
  is written, not what was intended but left unstated.
- Prefer structured lists and tables over long prose paragraphs.
- Every business or technical rule must be stated as a discrete, testable
  rule — not implied.
- Do not describe implementation code in architecture documents; describe
  contracts, boundaries, and behavior.

## 4. Review Process

1. Move status to `In Review` once the draft is complete.
2. Owner requests review from relevant Architecture/Business stakeholders,
   including a Codex review pass.
3. Reviewers verify: accuracy, completeness against the template, no
   unresolved contradictions with other Approved documents.
4. All Codex findings are resolved (fixed, or explicitly deferred with
   written reasoning) and all items in the document's **Approval
   Checklist** are satisfied.
5. **Only the Founder** may set `Status: Approved` — see
   [XP-0001](00-governance/xp-0001-ai-engineering-governance.md) for the
   full approval authority matrix. Update `Last Updated` and log the change
   in the document's Revision History.
6. Update `DOCUMENT-INDEX.md` to reflect the new status.

Full step-by-step transition rules live in
[XP-0002 — Approval Workflow](00-governance/xp-0002-approval-workflow.md).

## 5. Changing an Approved Document

- Approved documents are not edited casually. Any change requires:
  1. A new revision entry in the document's Revision History.
  2. Re-review by the Owner (and Architecture stakeholders for
     architecture-impacting changes).
  3. A corresponding entry in `CHANGELOG.md` if the change affects
     governance/structure, or in the document's own history otherwise.
- Breaking changes to Approved architecture must not be made silently to
  unblock code — the document is corrected and approved first.

## 6. Deprecating or Archiving

- **Deprecated**: superseded by a newer Approved document. Add a note at
  the top of the deprecated document linking to its replacement.
- **Archived**: no longer relevant. Left in place for audit history, clearly
  marked, excluded from active reference by AI agents and developers.

## 7. Rules for AI Coding Agents Contributing to Docs

- Never mark a document `Approved` — that status transition requires
  Founder sign-off, and no other role (see
  [XP-0001](00-governance/xp-0001-ai-engineering-governance.md)).
- When generating or editing documentation, preserve the structure defined
  in `DOCUMENT-TEMPLATE.md`.
- Do not invent architecture decisions; flag unknowns in **Open Questions**
  instead of guessing.
- Do not write or modify production application code as a side effect of a
  documentation task.
- Do not implement application code against any document that is not
  `Approved` — verify the Approval Gate in
  [XP-0002](00-governance/xp-0002-approval-workflow.md) before beginning
  implementation work.
