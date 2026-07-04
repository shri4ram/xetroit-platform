# Repository Memory

Stable, durable facts about this repository's architecture — not a
scratchpad for in-progress discussion or task notes, and not a tracker
of any document's lifecycle status. Lifecycle status changes as
documents move through review; this file does not track it, and never
should — `docs/DOCUMENT-INDEX.md` is the only place guaranteed current.
Always check it directly for what is `Approved`, `Frozen`, or otherwise.

## The Canonical Five-Layer Hierarchy

Fixed since `XP-0011`/`XP-0012`, restated identically by `XP-0014` §5:

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

## Engineering Principles and Decision Pyramid (Names Only)

The twelve Engineering Principles and the ten-layer Engineering Decision
Pyramid are defined by `XP-0005` and `XP-0006` respectively — those
governance documents are the authority on their content and rationale.
Consult them directly, and check `docs/DOCUMENT-INDEX.md` for their
current lifecycle status and authority; this file names them for
orientation only. See `.claude/context/platform-principles.md` for the
principle names and `.claude/context/architecture-governance.md` for how
conflicts between them resolve.

## Roles

Founder, ChatGPT (CTO / Product Architect), Claude Code, Codex, and any
Future AI Agent explicitly defined in `XP-0001` are this repository's
fixed set of roles. See `.claude/context/architecture-governance.md` for
their responsibilities and approval authority.

## What This File Is Not

- Not a log of in-progress work, open tasks, or conversation history —
  that belongs in the task itself, not here.
- Not a tracker of any document's lifecycle status or `DOCUMENT-INDEX.md`
  row — check `docs/DOCUMENT-INDEX.md` directly for that, every time.
- Not a description of the governance workflow's steps — see
  `.claude/context/review-workflow.md` and `.claude/workflows/` for that.
