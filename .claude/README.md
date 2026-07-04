# `.claude/`

## Purpose

This directory helps Claude Code apply the XETROIT Platform's existing
`docs/` rules consistently, task after task — reusable context,
role definitions, repeatable commands, templates, and analytical
checklists, all in operational form.

## `docs/` Is Authoritative

`docs/` is the single source of truth for architecture, governance, and
product decisions. Nothing in this directory is a second source of that
truth. If a file here ever appears to disagree with `docs/`, `docs/` is
correct and the file here has drifted and needs fixing.

This applies most strictly to document status: `.claude/` never states
or tracks which specific documents are currently `Draft`, `In Review`,
`Approved`, or `Frozen` — that changes over time, and only
`docs/DOCUMENT-INDEX.md` is guaranteed current. Check it directly rather
than trusting a status claim written here.

## `.claude/` Never Overrides Repository Documentation

Every file in this directory cites the `docs/` rule it operationalizes
rather than restating or reinterpreting it. Extending `docs/` content, or
introducing a new rule, boundary, or governance decision, does not
happen here — see `docs/CONTRIBUTING.md` and
`docs/00-governance/xp-0002-approval-workflow.md` for how that actually
happens.

## Layout

| Folder | Contents |
|---|---|
| `context/` | Reusable background: principles, governance, structure, terms |
| `agents/` | Role definitions for review/audit tasks |
| `commands/` | Repeatable operations (new document, review, freeze prep) |
| `templates/` | Blank skeletons to start from |
| `skills/` | Analytical techniques (boundary, dependency, duplication checks) |
| `memory/` | Stable, non-lifecycle repository facts |
| `workflows/` | End-to-end sequences for recurring processes |

Start at `.claude/CLAUDE.md` for the full operating manual.
