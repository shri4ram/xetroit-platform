# Purpose

This document defines the documentation boundaries of `docs/12-ui-ux/`
— exactly what belongs inside this folder, and what does not — before
any UI/UX documentation is authored.

# Why This Repository Exists

`docs/12-ui-ux/` exists to hold the shared design system and UX standards
used across platform surfaces, as identified by the approved
Documentation Roadmap. UI/UX is treated as a design governance
repository, not a business or platform domain: it is not one of the five
domains `XP-0014` §9 anticipates a Domain Architecture document for, and
it is not a Digital Operating System governed by `XP-0030`. No document
is yet registered, even as `Planned`, in `DOCUMENT-INDEX.md`; the
approved Documentation Roadmap lists this folder as `Future`, with no
document currently identified. This folder is the designated location
where shared design and UX standards will be documented once such a
document is identified and authorized.

# Repository Scope

This folder holds documentation that governs shared, platform-wide
design and UX standards, and only shared, platform-wide design and UX
standards:

- The primary design system and UX standards document(s) for UI/UX, once
  identified, registered, and authored.
- Any document the Documentation Dependency Order (`XP-0014` §8)
  recognizes as subordinate to that document, once authorized.
- Internal, non-authoritative planning material for sequencing UI/UX's
  own future documentation.

# Out of Scope

- Platform-wide vision, purpose, or audience content — owned by
  `00-company/` and `01-platform/`.
- Core Platform capability content — owned by `02-core-platform/`.
- The constitutional meaning of "Module" itself — owned by `modules/`.
- The constitutional contract every Digital Operating System must
  satisfy — owned by `digital-operating-systems/`.
- Feature-specific UI behavior — owned by the relevant domain folder
  (e.g. `03-business-os/`).
- Domain or business architecture decisions of any kind — owned by the
  relevant domain's own folder.
- Any other folder's own subject matter, including `04-community-os/`,
  `05-life-os/`, `06-marketplace/`, `07-payments/`, `08-ai/`,
  `09-mobile/`, `10-devops/`, `11-security/`, `15-development/`, or any
  other numbered folder — each owns its own documentation exclusively.
- Any documentation not yet authorized to be written under the Docs-First
  Rule and the Approval Gate.

# Architectural Dependencies

- `02-core-platform/` — notably its Platform Experience domain, must
  remain `Approved` as the foundation any eventual UI/UX standards
  document builds on.
- `09-mobile/` — the client surface UI/UX standards must remain
  consistent with, per the approved Documentation Roadmap.

# Downstream Documentation

No folder in the approved Documentation Roadmap lists a dependency on
this one.

# Candidate Documents

- **Design System & UX Standards** — the primary shared design system
  and UX standards document for UI/UX; no specific title or number is yet
  registered in `DOCUMENT-INDEX.md`, and its exact form is not decided by
  this document.

# Current Status

`docs/12-ui-ux/` currently contains no authored UI/UX documentation and
no document yet registered in `DOCUMENT-INDEX.md`, per the approved
Documentation Roadmap's `Future` status for this folder.
