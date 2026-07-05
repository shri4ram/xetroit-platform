# Purpose

This document defines the documentation boundaries of `docs/09-mobile/`
— exactly what belongs inside this folder, and what does not — before
any Mobile documentation is authored.

# Why This Repository Exists

`docs/09-mobile/` exists because the approved Documentation Roadmap
identifies Mobile as a folder with a document already registered as
`Planned` (per the "Numbering Collision — Resolved" section of
`DOCUMENT-INDEX.md`, under the working title "Mobile Architecture"). Like
Marketplace, Payments, AI, and Security, Mobile is not one of the five
domains `XP-0014` §9 anticipates a Domain Architecture document for, and
it is not a Digital Operating System governed by `XP-0030`. This folder
is the designated location where that architecture will be documented
once authored.

# Repository Scope

This folder holds documentation that describes the Mobile client, and
only the Mobile client:

- The single primary architecture document for Mobile, once authored.
- Any Feature Specification or Implementation Plan document that the
  Documentation Dependency Order (`XP-0014` §8) recognizes as subordinate
  to that document, once each is actually authorized to be written.
- Internal, non-authoritative planning material for sequencing Mobile's
  own future documentation.

# Out of Scope

- Platform-wide vision, purpose, or audience content — owned by
  `00-company/` and `01-platform/`.
- Core Platform capability content — owned by `02-core-platform/`.
- The constitutional meaning of "Module" itself — owned by `modules/`.
- The constitutional contract every Digital Operating System must
  satisfy — owned by `digital-operating-systems/`, and not assumed to
  apply here unless Mobile's eventual classification places it under a
  Digital Operating System.
- Backend API contracts owned by the platform — owned by `13-api/`,
  though consumed here.
- Any other folder's own subject matter, including `03-business-os/`,
  `04-community-os/`, `05-life-os/`, `06-marketplace/`, `07-payments/`,
  `08-ai/`, `11-security/`, or any other numbered folder — each owns its
  own documentation exclusively.
- Any documentation not yet authorized to be written under the Docs-First
  Rule and the Approval Gate.

# Architectural Dependencies

- `02-core-platform/` — must remain `Approved` as the foundation any
  eventual Mobile architecture document builds on.
- `13-api/` — the backend API contracts Mobile consumes, per the approved
  Documentation Roadmap.

# Downstream Documentation

Per the approved Documentation Roadmap, `12-ui-ux/` identifies this
folder as one of its dependencies. No other folder in the approved
roadmap lists a dependency on this one.

# Candidate Documents

- **Mobile Domain Architecture** — the single primary architecture
  document for Mobile; registered in `DOCUMENT-INDEX.md`'s "Numbering
  Collision — Resolved" table under the working title "Mobile
  Architecture," its exact tier is not decided by this document.

# Current Status

`docs/09-mobile/` currently contains no authored Mobile documentation.
Its planned architecture document remains unnumbered and unassigned, per
the "Numbering Collision — Resolved" section of `DOCUMENT-INDEX.md`.
