---
description: Apply a narrow, explicitly-scoped correction — fix exactly what was named, nothing else.
argument-hint: [what needs fixing]
---

Apply a precision fix for: $ARGUMENTS

A precision fix corrects a specific, named defect (e.g. a Codex finding,
a drift between `.claude/` and `docs/`, a terminology error) without
touching anything the instruction didn't name.

## Pre-Checks

- Restate the exact defect being fixed, in one sentence, before touching
  any file.
- Identify every file the defect actually appears in — search
  (`grep`/`Grep`) rather than assuming a fix is needed in only the file
  mentioned first.
- Confirm which files, if any, the instruction explicitly authorizes
  creating. Do not create others.

## Allowed Actions

- Edit exactly the content that constitutes the named defect.
- Create only a file the current instruction explicitly names as
  creatable.
- Re-verify the fix by searching for other instances of the same defect
  pattern, within the scope the instruction defines.

## Forbidden Actions

- Do not restructure, rewrite, or "clean up" anything beyond the named
  defect — see `.claude/CLAUDE.md` §5.
- Do not modify `docs/` unless the instruction explicitly says to.
- Do not create a file not explicitly listed as allowed.
- Do not introduce a new rule, boundary, or governance decision while
  fixing the defect — a precision fix corrects drift against existing
  `docs/` rules, it never adds new ones.
- Do not touch a document's lifecycle status.

## Expected Output

The named defect fixed everywhere it actually occurs, within the
explicitly authorized scope — plus a short report using
`.claude/templates/codex-handoff-summary.md`: files changed, confirmation
nothing out-of-scope was touched, confirmation no new governance was
introduced.
