# Core Platform Architecture Roadmap

## 1. Purpose

This is an internal CTO planning artifact for sequencing future Core
Platform architecture work. It exists to organize and order the future
documents that will elaborate on the Core Platform domain, following the
`Approved` and Frozen `XP-0015 — Core Platform Domain Architecture`. It
is a planning aid, not architecture: it introduces no new capability, no
new boundary, and no new decision beyond what `XP-0015` already
establishes.

## 2. Relationship to Frozen Architecture

This is a planning document, not a frozen architecture document.
`XP-0015 — Core Platform Domain Architecture` remains the sole canonical
architecture for the Core Platform domain. This document introduces no
architectural decisions of its own — it only organizes and sequences
future planning work in terms `XP-0015` has already defined.

This document is subordinate to `XP-0015` in every respect. Where
anything here ever appears to conflict with `XP-0015`, `XP-0015` is
correct and this roadmap must be corrected to match — never the reverse.
Nothing in this document authorizes any implementation, module design, or
feature work on its own; that authorization comes only from the
documentation dependency process already established in `XP-0014` and
`XP-0002`.

## 3. Planning Principles

- **Sequence by dependency, not convenience.** Order candidate work by
  what genuinely depends on what, not by what seems easiest to start.
- **Foundation before dependents.** Domains that other domains rely on
  are planned ahead of the domains that rely on them.
- **Nothing invented here.** Every candidate domain in this roadmap
  traces back to a foundation already named in `XP-0015`; this document
  does not introduce a capability `XP-0015` does not already recognize.
- **Suggestions, not commitments.** Every grouping, order, and topic in
  this document is a planning suggestion, subject to change, not a
  commitment to a specific document, sequence, or timeline.
- **Living document.** This roadmap is expected to be revised as planning
  understanding improves; it does not need Founder or Codex approval to
  be updated, because it grants no authority on its own.

## 4. Candidate Core Platform Domains

The following candidate domains are identified for future planning
purposes only. They are named and grouped here for reference; none is
defined, designed, or bounded in this document — that remains the job of
a future Module Architecture document, following `XP-0015`.

For planning convenience, the groups are further organized into three
categories — **Core Platform Domains**, **Cross-Cutting Platform
Services**, and **Supporting Foundations**. This categorization is for
planning discussion only; it is not an architectural decision and does
not appear in, or modify, `XP-0015`.

| Category | Group | Candidate Domains |
|---|---|---|
| Core Platform Domains | Identity & Access | Identity, Authorization |
| Core Platform Domains | Organization & Tenancy | Organizations |
| Core Platform Domains | Configuration & Policy | Configuration |
| Core Platform Domains | Trust & Accountability | Audit, Trust |
| Cross-Cutting Platform Services | Process & Events | Workflow, Events *(Architectural Decision Pending — see below)* |
| Cross-Cutting Platform Services | Communication & Content | Notifications, Communication, Search, Files, Media |
| Cross-Cutting Platform Services | Connectivity | Integrations |
| Cross-Cutting Platform Services | Insight & Governance | Analytics, Observability, AI Governance |
| Supporting Foundations | Commercial | Payments, Billing Entitlements |
| Supporting Foundations | Platform Experience | Platform Shell, Navigation |

**Events — Architectural Decision Pending.** Whether Events becomes an
independent architecture domain in its own right, or remains part of
Workflow Architecture, is not decided in this document. That decision is
deferred until after a Workflow Architecture document is completed, at
which point there will be enough concrete detail to judge whether Events
warrants its own domain. Events is listed alongside Workflow above for
planning reference only, not as a resolution of that question.

## 5. Suggested Dependency Order

One reasonable sequencing of the groups above, offered as a planning
illustration rather than a required order:

```
Identity & Access
      ↓
Organization & Tenancy
      ↓
Configuration & Policy
      ↓
Trust & Accountability
      ↓
Process & Events
      ↓
Communication & Content
      ↓
Connectivity
      ↓
Commercial
      ↓
Platform Experience
      ↓
Insight & Governance
```

This ordering follows the intuition that recognizing who is acting
(Identity & Access) and what group they belong to (Organization &
Tenancy) are the most foundational concerns, with groups that depend on
consistent policy, trust, and process coming next, and groups that
depend on many others (Commercial, Platform Experience, Insight &
Governance) coming last. This is a suggestion for planning discussion,
not a binding sequence.

The following lightweight dependency matrix restates the same
relationships in another form, for planning discussion only. It shows
each group's most immediate planning dependency, not a full technical
dependency graph, and introduces no implementation detail:

| Domain | Depends On | Potentially Enables |
|---|---|---|
| Identity & Access | — | Nearly every other group |
| Organization & Tenancy | Identity & Access | Configuration & Policy, Commercial |
| Configuration & Policy | Identity & Access, Organization & Tenancy | Trust & Accountability, Process & Events |
| Trust & Accountability | Configuration & Policy | Process & Events, Insight & Governance |
| Process & Events | Trust & Accountability | Communication & Content, Insight & Governance |
| Communication & Content | Organization & Tenancy | Platform Experience |
| Connectivity | Identity & Access | Commercial |
| Commercial | Organization & Tenancy, Connectivity | Insight & Governance |
| Platform Experience | Communication & Content | — |
| Insight & Governance | Process & Events | — |

## 6. Candidate Future Architecture Documents

The following are logical future document topics, one per candidate
group above, offered for planning purposes only. No `XP-NNNN` identifier
is assigned to any of them, and this list does not commit to the order in
which they will be produced:

- Identity & Access — Module Architecture
- Organization & Tenancy — Module Architecture
- Configuration & Policy — Module Architecture
- Trust & Accountability — Module Architecture
- Process & Events — Module Architecture
- Communication & Content — Module Architecture
- Connectivity — Module Architecture
- Commercial — Module Architecture
- Platform Experience — Module Architecture
- Insight & Governance — Module Architecture

Per `xp-0000-documentation-governance.md`, a real `XP-NNNN` number is
assigned only when a document is actually registered in
`DOCUMENT-INDEX.md`, at the point its work is explicitly authorized —
never in advance, and never by appearing on this list.

## 7. Risks

- **Mistaking sequence for commitment.** The order in Section 5 could be
  read as a promised roadmap rather than a planning suggestion.
- **Premature design.** Naming and grouping candidate domains creates a
  temptation to start designing them here, which this document must not
  do.
- **Events/Workflow overlap.** Events and Workflow are closely related
  and could be conflated. This is flagged in Section 4 as an
  Architectural Decision Pending, deliberately deferred until after
  Workflow Architecture is completed — not decided here.
- **Drift from XP-0015.** If `XP-0015`'s Capability Map is ever revised,
  this roadmap could become stale and misleading if not updated
  alongside it.

## 8. Architectural Guardrails

- No document produced from this roadmap becomes authoritative merely by
  appearing here; each must still pass through the full documentation
  dependency process defined in `XP-0014` and the approval workflow
  defined in `XP-0002`.
- Any future Module Architecture document arising from this roadmap must
  remain consistent with, and may not contradict, `XP-0015`'s Capability
  Map and boundaries.
- This roadmap grants no authority to skip a Blueprint, CTO review, or
  Codex review step for any future document it anticipates.
- If this roadmap is found to be inconsistent with `XP-0015`, this
  roadmap is corrected — `XP-0015` is never reinterpreted to fit it.

## 9. Success Criteria

This roadmap is working if: future Module Architecture documents are
planned in an order that avoids rework caused by planning a dependent
domain before its foundation is stable; nobody mistakes a candidate
domain listed here for an already-designed capability; this document
stays a living planning aid that is updated as understanding improves,
rather than being treated as frozen; and anyone picking up future Core
Platform planning work can use this roadmap to understand what is likely
to come next without re-deriving it from `XP-0015` each time.
