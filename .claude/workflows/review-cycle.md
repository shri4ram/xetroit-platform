# Workflow: Review Cycle

Operational form of the document review chain referenced throughout
recent Domain/Module Architecture work, mapped onto the status
transitions defined in `docs/00-governance/xp-0002-approval-workflow.md`.

## The Cycle

```
CTO → Founder Review → Claude → CTO Review → Codex → CTO Review →
Claude Fixes → Final CTO Review → Governance Closeout → Freeze
```

## Step by Step

1. **CTO** — ChatGPT drafts or directs the architecture-level content.
2. **Founder Review** — Founder reviews direction before deeper drafting
   continues.
3. **Claude** — Claude Code structures and refines the document for
   completeness and consistency with existing `Approved` documents
   (`.claude/agents/document-writer.md`,
   `.claude/agents/architecture-reviewer.md`).
4. **CTO Review** — ChatGPT confirms the drafted content is
   architecturally sound; may move `Draft → In Review`
   (`XP-0002` step 3).
5. **Codex** — independent review for correctness, consistency,
   security, and governance compliance
   (`.claude/commands/codex-pass.md` prepares the document for this
   step; Codex performs it).
6. **CTO Review** — findings are triaged.
7. **Claude Fixes** — Claude Code resolves each finding: fixed, or
   explicitly deferred with the Founder's written reasoning
   (`XP-0002`, "Resolving Codex Findings").
8. **Final CTO Review** — confirms all findings are genuinely resolved.
9. **Governance Closeout** — lifecycle bookkeeping is verified: status
   fields, `docs/DOCUMENT-INDEX.md` row, Approval Checklist.
10. **Freeze** — only after the Founder has set `Approved`
    (`.claude/commands/freeze.md`).

## Rules That Apply Throughout

- No step is skipped or reordered; a step may loop backward (e.g. Codex
  findings send the document back to step 3).
- Only the Founder moves a document to `Approved` — no AI role in this
  cycle holds that authority.
- An unresolved finding blocks progress past step 8, regardless of how
  minor it seems.

## Related

- `.claude/context/review-workflow.md` — the same cycle mapped against
  XP-0002's underlying status transitions.
- `.claude/workflows/freeze-process.md` — detail on the final step.
