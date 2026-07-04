---
description: Draft a Blueprint — a non-authoritative planning artifact that precedes and informs a future Domain Architecture document.
argument-hint: [topic the blueprint informs]
---

Draft a Blueprint for: $ARGUMENTS

Per `docs/00-governance/xp-0010-documentation-writing-standard.md` §3, a
Blueprint is a planning artifact, not constitutional architecture. It
carries no authority of its own and is not held to the Domain
Architecture pattern.

## Pre-Checks

- Confirm this is genuinely pre-architecture planning, not an attempt to
  skip authoring the real Domain Architecture document later.
- Confirm which future Domain Architecture document this Blueprint is
  meant to inform, if known.

## Allowed Actions

- Sketch candidate shape, open questions, and rough boundaries using
  `.claude/templates/blueprint.md`.
- Place the file under the relevant domain's `blueprints/` (or
  `planning/`) folder, matching the existing convention (see
  `docs/02-core-platform/blueprints/`).
- Explore multiple candidate directions without committing to one.

## Forbidden Actions

- Do not label or treat a Blueprint as `Approved`, `Frozen`, or otherwise
  authoritative — it authorizes no capability, boundary, or
  implementation on its own.
- Do not follow the Domain Architecture pattern's numbered
  Purpose-to-Architecture-Governance structure — that would misrepresent
  the Blueprint as constitutional architecture.
- Do not treat a Blueprint as satisfying the Approval Gate for anything.

## Expected Output

A clearly-labeled, non-authoritative planning file that a future Domain
Architecture document can draw on — never mistakeable for `docs/`
constitutional content.
