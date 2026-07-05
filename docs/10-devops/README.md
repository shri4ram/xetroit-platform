# Purpose

This document defines the documentation boundaries of `docs/10-devops/`
— exactly what belongs inside this folder, and what does not — before
any DevOps documentation is authored.

# Why This Repository Exists

`docs/10-devops/` exists to hold infrastructure, deployment, and
operational practices for the platform, as identified by the approved
Documentation Roadmap. DevOps is treated as an infrastructure and
operational practices repository, not a business or platform domain: it
is not one of the five domains `XP-0014` §9 anticipates a Domain
Architecture document for, and it is not a Digital Operating System
governed by `XP-0030`. No document is yet registered, even as `Planned`,
in `DOCUMENT-INDEX.md`; the approved Documentation Roadmap lists this
folder as `Future`, with no document currently identified. This folder
is the designated location where infrastructure and operational
practices will be documented once such a document is identified and
authorized.

# Repository Scope

This folder holds documentation that describes how the platform is
deployed and operated, and only how the platform is deployed and
operated:

- The primary infrastructure and operational practices document(s) for
  DevOps, once identified, registered, and authored.
- Any document the Documentation Dependency Order (`XP-0014` §8)
  recognizes as subordinate to that document, once authorized.
- Internal, non-authoritative planning material for sequencing DevOps's
  own future documentation.

# Out of Scope

- Platform-wide vision, purpose, or audience content — owned by
  `00-company/` and `01-platform/`.
- Core Platform capability content — owned by `02-core-platform/`.
- The constitutional meaning of "Module" itself — owned by `modules/`.
- The constitutional contract every Digital Operating System must
  satisfy — owned by `digital-operating-systems/`.
- Security policy specifics — owned by `11-security/`.
- Domain or business architecture decisions of any kind — owned by the
  relevant domain's own folder.
- Any other folder's own subject matter, including `03-business-os/`,
  `04-community-os/`, `05-life-os/`, `06-marketplace/`, `07-payments/`,
  `08-ai/`, `09-mobile/`, `15-development/`, or any other numbered
  folder — each owns its own documentation exclusively.
- Any documentation not yet authorized to be written under the Docs-First
  Rule and the Approval Gate.

# Architectural Dependencies

- `02-core-platform/` — must remain `Approved` as the foundation any
  eventual DevOps practices document builds on, per the approved
  Documentation Roadmap.

# Downstream Documentation

No folder in the approved Documentation Roadmap lists a dependency on
this one.

# Candidate Documents

- **Infrastructure & Operational Practices** — the primary infrastructure,
  deployment, and operational practices document for DevOps; no specific
  title or number is yet registered in `DOCUMENT-INDEX.md`, and its exact
  form is not decided by this document.

# Current Status

`docs/10-devops/` currently contains no authored DevOps documentation
and no document yet registered in `DOCUMENT-INDEX.md`, per the approved
Documentation Roadmap's `Future` status for this folder.
