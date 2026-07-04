# Workflow: New Architecture Document

End-to-end sequence for taking a new architecture topic from idea to a
`Draft` document ready for review. Operational form of the AI Engineering
Workflow (`docs/00-governance/xp-0001-ai-engineering-governance.md`).

## Steps

1. **Idea** — the need is identified (Founder, or ChatGPT with Founder
   sign-off).
2. **Pre-checks** — confirm the topic isn't already `Planned` or
   registered (`docs/DOCUMENT-INDEX.md`); confirm the parent
   architecture it depends on is `Approved`; confirm the correct folder
   (`.claude/context/repository-structure.md`); confirm the next unused
   `XP-NNNN` number.
3. **Architecture** — the approach is designed at architecture level
   (ChatGPT, as CTO / Product Architect), consistent with every frozen
   document it will depend on.
4. **Documentation** — the architecture is written up using the correct
   pattern (`.claude/context/documentation-standard.md`), status
   `Draft`. Use `.claude/commands/new-domain.md` and
   `.claude/templates/domain-architecture.md` (or
   `docs/DOCUMENT-TEMPLATE.md`) as the starting structure.
5. **Claude** — Claude Code structures and refines the draft: complete
   sections or explicit `N/A` with reason, resolved cross-references,
   current Open Questions. Use `.claude/agents/document-writer.md`.
6. **Ready for review** — the document enters the review cycle
   described in `.claude/workflows/review-cycle.md`.

## Forbidden Shortcuts

- Skipping straight to implementation before the document exists and is
  `Approved` (Docs-First Rule, `XP-0000`).
- Assigning an `XP-NNNN` number before registering in
  `docs/DOCUMENT-INDEX.md`.
- Drafting content for a tier whose prerequisite isn't `Approved` yet
  (`XP-0014` §8).

## Output

A `Draft` document, correctly patterned and placed, with Open Questions
recorded for genuine gaps — ready to move into
`.claude/workflows/review-cycle.md`.
