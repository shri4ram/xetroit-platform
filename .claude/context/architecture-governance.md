# Context: Architecture Governance

Authoritative sources: `docs/00-governance/xp-0000-documentation-governance.md`
(lifecycle, numbering), `docs/00-governance/xp-0001-ai-engineering-governance.md`
(roles, authority), `docs/00-governance/xp-0002-approval-workflow.md`
(approval mechanics). This file summarizes them for quick reference; it
never overrides them.

## Roles (XP-0001)

| Role | Function | Approves documents? |
|---|---|---|
| Founder | Final authority on product, architecture, and approval | Yes — sole authority |
| ChatGPT (CTO / Product Architect) | Designs architecture, drafts docs, recommends approval | No |
| Claude Code | Authors documentation, implements code once `Approved` | No |
| Codex | Independently reviews, files findings | No |
| Future AI Agents | No authority until explicitly defined in `XP-0001` | No |

Claude Code never marks a document `Approved`, never treats a non-`Approved`
document as authorizing implementation, and never assumes a future agent's
role exists until `XP-0001` names it.

## The Document Lifecycle (XP-0000)

`Planned → Draft → In Review → Approved → Deprecated / Archived`. States
are never skipped. `Foundation Draft` (seen on scaffolding files like
folder `README.md`s) is not one of these six states — it marks
repository scaffolding, not a governed decision.

## The Approval Gate (XP-0002)

Implementation of any kind is blocked unless all three are true:
1. The relevant `XP-NNNN` document exists.
2. The architecture it depends on is `Approved`.
3. The document's own status is `Approved` — in both its own metadata
   and `DOCUMENT-INDEX.md`.

Verify this against the actual current `DOCUMENT-INDEX.md`, not memory.

## Checking a Document's Status

`.claude/` never states which specific documents are currently `Approved`
or **Frozen** — that is repository truth, and it lives in exactly one
place: `docs/DOCUMENT-INDEX.md`. Check it directly, every time, before
editing or citing a document as authoritative; do not rely on a prior
session's memory of a document's status. Once you know a document is
`Approved` and Frozen, a new, subordinate document may cite and build on
it, but never restates, duplicates, or reinterprets it.

## When a Conflict Appears

Use the Engineering Decision Pyramid (`XP-0006`): a lower layer never
overrides a higher one. If a task's instruction seems to require
contradicting an `Approved` document, stop and surface the conflict
rather than resolving it by guesswork — see
`docs/00-governance/xp-0008-ai-decision-checklist.md` for exactly when to
pause and ask.
