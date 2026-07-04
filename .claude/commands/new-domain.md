---
description: Start a new architecture document (Domain Architecture, Module Architecture, or governance document) following the Docs-First process.
argument-hint: [document topic]
---

Create a new architecture document for: $ARGUMENTS

Follow `docs/CONTRIBUTING.md` and
`docs/00-governance/xp-0010-documentation-writing-standard.md`. Use
`.claude/context/documentation-standard.md` and
`.claude/templates/domain-architecture.md` (or `docs/DOCUMENT-TEMPLATE.md`
for the Specification pattern) as your structural starting point.

## Pre-Checks

- Confirm this topic isn't already registered or `Planned` in
  `docs/DOCUMENT-INDEX.md`.
- Confirm which existing folder it belongs in
  (`.claude/context/repository-structure.md`). If none genuinely fits,
  say so explicitly instead of inventing a folder.
- Confirm the parent architecture this document depends on is already
  `Approved` (`XP-0014` §8, Documentation Dependency Order) — a Module
  Architecture document cannot precede its Domain Architecture, for
  instance.
- Confirm the next unused `XP-NNNN` number by checking
  `docs/DOCUMENT-INDEX.md` directly, not from memory.

## Allowed Actions

- Draft new content following the correct pattern
  (Specification, Narrative/Vision, Domain Architecture, ADR, or
  Navigation — `.claude/context/documentation-standard.md`).
- Register the document in `docs/DOCUMENT-INDEX.md` at status `Planned`
  or `Draft`, unless the current task explicitly says not to touch that
  file.
- Cite and build on frozen documents; raise Open Questions for genuine
  gaps.

## Forbidden Actions

- Do not set status to `Approved` — that is the Founder's authority alone.
- Do not modify a frozen document
  (`.claude/context/architecture-governance.md`) to make this one fit.
- Do not invent a new top-level folder without flagging the need
  explicitly.
- Do not introduce a technology, database, or deployment decision.
- Do not duplicate a responsibility already owned by an existing Core
  Platform domain, Shared Ecosystem Service, or Module
  (`.claude/skills/duplication-detection.md`).

## Expected Output

A new `docs/` file, correctly named and placed, using the correct
pattern, status `Draft` (or `Planned` if only scaffolded), with Open
Questions recorded for anything genuinely undecided — ready to enter the
review cycle (`.claude/workflows/new-architecture.md`).
