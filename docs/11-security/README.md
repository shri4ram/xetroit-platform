# Purpose

This document defines the documentation boundaries of `docs/11-security/`
— exactly what belongs inside this folder, and what does not — before any
Security documentation is authored.

# Why This Repository Exists

`docs/11-security/` exists to hold platform-wide security architecture
and policy once such a document is identified and authorized. Unlike
Business OS, Community OS, Life OS, Marketplace, Payments, and AI,
Security has no document yet registered — even as `Planned` — in
`DOCUMENT-INDEX.md`; the approved Documentation Roadmap lists it as
`Future`, with no document currently identified. Security is not one of
the five domains `XP-0014` §9 anticipates a Domain Architecture document
for, and it is not a Digital Operating System governed by `XP-0030`. This
folder is the designated location where platform-wide security
architecture will be documented once a document is identified and
registered.

# Repository Scope

This folder holds documentation that describes platform-wide security,
and only platform-wide security:

- The single primary architecture document for Security, once identified,
  registered, and authored.
- Any Feature Specification or Implementation Plan document that the
  Documentation Dependency Order (`XP-0014` §8) recognizes as subordinate
  to that document, once each is actually authorized to be written.
- Internal, non-authoritative planning material for sequencing Security's
  own future documentation.

# Out of Scope

- Platform-wide vision, purpose, or audience content — owned by
  `00-company/` and `01-platform/`.
- Core Platform capability content — owned by `02-core-platform/`.
- The constitutional meaning of "Module" itself — owned by `modules/`.
- The constitutional contract every Digital Operating System must
  satisfy — owned by `digital-operating-systems/`, and not assumed to
  apply here unless Security's eventual classification places it under a
  Digital Operating System.
- Payment-specific compliance — owned by `07-payments/`.
- Any other folder's own subject matter, including `03-business-os/`,
  `04-community-os/`, `05-life-os/`, `06-marketplace/`, `08-ai/`, or any
  other numbered folder — each owns its own documentation exclusively.
- Any documentation not yet authorized to be written under the Docs-First
  Rule and the Approval Gate.

# Architectural Dependencies

- `02-core-platform/` — notably its Identity and Trust & Accountability
  domains, must remain `Approved` as the foundation any eventual Security
  architecture document builds on.

# Downstream Documentation

No folder in the approved Documentation Roadmap lists a dependency on
this one.

# Candidate Documents

- **Security Domain Architecture** — the single primary architecture
  document for Security; unlike the folders already covered by this
  standard, no working title for this document is yet registered in
  `DOCUMENT-INDEX.md`, and its exact tier is not decided by this
  document.

# Current Status

`docs/11-security/` currently contains no authored Security
documentation and no document yet registered in `DOCUMENT-INDEX.md`,
per the approved Documentation Roadmap's `Future` status for this
folder.
