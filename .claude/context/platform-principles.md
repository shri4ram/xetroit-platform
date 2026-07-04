# Context: Platform Principles

Authoritative source: `docs/00-governance/xp-0005-engineering-principles.md`.
This is a quick-reference distillation, not a substitute — read `XP-0005`
for the full rationale behind each principle before relying on this list
in a judgment call.

## The Twelve Principles (names only — see XP-0005 for detail)

1. Simplicity Over Complexity
2. Platform Before Product
3. Reuse Before Duplication
4. Documentation Before Implementation
5. Security by Design
6. AI Augments Humans
7. API-First Thinking
8. Modular Architecture
9. Consistency Over Cleverness
10. Long-Term Maintainability
11. Progressive Enhancement
12. Measurable Quality

## How to Use These

- Treat them as binding, not aspirational — a design that violates one
  without a documented, reasoned exception (an ADR, per `XP-0004`) is
  incorrect, not merely suboptimal.
- When a task's instructions are ambiguous, resolve the ambiguity in the
  direction these principles point, then flag the ambiguity rather than
  silently guessing.
- Principles 2 and 3 (Platform Before Product, Reuse Before Duplication)
  are the ones most often relevant to architecture documentation work:
  before proposing a new capability, boundary, or document, check whether
  an existing Core Platform domain, Shared Ecosystem Service, or Module
  already covers it.

## The Canonical Platform Shape

Every principle above operates within one fixed layer model, established
in `XP-0011`, `XP-0012`, and `XP-0014` §5, and repeated identically
everywhere it appears:

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

A capability belongs at the lowest layer that lets every layer above it
reuse it once, never rebuilt per Digital Operating System. See
`.claude/context/repository-structure.md` for how this maps to folders,
and `.claude/skills/duplication-detection.md` for how to check a proposal
against it.

## Related

- `docs/00-governance/xp-0006-engineering-decision-pyramid.md` — how these
  principles rank against Founder Vision, Governance, and Architecture
  when two rules conflict.
- `docs/00-governance/xp-0008-ai-decision-checklist.md` — the pre-flight
  checklist that operationalizes these principles before any change.
