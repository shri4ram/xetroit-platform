# Documentation Writing Standard

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0010 |
| **Title** | Documentation Writing Standard |
| **Version** | 1.0 |
| **Status** | Approved |
| **Owner** | Founder |
| **Category** | Governance |
| **Priority** | High |
| **Audience** | Founder / Architects / Engineers / Technical Writers / AI Coding Agents |
| **Last Updated** | 2026-07-04 |
| **Related Documents** | XP-0000, XP-0002, XP-0003, XP-0004, XP-0005, XP-0007, XP-0014, XP-0015, `DOCUMENT-TEMPLATE.md` |

---

> This document defines *how every future XETROIT document is written* —
> philosophy, style, language, and process. It complements, and does not
> replace, `xp-0003-repository-standards.md` (file naming and folder
> placement) and `DOCUMENT-TEMPLATE.md` (the structural skeleton used by
> specification-style documents). Sections 1–17 below are the required
> content of this standard; a closing Revision History section is appended
> after them, matching the convention every other document in this
> repository follows and that Section 12 (Versioning) itself requires.

## 1. Purpose

This document defines the official writing standard that every future
XETROIT document — governance, architecture, module specification, ADR,
or folder README — must follow. Its goal is to make every document
predictable in shape, precise in language, and equally usable by a human
reader meeting the platform for the first time and an AI agent acting on
it literally.

This standard governs *how* something is written. It does not govern
*what* gets built (that is architecture and business-rule content, out of
scope here) or *where a file lives* (that is `xp-0003`).

## 2. Writing Philosophy

- **Documentation is a specification, not a description.** Per the
  Docs-First Rule (`xp-0000`), a document is written before the thing it
  describes exists — never as a write-up produced afterward.
- **Write for the reader with the least context.** A new engineer, a new
  AI agent, and an investor meeting XETROIT for the first time should all
  be able to follow a document without a live explanation from its author.
- **Clarity over cleverness.** A plain sentence that is immediately
  understood beats an elegant one that requires re-reading.
- **Timelessness over topicality.** Prefer durable statements of
  principle and rule over details that will need constant revision as
  circumstances change. If a fact is likely to be wrong in a year, it
  probably belongs in a more specific, faster-moving document — not here.
- **Precision over ambiguity.** AI coding agents act on what is written,
  literally. An ambiguous sentence is not a stylistic flaw; it is a defect
  with the same weight as a technical error.

## 3. Document Structure Standard

Every document in `docs/` follows one of five recognized structural
patterns. A document must make clear which pattern it follows (by using
that pattern consistently, or by stating it explicitly), and must not mix
patterns within a single document.

| Pattern | Used By | Shape |
|---|---|---|
| **Specification** | Governance and module/feature-level architecture documents | Full `DOCUMENT-TEMPLATE.md` skeleton: Purpose, Scope, Goals, Non-Goals, Dependencies, Architecture Notes, Business Rules, Technical Rules, AI Agent Notes, Open Questions, Approval Checklist, Revision History. |
| **Narrative / Vision** | Company-level vision documents (e.g. `XP-0009`) | A custom, purpose-fit section outline stated explicitly at the top of the document, opening with Document Metadata and closing with Revision History. |
| **Domain Architecture** | Core Platform and future Digital Operating System Domain Architecture documents, at the Domain Architecture tier defined in `XP-0014` (`XP-0015` onward) | A numbered sequence of constitutional sections opening with `Purpose` and closing with `Architecture Governance`. See "Domain Architecture Characteristics" below for its governing principles; exact section names are not prescribed by this standard. |
| **ADR** | Architecture Decision Records | The fixed template defined in `xp-0004-architecture-decision-records.md`. |
| **Navigation** | Folder `README.md` files | Lightweight: Purpose, contents, current status — per `xp-0003`. Exempt from the full specification skeleton. |

Every pattern other than Domain Architecture shares two non-negotiable
bookends: a **Document Metadata** header at the top (for any file with an
`XP-NNNN` ID), and a **Revision History** at the bottom. The Domain
Architecture pattern is the one documented exception to both, per
"Domain Architecture Characteristics" below. Once a document reaches
`In Review`, its section order must not be silently rearranged — a
structural change is itself a revision and must be logged as one, where
the pattern in use carries a Revision History.

**Domain Architecture characteristics.** The Domain Architecture pattern
was established by `XP-0015 — Core Platform Domain Architecture` and has
since been followed consistently by `XP-0016` through `XP-0025`. This
standard recognizes it as an official pattern, distinct from
Specification, without prescribing its exact section names — each Domain
Architecture document names its own sections to fit the domain it
defines, provided it follows these governing principles:

- **Architecture-first.** The document defines principles, boundaries,
  and responsibilities at the constitutional level only — never
  implementation, protocol, schema, or technology detail.
- **Implementation-independent.** No framework, database, API, vendor,
  or infrastructure decision appears in the document, consistent with
  the Domain Architecture tier defined in `XP-0014` Section 4.
- **Ownership-focused.** The document states plainly what the domain
  owns and what it explicitly does not own, so its boundary against
  every neighboring domain stays unambiguous.
- **Dependency-aware.** The document states which other domains it
  depends on and in which direction, and remains consistent with, and
  subordinate to, every frozen document it depends on.
- **No Document Metadata table unless explicitly required.** A Domain
  Architecture document does not carry the Document Metadata table
  described in Section 4 unless a specific document's own governing
  instructions explicitly call for one.
- **No Revision History unless explicitly required.** A Domain
  Architecture document does not carry a Revision History section unless
  a specific document's own governing instructions explicitly call for
  one; its governance and lifecycle status are instead carried by its
  closing Architecture Governance section and by `DOCUMENT-INDEX.md`.
- **Document Minimalism.** A Domain Architecture document owns only the
  universal, platform-level concerns of the domain it defines. It does
  not expand into a neighboring domain's responsibility, and it carries
  no section, detail, or scope beyond what defining that domain at the
  constitutional level requires.

Recognizing this pattern requires no retroactive edit to `XP-0015`
through `XP-0025`, or to any future Domain Architecture document already
written under it — this entry codifies practice already established and
reviewed, rather than introducing a new requirement those documents must
be revised to meet.

**Blueprint and planning documents are not constitutional architecture.**
A **Blueprint** (for example, a CTO Blueprint informing a Domain
Architecture document's drafting) is a planning artifact that precedes
and informs a Domain Architecture document. It is not itself
constitutional architecture, is not held to the Domain Architecture
pattern above, and carries no authority of its own — only the Domain
Architecture document it results in, once frozen, is constitutional. A
**Planning document** (for example, an internal roadmap sequencing
candidate future architecture work) is non-authoritative: it may group,
sequence, or discuss candidate future domains for planning purposes, but
it introduces no capability, boundary, or decision on its own, and no
future document becomes authoritative merely by appearing in one. Neither
a Blueprint nor a Planning document is one of the five patterns in the
table above; both remain working artifacts outside this standard's
document-pattern system.

## 4. Required Metadata

Every `XP-NNNN` document carries the Document Metadata table described
below, with the exception of the Domain Architecture pattern (Section 3),
which does not carry one unless a specific document's own governing
instructions explicitly require it. Where a Document Metadata table is
used, it carries, at minimum: **Document ID, Title, Version, Status,
Owner, Category, Priority, Audience, Last Updated, Related Documents.**

- `Status` must be one of the six lifecycle states defined in `xp-0000`
  (`Planned`, `Draft`, `In Review`, `Approved`, `Deprecated`, `Archived`),
  or, for non-lifecycle scaffolding files only, `Foundation Draft` — never
  used interchangeably with `Draft`.
- `Audience` must name specific reader groups (e.g. "Architects / AI
  Agents"), never a placeholder like "everyone."
- `Related Documents` must list real `XP-NNNN` IDs (or `DOCUMENT-TEMPLATE.md`
  /`DOCUMENT-INDEX.md` where relevant), not vague topic references.
- `Last Updated` uses ISO 8601 (`YYYY-MM-DD`) and must change in the same
  edit as `Version`.

## 5. Required Sections

At minimum, every document must contain:

- An opening section stating why the document exists (`Purpose`, or the
  narrative-pattern equivalent), as the first substantive content after
  the metadata header, or, for the Domain Architecture pattern, as the
  document's first numbered section.
- A closing **Revision History**, except for the Domain Architecture
  pattern, which closes with an **Architecture Governance** section
  instead (Section 3), unless a specific document's own governing
  instructions explicitly require a Revision History too.
- For the **Specification** pattern: every section named in
  `DOCUMENT-TEMPLATE.md`, in order.
- For the **Narrative/Vision** pattern: an explicit statement of what kind
  of document it is and is not (as `XP-0009` does in its opening note).
- For the **Domain Architecture** pattern: sections stating the domain's
  scope, its ownership boundary against every neighboring domain, and its
  dependencies, consistent with the characteristics in Section 3 — exact
  section names remain a document-by-document choice, not prescribed
  here.

A required section may never be silently deleted. If it does not apply,
it is kept and marked `N/A` with a one-line reason (see Section 6). The
Domain Architecture pattern is not held to the Specification pattern's
fixed section list in the first place, so this rule applies within
whatever section set a given Domain Architecture document uses, not
against `DOCUMENT-TEMPLATE.md`.

## 6. Optional Sections

- Sections such as `Architecture Notes`, `Business Rules`, or `Technical
  Rules` that do not apply to a given document are marked `N/A` with a
  short reason — never omitted outright, so that both human readers and
  AI agents can rely on a predictable section list existing (per
  `xp-0003`).
- Diagrams, worked examples, and FAQs are optional additions used only
  when they materially aid understanding — never included for decoration
  or to make a document appear more thorough than its content warrants.

## 7. Writing Style

- Enterprise, professional tone. Concise sentences. Prefer active voice.
- Third-person, company-voice narration by default. First-person ("I,"
  "we believe") is acceptable only as the collective voice of the company
  making a considered statement — never as an invented personal quote
  attributed to a specific individual who did not supply those literal
  words.
- No marketing language, hype, or unverified superlatives ("revolutionary,"
  "world-class," "best-in-class"). A claim belongs in a document only if
  it is true regardless of who is reading it.
- Prefer plain language over unexplained jargon. Define any term that
  isn't self-evident in `GLOSSARY.md` rather than assuming shared
  understanding.

## 8. Language Rules

- Use disciplined rule language, matching the weight of the requirement:
  **must / must not** for non-negotiable rules, **should / should not**
  for strong recommendations that require stated reasoning to deviate
  from, and **may** for genuine discretion. Do not use these words
  interchangeably.
- Avoid ambiguous pronouns without a clear, single antecedent.
- Write all dates in ISO 8601 (`YYYY-MM-DD`).
- Do not state market-size estimates, competitor comparisons, or
  unrealistic business claims in any document unless a specific document's
  own governing instructions explicitly call for them — the default
  assumption is that such claims do not belong in XETROIT documentation.

## 9. Diagrams

- Diagrams are optional and used only when prose alone would make a
  structure or flow meaningfully harder to follow.
- Use text-based diagrams (fenced code blocks, box-drawing characters, or
  simple arrows) rather than embedded binary images, so that every
  diagram stays diffable, versionable in plain text, and directly
  readable by an AI agent.
- A diagram must never be the sole carrier of a requirement — every
  diagram is accompanied by a plain-text explanation of what it shows.

## 10. Tables

- Prefer tables for anything structurally tabular: metadata, statuses,
  role/authority matrices, comparisons, and revision history — this
  repeats and reaffirms the rule already established in `xp-0003`.
- Every table has a header row. Keep cell content concise; link out to
  detail rather than embedding paragraphs inside a cell.

## 11. Cross References

- Internal references use relative Markdown links, never absolute paths
  or external URLs, per `xp-0003`.
- When referencing another document, name both its `XP-NNNN` ID and title
  (e.g., "see `XP-0005 — Engineering Principles`"), so the reference stays
  meaningful even if the document is later moved or reorganized.
- When a reference is about a specific rule rather than a whole document,
  point to the specific section, not just the document as a whole.

## 12. Versioning

- A document starts at version `0.1` when it enters `Draft`.
- Each substantive revision made while the document is below `Approved`
  increments the minor decimal (`0.1` → `0.2` → `0.3`, and so on).
- Upon first reaching `Approved`, the version becomes `1.0`.
- After `Approved`, a change that alters meaning or requirements
  increments the whole number (`1.0` → `2.0`); a change that only
  clarifies existing meaning without altering it increments the decimal
  (`1.0` → `1.1`).
- Every version change is accompanied by a corresponding row in Revision
  History, and `Last Updated` changes in the same edit.

## 13. Review Rules

- Every document is reviewed and approved through the process defined in
  `xp-0002-approval-workflow.md` — this document does not redefine that
  mechanism, it requires compliance with it.
- Minimum review bar before `Approved`: content reviewed by its Owner,
  reviewed by an AI review agent (e.g. Codex) for internal consistency and
  compliance with this writing standard, and no blocking Open Question
  left unresolved.
- A review finding that concerns style or language cites this document's
  specific section; a finding that concerns lifecycle or numbering cites
  `xp-0000` or `xp-0002` instead — findings should always be traceable to
  the rule they are enforcing.

## 14. AI Authoring Rules

- An AI agent drafting a document selects the correct structural pattern
  (Section 3) and follows it completely — no partial or invented hybrid
  structure.
- Every required metadata field and required section must be filled in;
  if a section does not apply, it is marked `N/A` with a reason, never
  left blank or deleted.
- An AI agent does not invent facts, figures, or claims that are not
  already established elsewhere in approved documentation — this
  generalizes the rule applied when drafting `XP-0009`, where an invented
  personal narrative was avoided in favor of the established company
  perspective.
- When writing on behalf of a human role, an AI agent uses neutral,
  third-person company voice. It does not fabricate a first-person quote
  attributed to a specific person unless that person has supplied the
  literal words.
- Genuine gaps are flagged as an **Open Question** or a clearly marked
  placeholder — never silently filled with a guess.
- No AI agent marks any document `Approved`; that remains the Founder's
  authority alone, per `xp-0001-ai-engineering-governance.md`.

## 15. AI Review Rules

- An AI reviewer checks a document against: this writing standard
  (structure, language, table/diagram rules), `xp-0003` (naming and
  folder placement), `xp-0000` (lifecycle and numbering), and the
  document's own internal consistency.
- Findings must be specific and actionable — citing the exact section,
  sentence, or phrase at issue — never a vague note like "improve
  clarity."
- An AI reviewer files findings; it does not silently edit a document to
  resolve its own finding. Any fix still goes through the normal
  authoring and revision process and is logged in Revision History.

## 16. Common Mistakes

- Leaving a section blank instead of marking it `N/A` with a reason.
- Mixing structural patterns — for example, starting from
  `DOCUMENT-TEMPLATE.md` and then dropping half its sections without
  declaring a different pattern is in use.
- Using absolute file paths or external URLs for internal cross-references.
- Writing marketing language or unverified superlatives into a document
  meant to remain timeless.
- Letting `Version` and `Last Updated` drift out of sync with the actual
  edit history.
- Treating `Foundation Draft` as equivalent to `Draft` — it is a distinct,
  non-lifecycle bootstrap marker (see `xp-0000`), a mistake this
  repository has already made and corrected once.
- Attributing a direct quote to a specific person who did not supply
  those literal words.

## 17. Definition of Done

A document is ready to move from `Draft` to `In Review` when:

- All required metadata fields and required sections (Sections 4–5) are
  present and complete, or explicitly marked `N/A` with a stated reason.
- Its language follows the rules in this document — disciplined rule
  language where applicable, no marketing language, ISO-format dates.
- Every cross-reference resolves to a real document or section.
- Revision History reflects the document's current version.
- No unmarked placeholder text remains anywhere in the document.

Reaching `Approved` additionally requires satisfying the review bar in
Section 13 and, where the specification pattern is used, the document's
own Approval Checklist. This Definition of Done is the general readiness
bar this writing standard sets for every document; it does not replace
whatever additional, document-specific checklist a given document also
carries.

## Revision History

| Version | Date | Author | Summary of Change |
|---|---|---|---|
| 0.1 | 2026-07-02 | Claude Code | Initial draft: writing philosophy, document structure patterns, metadata/section requirements, style and language rules, diagram/table/cross-reference conventions, versioning, review rules, AI authoring and review rules, common mistakes, and Definition of Done. |
| 0.2 | 2026-07-04 | Claude Code | Governance alignment: recognized **Domain Architecture** as a fifth official document pattern in Section 3 (table row plus a "Domain Architecture characteristics" entry describing it as architecture-first, implementation-independent, ownership-focused, dependency-aware, exempt from the Document Metadata table and Revision History unless explicitly required, and subject to Document Minimalism — without prescribing exact section names), codifying the pattern already established by `XP-0015` and followed by `XP-0016`–`XP-0025`. Added a clarifying entry that Blueprint and Planning documents are working artifacts, not constitutional architecture, and are not among the five document patterns. Updated Sections 4 and 5 to state the Domain Architecture pattern's exception to the Document Metadata and Revision History requirements. No retroactive edit required to `XP-0015`–`XP-0025`. The four pre-existing patterns (Specification, Narrative/Vision, ADR, Navigation) were not altered. No constitutional architecture document (`XP-0009` and above) was modified as part of this change. |
| 1.0 | 2026-07-04 | Claude Code | Lifecycle synchronization only: `Status` moved `Draft` → `Approved`, `Version` moved `0.2` → `1.0`, per Section 12 of this document's own versioning rule, to match the `Approved` status already recorded in `DOCUMENT-INDEX.md`. No content in Sections 1–17 was changed. |
