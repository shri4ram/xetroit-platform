# Context: Governance / Review Workflow

Authoritative sources: `docs/00-governance/xp-0001-ai-engineering-governance.md`
(the end-to-end engineering workflow) and
`docs/00-governance/xp-0002-approval-workflow.md` (document status
transitions). This file connects the two views used across this
repository's recent architecture work.

## The Engineering Workflow (XP-0001)

```
Idea → Architecture → Documentation → Claude → Codex → Approval →
Implementation → Documentation Update
```

Steps are not skipped or reordered. A step may loop backward (e.g. a
Codex finding sends documentation back to the Documentation step), but
the sequence itself never bypasses a stage.

## The Document Review Cycle (used by recent Domain/Module Architecture work)

```
CTO → Founder Review → Claude → CTO Review → Codex → CTO Review →
Claude Fixes → Final CTO Review → Governance Closeout → Freeze
```

This is the concrete review chain a document runs through while it sits
in `Draft`/`In Review`, mapped onto XP-0002's status transitions:

| Review-chain step | XP-0002 status transition |
|---|---|
| CTO drafts / Founder Review | `Planned → Draft` |
| Claude structures and refines | still `Draft` |
| CTO Review, Codex, CTO Review, Claude Fixes | `Draft → In Review`, Codex findings resolved |
| Final CTO Review, Governance Closeout | preconditions for `In Review → Approved` |
| Freeze | `Approved`, and — for constitutional documents — marked Frozen |

## Resolving a Codex Finding

A finding is resolved only when it is either fixed (document updated) or
explicitly deferred with the Founder's written reasoning recorded in the
document. An unresolved finding blocks `In Review → Approved`.

## Claude Code's Position in This Cycle

- Structures, drafts, and refines documentation; raises Open Questions
  where content is genuinely unclear.
- Never moves a document to `Approved`, and never treats `Draft` or
  `In Review` as authorizing implementation.
- Verifies the Approval Gate's three conditions
  (`.claude/context/architecture-governance.md`) against the current
  `DOCUMENT-INDEX.md` before any implementation-adjacent task.

## Related

- `.claude/workflows/review-cycle.md` — the same cycle as a step-by-step
  operational workflow.
- `.claude/commands/codex-pass.md`, `.claude/commands/freeze.md` — the
  commands that operationalize the later stages of this cycle.
