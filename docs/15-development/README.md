# Purpose

This document defines the documentation boundaries of
`docs/15-development/` — exactly what belongs inside this folder, and
what does not — before any Development documentation is authored.

# Why This Repository Exists

`docs/15-development/` exists to hold engineering standards and workflow
practices for developers and AI coding agents, as identified by the
approved Documentation Roadmap. Unlike the domain and platform-capability
folders already covered by this standard, Development is not one of the
five domains `XP-0014` §9 anticipates a Domain Architecture document
for, it is not a Digital Operating System governed by `XP-0030`, and —
per the approved Documentation Roadmap — its own scope explicitly
excludes domain or business architecture decisions. No document is yet
registered, even as `Planned`, in `DOCUMENT-INDEX.md`; the approved
Documentation Roadmap lists this folder as `Future`, with no document
currently identified. This folder is the designated location where
engineering standards and workflow practices will be documented once
such a document is identified and authorized.

# Repository Scope

This folder holds documentation that describes how engineering work is
done, and only how engineering work is done:

- The primary engineering standards and workflow document(s) for
  Development, once identified, registered, and authored.
- Any document the Documentation Dependency Order (`XP-0014` §8)
  recognizes as subordinate to that document, once authorized.
- Internal, non-authoritative planning material for sequencing
  Development's own future documentation.

# Out of Scope

- Platform-wide vision, purpose, or audience content — owned by
  `00-company/` and `01-platform/`.
- Core Platform capability content — owned by `02-core-platform/`.
- The constitutional meaning of "Module" itself — owned by `modules/`.
- The constitutional contract every Digital Operating System must
  satisfy — owned by `digital-operating-systems/`.
- Domain or business architecture decisions of any kind — owned by the
  relevant domain's own folder, per the approved Documentation Roadmap's
  own exclusion for this folder.
- Any other folder's own subject matter, including `03-business-os/`,
  `04-community-os/`, `05-life-os/`, `06-marketplace/`, `07-payments/`,
  `08-ai/`, `09-mobile/`, `11-security/`, or any other numbered folder —
  each owns its own documentation exclusively.
- Any documentation not yet authorized to be written under the Docs-First
  Rule and the Approval Gate.

# Architectural Dependencies

- `00-governance/` — must remain authoritative as the foundation any
  eventual Development standards document builds on, per the approved
  Documentation Roadmap.

# Downstream Documentation

No folder in the approved Documentation Roadmap lists a dependency on
this one.

# Candidate Documents

- **Development Standards** — the primary engineering standards and
  workflow document for Development; no specific title or number is yet
  registered in `DOCUMENT-INDEX.md`, and its exact form is not decided by
  this document.

# Current Status

`docs/15-development/` currently contains no authored Development
documentation and no document yet registered in `DOCUMENT-INDEX.md`, per
the approved Documentation Roadmap's `Future` status for this folder.
