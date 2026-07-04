# Skill: Boundary Analysis

Checks whether a document's ownership boundary is clear and non-
overlapping, per the Domain Architecture pattern's "ownership-focused"
characteristic (`docs/00-governance/xp-0010-documentation-writing-standard.md`
§3).

## Method

1. List what the document says it owns (its Responsibilities).
2. List what it explicitly says it does not own (its Non-Responsibilities).
3. For each neighboring domain, module, or Shared Ecosystem Service it
   touches, confirm that neighbor's own document draws the boundary the
   same way — from both sides, the line should be in the same place.
4. Check that the boundary is defined by cohesive function, not by
   implementation convenience (the test `XP-0026` §11 uses for Modules).

## Red Flags

- A responsibility stated here that another `Approved` document already
  claims.
- A boundary justified by "it was easier to build this way" rather than
  by what function is cohesive.
- Non-Responsibilities section that is thin or missing where the
  document clearly borders a Core Platform domain or Shared Ecosystem
  Service.
- Two documents that each assume the other owns a specific
  responsibility, leaving it owned by neither.

## Reference

`docs/02-core-platform/xp-0015-core-platform-domain-architecture.md` (via
`blueprints/`) and `docs/modules/xp-0026-module-architecture.md` are the
clearest existing examples of boundary statements done well — each names
what it owns, what it doesn't, and why.
