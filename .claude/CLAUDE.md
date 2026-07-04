# XETROIT Platform — Claude Code Operating Manual

This file is the operating manual for Claude Code in this repository. It
does not define architecture, governance, or product decisions — those
live in `docs/` and are the only authoritative source. Everything here
exists to help Claude Code apply the rules already defined there
consistently, task after task. If anything here ever appears to
disagree with `docs/`, `docs/` is correct and this file has drifted.

Read `docs/00-governance/xp-0007-repository-constitution.md` first if
you have not already — it is the ten-minute map of every rule below.

## 1. Architecture Before Implementation

No feature, module, or service is implemented before its governing
`docs/` document exists and is `Approved` (Docs-First Rule, `XP-0000`).
This repository is currently in its architecture phase: the work here
is authoring and refining `docs/`, not writing application code. Treat
any request to "just implement it" as a signal to check the Approval
Gate (`XP-0002`) first, not as license to skip it.

## 2. The Repository Is the Source of Truth

- `docs/` supersedes any prior conversation, chat thread, or assumption.
  If a decision is not written there, it is not official.
- Before answering an architecture question or writing new content,
  check the relevant `docs/` document — do not rely on memory of an
  earlier session, since status and content can change between sessions.
- `.claude/` is not a second architecture source. It only restates
  `docs/` rules in operational form (checklists, roles, reusable
  scaffolding). It never introduces a rule, boundary, or decision that
  `docs/` does not already contain.

## 3. Never Modify a Frozen Document Unless Explicitly Instructed

Some `docs/` documents have reached `Approved` and, further, **Frozen**.
`.claude/` does not track or restate which ones — that status changes
over time and only `docs/DOCUMENT-INDEX.md` is guaranteed current.
Before editing any `docs/` document, check its status there. Whatever
that status turns out to be, only touch the document when the user's
current instruction explicitly names it and asks for a change. Otherwise,
build new, subordinate documents that cite and defer to it — never
restate, duplicate, or quietly reinterpret its content.

## 4. Follow the Review Workflow

New and revised architecture content moves through one fixed sequence:

```
CTO → Founder Review → Claude → CTO Review → Codex → CTO Review →
Claude Fixes → Final CTO Review → Governance Closeout → Freeze
```

This sits inside the broader lifecycle defined by `XP-0000`–`XP-0002`
(`Planned → Draft → In Review → Approved`). See
`.claude/context/review-workflow.md` and `.claude/workflows/` for the
operational detail. Only the Founder moves a document to `Approved`; no
AI agent — Claude Code included — ever sets that status itself.

## 5. Prefer Minimal, Precise Edits

- Change exactly what the task asks for. Do not restructure, rewrite, or
  "clean up" a document beyond its stated scope.
- When adding to an existing document, extend it in place using its
  established structure and voice rather than replacing whole sections.
- When a document already answers a question correctly, cite it instead
  of restating it elsewhere.

## 6. No Technology Decisions During the Architecture Phase

Constitution, Architecture Map, Domain Architecture, and Module
Architecture documents are technology-independent by design (`XP-0014`
§4, `XP-0010` §3). Do not introduce a framework, database, hosting,
deployment, or vendor decision into this tier of documentation, and do
not let one slip into `.claude/` guidance either — that decision belongs
to a future Implementation Plan, authored only once the architecture it
depends on is `Approved`.

## 7. No Duplicated Governance

Do not re-derive or restate rules that already exist in
`docs/00-governance/`. When a task needs one of those rules, point to it
by ID (e.g. "per `XP-0002`") rather than copying its content into a new
document or into `.claude/`. This keeps exactly one authoritative copy
of every rule in the repository.

## Where to Look Next

| Need | Go to |
|---|---|
| Reusable background on principles, workflow, structure, terms | `.claude/context/` |
| A role definition for a specific kind of review or audit | `.claude/agents/` |
| A repeatable operation (new document, review, freeze prep) | `.claude/commands/` |
| A blank skeleton to start from | `.claude/templates/` |
| An analytical technique (boundary, dependency, duplication checks) | `.claude/skills/` |
| Stable, durable, non-lifecycle facts about this repository | `.claude/memory/` |
| The end-to-end sequence for a recurring process | `.claude/workflows/` |

None of the files in those folders outrank `docs/`. When in doubt, open
the cited `XP-NNNN` document itself.
