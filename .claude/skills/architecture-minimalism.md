# Skill: Architecture Minimalism

Checks a document against Domain Minimalism and Document Minimalism —
that it carries no section, detail, or scope beyond what its stated
purpose actually requires (`docs/GLOSSARY.md`, "Domain Minimalism" and
"Document Minimalism" entries).

## Method

1. For each section, ask whether removing it would leave the document
   unable to fulfill its stated Purpose. If not, it may be scope creep.
2. Check for sections that only restate another frozen document instead
   of citing it — a restatement is a duplication risk, not thoroughness.
3. Check that the document stays at its own tier: no implementation,
   protocol, schema, or technology decision inside Constitution /
   Architecture Map / Domain Architecture / Module Architecture content
   (`XP-0014` §4).
4. Check that expansion of an existing document's scope is treated as a
   governed change (new revision, re-review), not an informal addition.

## Red Flags

- A "just in case" section with no concrete reader need.
- A Domain Architecture document describing a specific technology,
  vendor, or deployment detail.
- A document's scope quietly growing across small edits without a
  corresponding revision entry.
- Content that duplicates a neighboring or parent document instead of
  citing it by ID.

## Reference

`docs/00-governance/xp-0010-documentation-writing-standard.md` §3
("Document Minimalism") and the Module Foundation's own Architecture
Governance sections (e.g. `docs/modules/xp-0026-module-architecture.md`
§15) apply this discipline explicitly.
