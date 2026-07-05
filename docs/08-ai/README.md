# Purpose

This document defines the documentation boundaries of `docs/08-ai/` —
exactly what belongs inside this folder, and what does not — before any
AI documentation is authored.

# Why This Repository Exists

`docs/08-ai/` exists because the approved Documentation Roadmap
identifies AI as a folder with a document already registered as
`Planned` (per the "Numbering Collision — Resolved" section of
`DOCUMENT-INDEX.md`). Like Marketplace and Payments, AI is not one of the
five domains `XP-0014` §9 anticipates a Domain Architecture document for,
and it is not a Digital Operating System governed by `XP-0030`. Its
exact architecture tier is not otherwise specified by the approved
Documentation Roadmap or Repository Documentation Matrix, and is not
decided by this document. This folder is the designated location where
that architecture will be documented once authored.

# Repository Scope

This folder holds documentation that describes AI, and only AI, as a
platform capability:

- The single primary architecture document for AI, once authored.
- Any Feature Specification or Implementation Plan document that the
  Documentation Dependency Order (`XP-0014` §8) recognizes as subordinate
  to that document, once each is actually authorized to be written.
- Internal, non-authoritative planning material for sequencing AI's own
  future documentation.

# Out of Scope

- Platform-wide vision, purpose, or audience content — owned by
  `00-company/` and `01-platform/`.
- Core Platform capability content — owned by `02-core-platform/`.
- The constitutional meaning of "Module" itself — owned by `modules/`.
- The constitutional contract every Digital Operating System must
  satisfy — owned by `digital-operating-systems/`, and not assumed to
  apply here unless AI's eventual classification places it under a
  Digital Operating System.
- Generic AI-agent operating context for navigating `docs/` — owned by
  `99-ai-context/`, as already distinguished by the approved Documentation
  Roadmap.
- Any other folder's own subject matter, including `03-business-os/`,
  `04-community-os/`, `05-life-os/`, `06-marketplace/`, `07-payments/`, or
  any other numbered folder — each owns its own documentation
  exclusively.
- Any documentation not yet authorized to be written under the Docs-First
  Rule and the Approval Gate.

# Architectural Dependencies

- `02-core-platform/` — must remain `Approved` as the foundation any
  eventual AI architecture document builds on.

# Downstream Documentation

No folder in the approved Documentation Roadmap lists a dependency on
this one.

# Candidate Documents

- **AI Domain Architecture** — the single primary architecture document
  for AI; its exact tier is not specified by the approved Documentation
  Roadmap or Repository Documentation Matrix, and is not decided by this
  document.

# Current Status

`docs/08-ai/` currently contains no authored AI documentation. Its
planned architecture document remains unnumbered and unassigned, per the
"Numbering Collision — Resolved" section of `DOCUMENT-INDEX.md`.
