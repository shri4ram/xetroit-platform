# Context: Documentation Writing Standard

Authoritative source: `docs/00-governance/xp-0010-documentation-writing-standard.md`.
This is a quick-reference distillation for drafting or reviewing a
document; read `XP-0010` in full before making a judgment call it doesn't
cover here.

## Five Recognized Document Patterns (XP-0010 §3)

| Pattern | Used by | Shape |
|---|---|---|
| Specification | Governance, module/feature architecture | Full `DOCUMENT-TEMPLATE.md` skeleton |
| Narrative/Vision | Company-level vision (e.g. `XP-0009`) | Custom outline, stated explicitly up front |
| Domain Architecture | `XP-0015` onward, and cross-cutting foundations like the Module Foundation | Numbered sections, `Purpose` → `Architecture Governance`, no metadata table or Revision History unless required |
| ADR | Architecture Decision Records | Fixed template in `XP-0004` |
| Navigation | Folder `README.md` files | Lightweight: Purpose, contents, status |

Never mix patterns within one document. State which pattern is in use if
it isn't obvious from the folder/section shape.

## Domain Architecture Characteristics (the pattern most new work uses)

- Architecture-first: principles, boundaries, responsibilities only —
  never implementation, protocol, schema, or technology.
- Implementation-independent: no framework, database, API, or vendor
  decision.
- Ownership-focused: states plainly what it owns and what it explicitly
  does not.
- Dependency-aware: states what it depends on, and stays subordinate to
  every frozen document it cites.
- Document Minimalism: no section beyond what defining the domain at a
  constitutional level actually requires.

## Style Rules Worth Remembering

- Rule-strength words carry real weight: **must/must not** (non-negotiable),
  **should/should not** (deviate only with stated reasoning), **may**
  (genuine discretion). Don't use them interchangeably.
- No marketing language or unverified superlatives.
- Third-person, company-voice narration; no invented first-person quotes
  attributed to a specific person.
- ISO 8601 dates (`YYYY-MM-DD`).
- A section that doesn't apply is marked `N/A` with a one-line reason —
  never deleted.

## Blueprints and Planning Documents Are Not Architecture

A Blueprint or Planning document may precede and inform a Domain
Architecture document, but carries no authority of its own and is not
held to the Domain Architecture pattern. Never treat one as authoritative
or as satisfying the Approval Gate. See
`.claude/templates/blueprint.md` and `.claude/commands/blueprint.md`.

## Related

- `docs/DOCUMENT-TEMPLATE.md` — the Specification-pattern skeleton.
- `.claude/templates/domain-architecture.md` — a ready-to-use Domain
  Architecture skeleton.
- `.claude/context/repository-structure.md` — naming and folder rules
  (`XP-0003`), which this standard complements rather than repeats.
