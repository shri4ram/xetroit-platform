# Purpose

This document defines the documentation boundaries of `docs/06-marketplace/`
— exactly what belongs inside this folder, and what does not — before any
Marketplace documentation is authored.

# Why This Repository Exists

`docs/06-marketplace/` exists because the approved Documentation Roadmap
identifies Marketplace as a folder with a document already registered as
`Planned` (per the "Numbering Collision — Resolved" section of
`DOCUMENT-INDEX.md`). Unlike Business OS, Community OS, and Life OS,
Marketplace is not one of the five domains `XP-0014` §9 anticipates a
Domain Architecture document for, and it is not a Digital Operating
System governed by `XP-0030`. Its classification — whether it is a
Module, a Capability, a Shared Ecosystem Service, or a Core Platform
responsibility — is not yet determined, per `XP-0027` and the approved
Documentation Roadmap. This folder is the designated location where that
classification, and the architecture document that follows from it, will
be documented once resolved.

# Repository Scope

This folder holds documentation that describes Marketplace, and only
Marketplace:

- The single primary architecture document for Marketplace, once its
  classification against `XP-0027` is resolved and the document is
  authored.
- Any Feature Specification or Implementation Plan document that the
  Documentation Dependency Order (`XP-0014` §8) recognizes as subordinate
  to that document, once each is actually authorized to be written.
- Internal, non-authoritative planning material for sequencing
  Marketplace's own future documentation.

# Out of Scope

- Platform-wide vision, purpose, or audience content — owned by
  `00-company/` and `01-platform/`.
- Core Platform capability content — owned by `02-core-platform/`.
- The constitutional meaning of "Module" itself — owned by `modules/`.
- The constitutional contract every Digital Operating System must
  satisfy — owned by `digital-operating-systems/`, and not assumed to
  apply here unless Marketplace's eventual classification places it under
  a Digital Operating System.
- Payment processing itself — owned by `07-payments/`.
- Any other folder's own subject matter, including `03-business-os/`,
  `04-community-os/`, `05-life-os/`, `08-ai/`, or any other numbered
  folder — each owns its own documentation exclusively.
- Any documentation not yet authorized to be written under the Docs-First
  Rule and the Approval Gate.

# Architectural Dependencies

- `02-core-platform/` — must remain `Approved` as the foundation any
  eventual Marketplace architecture document builds on.
- `modules/` (`XP-0027`) — governs the classification decision this
  folder's primary document depends on.
- `03-business-os/`, `04-community-os/`, `05-life-os/` — one or more may
  become a dependency depending on how Marketplace is classified, per the
  approved Documentation Roadmap; this is not resolved by this document.

# Downstream Documentation

No folder in the approved Documentation Roadmap lists a dependency on
this one.

# Candidate Documents

- **Marketplace Domain Architecture** — the single primary architecture
  document for Marketplace; its exact tier (Domain Architecture vs.
  Module Architecture) depends on the classification against `XP-0027`
  described above and is not decided by this document.

# Current Status

`docs/06-marketplace/` currently contains no authored Marketplace
documentation. Its planned architecture document remains unnumbered and
unassigned, per the "Numbering Collision — Resolved" section of
`DOCUMENT-INDEX.md`.
