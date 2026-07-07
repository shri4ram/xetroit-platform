# Purpose

This document defines the documentation boundaries of `docs/03-business-os/`
— exactly what belongs inside this folder, and what does not — before any
Business OS documentation is authored.

# Why This Repository Exists

`docs/03-business-os/` exists because `XP-0014` §9 anticipates a Domain
Architecture document for Business OS as one of the five major
architectural domains, and `XP-0030` establishes the constitutional
contract that document must satisfy once authored. This folder is the
designated location where that responsibility is discharged. It answers
only why this folder exists as a documentation location — not why
Business OS itself exists as a product, which is Business OS content and
out of scope for this document.

# Repository Scope

This folder holds documentation that describes Business OS, and only
Business OS, as one Digital Operating System instance:

- The Business OS Domain Architecture document, once authored, satisfying
  the contract `XP-0030` establishes for every Digital Operating System.
- Any Module Architecture, Feature Specification, or Implementation Plan
  document that the Documentation Dependency Order (`XP-0014` §8)
  recognizes as subordinate to Business OS's own Domain Architecture,
  once each is actually authorized to be written.
- Internal, non-authoritative planning material for sequencing Business
  OS's own future documentation.

# Out of Scope

- Platform-wide vision, purpose, or audience content — owned by
  `00-company/` and `01-platform/`.
- Core Platform capability content — owned by `02-core-platform/`.
- The constitutional meaning of "Module" itself — owned by `modules/`.
- The constitutional contract every Digital Operating System must
  satisfy — owned by `digital-operating-systems/`.
- Any other folder's own subject matter, including `04-community-os/`,
  `05-life-os/`, `06-marketplace/`, `07-payments/`, `08-ai/`, or any other
  numbered folder — each owns its own documentation exclusively.
- Any documentation not yet authorized to be written under the Docs-First
  Rule and the Approval Gate.

# Architectural Dependencies

- `02-core-platform/` — must be `Approved` before this folder's Domain
  Architecture document can become authoritative, per `XP-0014` §8.
- `digital-operating-systems/` — the contract this folder's Domain
  Architecture document must satisfy.
- `modules/` — governs any Module Architecture document this folder later
  hosts.
- `01-platform/` — establishes this folder's place in the Documentation
  Dependency Order and the Future Architecture Document Roadmap.

# Downstream Documentation

Per the approved Documentation Roadmap, `06-marketplace/` identifies this
folder as one of the folders its own classification may depend on; that
classification remains undetermined and is not decided by this document.
No other folder in the approved roadmap lists a dependency on this one.

# Candidate Documents

- **Business OS Domain Architecture** — the single document satisfying
  `XP-0030`'s contract for Business OS, anticipated by `XP-0014` §9. Now
  authored as `XP-0031` (see Current Status).

# Current Status

`docs/03-business-os/` now contains `XP-0031 — Business Operating System
Domain Architecture`, registered in `DOCUMENT-INDEX.md` as `Draft`, Owner
Founder. It applies `XP-0030`'s constitutional contract to Business OS
and identifies no specific Module, capability, workflow, or
implementation detail — those remain deferred to Business OS's own
future Module Architecture, Feature Specification, and Implementation
Plan documents, once `XP-0031` itself reaches `Approved`.
