# Skill: Duplication Detection

Checks a proposed capability, boundary, or document against Reuse
Before Duplication (`docs/00-governance/xp-0005-engineering-principles.md`,
Principle 3) before it is written down as something new.

## Method

1. Before drafting a new responsibility, search existing Core Platform
   domains (`docs/02-core-platform/`), Shared Ecosystem Services
   (`XP-0011`), and existing Modules for an equivalent capability.
2. If something close already exists, default to extending or citing it
   rather than restating or rebuilding it under a new name.
3. Where a capability seems needed by more than one Digital Operating
   System, treat that as a signal it belongs at the Core Platform or
   Shared Ecosystem Services layer, not as a reason to build it once per
   Operating System (`XP-0027` §10–§11).
4. When writing `.claude/` guidance itself, check it isn't restating
   content `docs/` already states — cite instead of copying
   (see `.claude/CLAUDE.md` §7, No Duplicated Governance).

## Red Flags

- A Digital Operating System module owning identity, permissions, audit,
  or another Core Platform responsibility for "convenience"
  (`XP-0026` §5, §10).
- A new document restating another document's content instead of citing
  it.
- A capability description that reads as a rename of an existing one
  rather than something genuinely new.

## Reference

`docs/00-governance/xp-0008-ai-decision-checklist.md` item 3 makes this
check a mandatory, blocking pre-flight question before implementation or
new documentation content.
