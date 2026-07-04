# Context: Terminology Discipline

Authoritative source: `docs/GLOSSARY.md`. This file is a reminder to use
it, not a replacement for it — `GLOSSARY.md` is updated as new documents
introduce new terms; this file is not.

## The Rule

Check `docs/GLOSSARY.md` before assuming what a term means, and before
introducing a new one. If a term is defined in detail by a specific
`XP-NNNN` document, that document is the authority; the glossary entry is
a pointer to it, not a restatement.

## Terms Most Often Misused or Conflated

- **Digital Operating System** vs. **Module** — a Digital Operating
  System is composed of Modules; it is never itself a Module. Ownership
  differs by kind, so never use the generic term "Module" alone to state
  ownership: a **Digital Operating System Module** belongs to exactly one
  Digital Operating System; a **Core Platform Module** belongs to exactly
  one already-`Approved` Core Platform Domain, not to any Digital
  Operating System (`XP-0026` §3, §7, §9–§10).
- **Domain Architecture** vs. **Module Architecture** vs. **Feature
  Specification** vs. **Implementation Plan** — four distinct tiers of
  decreasing scope, defined in `XP-0014` §4. Don't use one name for
  content that actually belongs at another tier.
- **Capability** vs. **Feature** vs. **Workflow** vs. **Configuration** —
  the classification vocabulary in `XP-0027`; a proposed piece of work
  gets exactly one of these labels, chosen by the criteria in that
  document, not by which one sounds most significant.
- **Core Platform** vs. **Shared Ecosystem Services** — foundational,
  every-Operating-System capability vs. ecosystem-wide experiences built
  on top of it (`XP-0011`).
- **Approved** vs. **Frozen** — every Frozen document is `Approved`, but
  `Approved` alone doesn't imply the document has also been marked
  Frozen; check the document itself.
- **Foundation Draft** — not a lifecycle status. Never treat it as
  equivalent to `Draft` (`XP-0000`).

## When Writing New Content

- Reuse an existing term exactly as `GLOSSARY.md` or its source document
  defines it — don't quietly redefine it or introduce a near-synonym.
- If a genuinely new term is needed, define it once in the document that
  introduces it, and note that `GLOSSARY.md` should gain an entry
  pointing back to that document.
- Flag, rather than silently resolve, any place where two existing
  documents appear to use the same term differently.
