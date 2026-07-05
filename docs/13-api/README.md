# Purpose

This document defines the documentation boundaries of `docs/13-api/` —
exactly what belongs inside this folder, and what does not — before any
API documentation is authored.

# Why This Repository Exists

`docs/13-api/` exists to hold API contracts and standards for the
platform, as identified by the approved Documentation Roadmap. API is
treated as an integration governance repository, not a business or
platform domain: it is not one of the five domains `XP-0014` §9
anticipates a Domain Architecture document for, and it is not a Digital
Operating System governed by `XP-0030`. No document is yet registered,
even as `Planned`, in `DOCUMENT-INDEX.md`; the approved Documentation
Roadmap lists this folder as `Future`, with no document currently
identified. This folder is the designated location where API contracts
and standards will be documented once such a document is identified and
authorized.

# Repository Scope

This folder holds documentation that governs how platform consumers
communicate with the backend, and only how platform consumers
communicate with the backend:

- The primary API contracts and standards document(s), once identified,
  registered, and authored.
- Any document the Documentation Dependency Order (`XP-0014` §8)
  recognizes as subordinate to that document, once authorized.
- Internal, non-authoritative planning material for sequencing API's own
  future documentation.

# Out of Scope

- Platform-wide vision, purpose, or audience content — owned by
  `00-company/` and `01-platform/`.
- Core Platform capability content — owned by `02-core-platform/`.
- The constitutional meaning of "Module" itself — owned by `modules/`.
- The constitutional contract every Digital Operating System must
  satisfy — owned by `digital-operating-systems/`.
- Module-specific business logic behind an endpoint — owned by that
  module's own folder.
- Domain or business architecture decisions of any kind — owned by the
  relevant domain's own folder.
- Any other folder's own subject matter, including `03-business-os/`,
  `04-community-os/`, `05-life-os/`, `06-marketplace/`, `07-payments/`,
  `08-ai/`, `09-mobile/`, `10-devops/`, `11-security/`, `12-ui-ux/`,
  `15-development/`, or any other numbered folder — each owns its own
  documentation exclusively.
- Any documentation not yet authorized to be written under the Docs-First
  Rule and the Approval Gate.

# Architectural Dependencies

- `02-core-platform/` — must remain `Approved` as the foundation any
  eventual API contracts document builds on, per the approved
  Documentation Roadmap.

# Downstream Documentation

Per the approved Documentation Roadmap, `09-mobile/` identifies this
folder as one of its dependencies. No other folder in the approved
roadmap lists a dependency on this one.

# Candidate Documents

- **API Contracts & Standards** — the primary API contracts and
  standards document; no specific title or number is yet registered in
  `DOCUMENT-INDEX.md`, and its exact form is not decided by this
  document.

# Current Status

`docs/13-api/` currently contains no authored API documentation and no
document yet registered in `DOCUMENT-INDEX.md`, per the approved
Documentation Roadmap's `Future` status for this folder.
