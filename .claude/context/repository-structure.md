# Context: Repository Structure

Authoritative sources: `docs/00-governance/xp-0003-repository-standards.md`
(naming/folder rules) and `docs/README.md` (folder-by-folder purpose).
This file is a navigation aid only.

## Folder Map (see `docs/README.md` for the full, current tree)

```
docs/
├── 00-governance/     Documentation & AI engineering governance
├── 00-company/        Company vision, mission, philosophy
├── 01-platform/       Platform-wide architecture and master plan
├── 02-core-platform/  Core Platform Domain Architecture (XP-0015–0025)
├── modules/           Module Foundation (XP-0026–0029) — cross-cutting,
│                      not tied to one numbered folder
├── 03…16-*/           One numbered folder per Digital Operating System
│                      or other major product/technical area
├── 99-ai-context/      AI-agent-facing navigation/context
└── archive/            Superseded or exploratory material
```

## File Naming (XP-0003)

- Every `XP-NNNN` document: lowercase kebab-case —
  `xp-nnnn-short-descriptive-slug.md`. No uppercase variant.
- Fixed, singular entry points (`README.md`, `CHANGELOG.md`,
  `CONTRIBUTING.md`, `GLOSSARY.md`, `DOCUMENT-INDEX.md`,
  `DOCUMENT-TEMPLATE.md`) keep their existing uppercase names.

## Folder Rules (XP-0003)

- Top-level folders under `docs/` are two-digit-numbered,
  lowercase-hyphenated (e.g. `03-business-os/`).
- `00-` is reserved for pre-architecture concerns (identity, process
  authority). `99-ai-context/` stays last by convention.
- **A new top-level folder is never added casually** — it requires
  updating `xp-0003-repository-standards.md` and the structure diagram
  in `docs/README.md` in the same change. Flag the need explicitly
  instead of creating one ad hoc.
- A document's folder matches its subject domain, not its numeric ID —
  the `XP-NNNN` ID, not the folder, is the canonical cross-reference.

## Numbering (XP-0000, XP-0003)

- `XP-NNNN` numbers are assigned once, in order, only when a document is
  registered in `DOCUMENT-INDEX.md` — never speculatively, never reused.
- Check `DOCUMENT-INDEX.md` for the next unused number before creating a
  new document; do not guess or rely on a prior session's count.

## Before Creating Anything New

1. Check `docs/DOCUMENT-INDEX.md` — the topic may already exist or be
   `Planned`.
2. Confirm which existing folder fits. If none genuinely fits, say so
   explicitly rather than forcing a placement or inventing a folder.
3. Follow `docs/CONTRIBUTING.md` for the mechanical steps.
