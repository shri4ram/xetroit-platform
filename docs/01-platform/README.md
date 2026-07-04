# 01 — Platform

**Status:** Foundation Draft

## Purpose

This folder holds the platform-wide master plan and top-level architecture
that ties all individual modules (Business OS, Community OS, Life OS,
Marketplace, Payments, AI, Mobile, etc.) together into one coherent system.
It is the bridge between company vision (`00-company/`) and the detailed,
module-specific architecture documents found in later folders.

## Documents That Belong Here

- The platform master plan (product scope, roadmap at a strategic level)
- Top-level system architecture: how modules relate, shared services,
  cross-cutting concerns
- The master navigation map for how architecture documentation is
  organized and in what order it must be produced
- High-level data flow and integration boundaries between modules

Technology-specific direction (framework, language, vendor choices)
belongs to a separate, later Implementation Plan document, not here — see
`XP-0014`'s Architecture Vocabulary.

Module-specific implementation detail belongs in that module's own folder
(e.g. `03-business-os/`), not here.

## Current Status

**Foundation Draft** — folder structure established. Four documents
authored so far:

- [`XP-0011 — XETROIT: The Unified Digital Platform`](xp-0011-xetroit-unified-digital-platform.md)
  (status `Approved`) — the executive overview of what the platform is.
  Fulfills the previously unnumbered "XETROIT Platform Master Plan"
  placeholder.
- [`XP-0012 — How XETROIT Works`](xp-0012-how-xetroit-works.md)
  (status `Approved`) — the conceptual architecture of how the platform's
  layers fit together. Fulfills the previously unnumbered, conceptual
  "Platform Architecture" placeholder.
- [`XP-0013 — Who XETROIT Serves`](xp-0013-who-xetroit-serves.md)
  (status `Approved`) — the business-level description of every primary
  audience the platform is designed to serve. Completes the Platform
  Constitution alongside `XP-0009`, `XP-0011`, and `XP-0012`.
- [`XP-0014 — XETROIT Platform Architecture Map`](xp-0014-platform-architecture-map.md)
  (status `Approved`) — the master navigation map defining the Architecture
  Vocabulary and the documentation dependency order for every Domain
  Architecture document that follows, including `02-core-platform/`.

A separate, more detailed, **technology-specific** architecture document
(naming actual technology choices) remains planned and currently
unnumbered — see `../DOCUMENT-INDEX.md`.
