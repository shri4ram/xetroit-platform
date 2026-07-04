---
description: Review an architecture document against XETROIT's documentation patterns, boundary rules, and governance requirements.
argument-hint: [path to document]
---

Review the following document against XETROIT's architecture and
documentation rules: $ARGUMENTS

This is an architecture/documentation review, not a code review and not
a substitute for Codex's independent pass
(`.claude/commands/codex-pass.md`).

## Pre-Checks

- Identify which of the five document patterns the document uses
  (`.claude/context/documentation-standard.md`).
- Identify every frozen or `Approved` document it depends on or should be
  consistent with.

## Allowed Actions

- Read the document and every document it cites.
- Use `.claude/agents/architecture-reviewer.md`,
  `.claude/agents/dependency-inspector.md`,
  `.claude/agents/terminology-guardian.md`, and
  `.claude/agents/consistency-checker.md` as reference checklists.
- Produce findings using `.claude/templates/review-report.md`.

## Forbidden Actions

- Do not edit the document as part of the review itself — file findings
  first; fixes are a separate, explicit step.
- Do not change any document's lifecycle status.
- Do not treat a review as equivalent to Codex's required independent
  pass before `Approved` (`XP-0002`).

## Expected Output

A findings list (using `.claude/templates/review-report.md`) covering:
document pattern compliance, ownership boundary clarity, dependency
direction, duplication against existing Core Platform/Shared Ecosystem
Service/Module responsibility, terminology consistency, and any
technology-independence violation — each finding traceable to a specific
`docs/` rule or section, never a vague note.
