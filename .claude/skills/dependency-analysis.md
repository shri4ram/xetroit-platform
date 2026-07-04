# Skill: Dependency Analysis

Checks that a document's dependencies are accurate, resolvable, and
point in the correct direction, per the Domain Architecture pattern's
"dependency-aware" characteristic
(`docs/00-governance/xp-0010-documentation-writing-standard.md` §3).

## Method

1. List everything the document's own `Dependencies` / `Related
   Documents` field names, and confirm each actually exists and each
   relative link resolves.
2. Compare that list against what the document's content actually
   relies on — a missing citation and a stale one are both defects.
3. Check direction against the canonical hierarchy
   (`.claude/context/platform-principles.md`): dependencies flow
   downward (Digital Operating System → Shared Ecosystem Services →
   Core Platform → Infrastructure; Module → parent Domain Architecture).
   A dependency running the other way is a defect, not a stylistic
   choice.
4. Check tier order (`XP-0014` §4, §8): a document never depends on
   authoritative content from a tier that hasn't reached `Approved` yet.

## Red Flags

- A Core Platform domain document referencing a specific Digital
  Operating System or Module.
- A Module Architecture document treated as authoritative before its
  parent Domain Architecture is `Approved`.
- A circular dependency between two documents at the same tier.
- A citation of a document by topic ("the payments document") instead of
  by `XP-NNNN` ID and title, making the dependency hard to verify.

## Reference

`docs/01-platform/xp-0014-platform-architecture-map.md` §7–§8 states the
platform's dependency direction and tier order explicitly.
