# Repository Standards

## Document Metadata

| Field | Value |
|---|---|
| **Document ID** | XP-0003 |
| **Title** | Repository Standards |
| **Version** | 0.3 |
| **Status** | Draft |
| **Owner** | Founder |
| **Category** | Governance |
| **Priority** | High |
| **Audience** | Developers / Architects / AI Agents |
| **Last Updated** | 2026-07-06 |
| **Related Documents** | XP-0000, XP-0003 (self), XP-0004, XP-0010 — Documentation Writing Standard |

---

## Purpose

Defines the concrete file, folder, and formatting conventions used across
the entire `docs/` tree, so that both humans and AI agents can predict a
document's location and filename without asking.

## Scope

Covers file naming, folder structure rules, and markdown formatting
conventions for all documentation. Does not cover source code style
(reserved for a future `15-development/` document, out of scope here).

## Goals

- Eliminate ambiguity in file naming, including fixing the inconsistency
  between earlier examples in this repository.
- Make folder-vs-number placement rules explicit.
- Keep documents parseable by AI agents via a consistent structure.

## Non-Goals

- Does not define document *content* structure — see
  `DOCUMENT-TEMPLATE.md`.
- Does not define source code conventions.

## Dependencies

`xp-0000-documentation-governance.md` (numbering convention this builds on).

## Architecture Notes

N/A.

## Business Rules

N/A — this document is purely a technical/repository convention.

## Technical Rules

### File Naming Convention

**All `XP-NNNN` document files use lowercase, hyphen-separated
("kebab-case") names in the form:**

```
xp-nnnn-short-descriptive-slug.md
```

Examples: `xp-0000-documentation-governance.md`,
`xp-0004-architecture-decision-records.md`.

> **Correction note:** `CONTRIBUTING.md` previously showed an example
> filename in uppercase (`XP-0004-business-os.md`). That example
> conflicted with the convention established by the governance documents
> in this folder and has been corrected to lowercase to match. Lowercase
> kebab-case is the single official convention going forward — there is no
> uppercase variant.

Non-`XP` repository files (`README.md`, `CHANGELOG.md`,
`CONTRIBUTING.md`, `GLOSSARY.md`, `DOCUMENT-INDEX.md`,
`DOCUMENT-TEMPLATE.md`) keep their existing uppercase names, since they are
fixed, singular, well-known entry points rather than a numbered series.

### Folder Structure Rules

- Every top-level folder under `docs/` is a two-digit numbered prefix
  followed by a lowercase, hyphen-separated name (e.g. `03-business-os/`).
- `00-` is reserved for foundational, pre-architecture concerns: identity
  (`00-company/`) and process authority (`00-governance/`). Both may
  coexist under `00-` because they answer different questions ("who we
  are" vs. "how we decide"), not because folder numbers indicate strict
  sequential order.
- `99-ai-context/` is reserved specifically for AI-agent-facing
  navigation/context content and stays last by convention.
- A small number of top-level folders are **unnumbered**, reserved for
  cross-cutting architecture that applies across every Digital Operating
  System rather than belonging to any one numbered domain folder:
  `modules/` (Module Architecture, `XP-0026`–`XP-0029`) and
  `digital-operating-systems/` (Digital Operating System Architecture,
  `XP-0030`) are the two current examples. Each holds the constitutional
  contract a whole category of future documents must follow, not a
  specific domain's own content, which is why it sits outside the
  two-digit numbering scheme entirely rather than claiming a number.
- A new top-level folder — numbered or unnumbered — may only be added by
  updating this document and the repository structure diagram in
  `docs/README.md` in the same change.
- A document lives in the folder matching its primary subject domain,
  regardless of its `XP-NNNN` number — the folder does not need to match
  numeric order.
- A non-authoritative Blueprint planning artifact (as defined in
  `xp-0010-documentation-writing-standard.md` §3) is placed in a
  `blueprints/` subfolder within the existing top-level folder that owns
  the authoritative document, repository scope, or document set the
  Blueprint directly prepares or supports — never in a top-level folder
  of its own, and never in a top-level folder that does not already
  exist.

### Markdown Formatting Conventions

- Use `#` for the document title, `##` for major sections matching
  `DOCUMENT-TEMPLATE.md`, and `###` for subsections within those.
- Use tables for anything structurally tabular (metadata, statuses, roles,
  matrices) rather than prose lists, so AI agents can parse fields
  reliably.
- Internal links between documents use relative paths (e.g.
  `../00-governance/xp-0001-ai-engineering-governance.md`), never absolute
  paths or URLs.
- Every substantive document (one with an `XP-NNNN` ID) must use the full
  `DOCUMENT-TEMPLATE.md` structure. Folder `README.md` files are
  navigation aids and are exempt from the full template, but must state
  Purpose, contents, and current status at minimum.

## AI Agent Notes

- When creating a new `XP-NNNN` document, always use the lowercase
  kebab-case filename convention defined above — never the uppercase
  pattern from earlier repository history.
- Do not invent new top-level numbered folders without flagging the need
  explicitly; folder creation changes this document and must be treated
  with the same care as a governance change.

## Open Questions

None at this time.

## Approval Checklist

- [ ] Content reviewed by Founder
- [ ] Reviewed by ChatGPT (CTO / Product Architect)
- [ ] Reviewed by Codex
- [ ] No open blocking questions remain
- [ ] Cross-references updated in `DOCUMENT-INDEX.md`
- [ ] Status updated in document metadata and `DOCUMENT-INDEX.md`

## Revision History

| Version | Date | Author | Summary of Change |
|---|---|---|---|
| 0.1 | 2026-07-02 | Claude Code | Initial draft: file naming convention (with correction of prior uppercase example), folder structure rules, markdown conventions. |
| 0.2 | 2026-07-04 | Claude Code | Recognized unnumbered top-level folders as an approved category for cross-cutting architecture spanning every Digital Operating System (`modules/`, and newly `digital-operating-systems/` for `XP-0030`), distinct from the two-digit numbered domain folders. No renumbering or reordering of existing numbered folders. |
| 0.3 | 2026-07-06 | Claude Code | Closed a governance gap in Folder Structure Rules: added one generic rule stating that a non-authoritative Blueprint planning artifact (per `xp-0010-documentation-writing-standard.md` §3) is placed in a `blueprints/` subfolder of the existing top-level folder it informs, never as a new top-level folder and never inside one that does not already exist. Introduces no numbering scheme, names no specific Blueprint type, and does not redefine what a Blueprint is. No other top-level rule changed; no other document modified. |
