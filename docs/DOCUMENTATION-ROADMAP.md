# XETROIT Platform — Documentation Roadmap

**Status:** Foundation Draft
**Owner:** XETROIT Architecture Team
**Last Updated:** 2026-07-07 (v0.5)

---

## 0. What This Document Is

This is the master execution roadmap for every `docs/` folder and every
document still needed to fully specify the XETROIT Platform before
implementation begins. It organizes and sequences remaining documentation
work; it does not create architecture, rules, or approvals of its own.

- It does not define any Constitution, Architecture Map, Domain
  Architecture, Module Architecture, capability, boundary, or technology
  decision. Those exist only in `docs/00-governance/`, `docs/00-company/`,
  `docs/01-platform/`, `docs/02-core-platform/`, `docs/modules/`, and
  `docs/digital-operating-systems/`, and only this document's citations to
  them are authoritative — never a restatement here.
- It does not change any document's lifecycle status. Status changes only
  happen the way `00-governance/xp-0002-approval-workflow.md` already
  describes, recorded in `DOCUMENT-INDEX.md`.
- It does not reserve or assign any `XP-NNNN` number. Numbers are assigned
  only at the moment `xp-0000-documentation-governance.md`'s Document
  Numbering Convention describes, i.e. when a document is actually
  registered in `DOCUMENT-INDEX.md` under an authorized governance
  process — never speculatively by this roadmap.
- It does not move, rename, delete, or recreate any `XP-NNNN` document,
  and does not assert any file path as permanently authoritative beyond
  whatever `DOCUMENT-INDEX.md` and the relevant folder `README.md`
  currently state. File and folder placement is governed exclusively by
  `00-governance/xp-0003-repository-standards.md` and `DOCUMENT-INDEX.md`
  — never by this roadmap, and this roadmap does not restate their rules.
- It does not restate any review, approval, freeze, cross-reference, or
  naming rule already defined elsewhere in this repository — Section 3.5
  onward only points to the document that governs each.

If anything below conflicts with `DOCUMENT-INDEX.md`, `README.md`, or any
`XP-NNNN` document, those win and this file must be corrected.

This document is itself repository scaffolding — like `README.md` and
`DOCUMENT-INDEX.md` — and carries the same non-lifecycle `Foundation Draft`
marker defined in `xp-0000-documentation-governance.md`.

## 1. How to Read This Document

Section 2 is a folder-by-folder reference: purpose, scope, audience,
planned documents, dependencies, and status, for every folder listed in
`README.md` §7. Section 3 is the execution plan: phases, ordering,
dependency graph, and completion criteria that tie those folders together
into one sequence, followed by pointers (not restatements) to the
governance documents that already define workflow, naming, and
cross-referencing.

---

## 2. Folder-by-Folder Reference

Each entry below restates only what is already established in that
folder's own `README.md`, `DOCUMENT-INDEX.md`, and, where a folder hosts a
Digital Operating System, `XP-0030` — reorganized for planning purposes.
Where any of those disagree with this table, they win.

### 2.1 `00-company/`

- **Purpose:** Foundational identity of XETROIT as a company — the "why."
- **Scope:** Vision, mission, philosophy, values, non-technical context.
- **Audience:** Investors, Founder, all downstream document authors.
- **Planned documents:** None outstanding.
- **Dependencies:** None (root of the documentation set).
- **Status:** Completed — `XP-0009` Approved.

### 2.2 `00-governance/`

- **Purpose:** Rules for how documentation and AI-assisted engineering
  are governed.
- **Scope:** Lifecycle, numbering, approval authority, repository
  standards, ADRs, engineering principles/decision authority, AI checklist,
  writing standard.
- **Audience:** Founder, Claude Code, Codex, ChatGPT, any future AI agent.
- **Planned documents:** None outstanding — `XP-0000`–`XP-0008`, `XP-0010`
  exist, and `XP-0000`–`XP-0008` are `Approved` per `DOCUMENT-INDEX.md`.
- **Dependencies:** None (root of the documentation set, alongside
  `00-company/`).
- **Status:** Completed (all identified documents authored and `Approved`).

### 2.3 `01-platform/`

- **Purpose:** Platform-wide master plan and top-level architecture
  vocabulary tying every domain together.
- **Scope:** Executive overview, conceptual architecture, audience
  constitution, architecture map/vocabulary/dependency order.
- **Audience:** Investors, architects, all Domain Architecture authors.
- **Planned documents:** "Platform Architecture (technology-specific)" —
  remains unnumbered and explicitly deferred until an Implementation Plan
  is authorized (`DOCUMENT-INDEX.md`, `XP-0014` §10). Not to be authored
  under this roadmap.
- **Dependencies:** `00-company/`.
- **Status:** Completed for the architecture-phase scope (`XP-0011`–`XP-0014`
  Approved); the technology-specific document is Future and out of phase.

### 2.4 `02-core-platform/`

- **Purpose:** Core Platform Domain Architecture — shared foundation every
  Digital Operating System depends on.
- **Scope:** Ten Domain Architecture documents (`XP-0015`–`XP-0025`) under
  their parent `XP-0015`, organized into Core Domains, Cross-Cutting
  Services, and Supporting Foundations per its own `README.md`.
- **Audience:** Architects, Module Architecture authors, every Digital
  Operating System's own Domain Architecture author.
- **Planned documents:** None outstanding.
- **Dependencies:** `01-platform/` (`XP-0014` §8).
- **Status:** Completed — all eleven documents Approved.

### 2.5 `modules/`

- **Purpose:** Constitutional meaning of a Module — what qualifies, how
  it is classified, composed, and evolves — shared across every Digital
  Operating System.
- **Scope:** `XP-0026` (definition), `XP-0027` (classification), `XP-0028`
  (composition), `XP-0029` (lifecycle).
- **Audience:** Digital Operating System architects, future Module
  Architecture document authors.
- **Planned documents:** None outstanding at the foundation tier. Specific
  per-module Module Architecture documents are Future, gated per `XP-0014`
  §8 on their owning Digital Operating System's Domain Architecture
  reaching Approved.
- **Dependencies:** `02-core-platform/` (per `XP-0026`'s own Dependencies
  section).
- **Status:** Completed for the foundation tier (`XP-0026`–`XP-0029` exist
  and are `Approved` per `DOCUMENT-INDEX.md`); per-module documents are
  Future.
- **Note:** The `modules/` folder's `README.md` was added 2026-07-06,
  closing the gap this roadmap originally identified in Phase 1, §3.4, and
  now reflects `Approved` status.

### 2.6 `digital-operating-systems/`

- **Purpose:** Constitutional contract every Digital Operating System's
  own Domain Architecture document must follow.
- **Scope:** `XP-0030` — responsibilities, non-responsibilities, and
  relationships to Users, Core Platform, Shared Ecosystem Services,
  Infrastructure, and every other Digital Operating System. Per `XP-0030`
  §3, Business OS, Community OS, Life OS, and any Future Vertical OS are
  all instances of this one category, none privileged over another —
  Sections 2.7–2.10 below cover all four.
- **Audience:** Business OS / Community OS / Life OS / future-vertical
  Domain Architecture authors.
- **Planned documents:** None outstanding at this cross-cutting tier.
- **Dependencies:** `02-core-platform/`, `modules/` (per `XP-0030`'s own
  Dependencies section).
- **Status:** Completed for this tier (`XP-0030` exists and is `Approved`
  per `DOCUMENT-INDEX.md`).
- **Note:** This folder's `README.md` was added 2026-07-06, closing the
  gap this roadmap originally identified in Phase 1, §3.4, and now
  reflects `Approved` status.

### 2.7 `03-business-os/`

- **Purpose:** Business OS — one of the Digital Operating System instances
  named in `XP-0014` §9 and governed by the constitutional contract in
  `XP-0030`. Per `XP-0030` §3, a Digital Operating System is composed of
  one or more Modules and is never itself a Module — this folder is not a
  generic module folder.
- **Scope:** A Domain Architecture document satisfying `XP-0030`'s
  contract (responsibilities, non-responsibilities, and relationships to
  Users, Core Platform, Shared Ecosystem Services, Infrastructure, and
  other Digital Operating Systems, per `XP-0030` §4–10) for the domain of
  running a business (`XP-0030` §3). Once that Domain Architecture is
  `Approved`, the Modules within its scope are identified and bounded per
  `XP-0026` §7.
- **Audience:** Business OS Domain Architecture authors and, once that is
  Approved, its constituent Module Architecture authors.
- **Planned documents:** One Domain Architecture document ("Business OS"),
  unnumbered pending the governance sequencing this roadmap defines in
  Phase 2.
- **Dependencies:** `02-core-platform/`, `digital-operating-systems/`
  (`XP-0014` §8–9, `XP-0030`).
- **Status:** Planned.

### 2.8 `04-community-os/`

- **Purpose:** Community OS — one of the Digital Operating System
  instances named in `XP-0014` §9 and governed by the constitutional
  contract in `XP-0030`. As with every Digital Operating System, it is
  composed of Modules per `XP-0026`; it is not itself a Module or a
  generic module folder.
- **Scope:** A Domain Architecture document satisfying `XP-0030`'s
  contract for the domain of organizing a community (`XP-0030` §3). Once
  `Approved`, its Modules are identified and bounded per `XP-0026` §7.
- **Audience:** Community OS Domain Architecture authors and, once that is
  Approved, its constituent Module Architecture authors.
- **Planned documents:** One Domain Architecture document
  ("Community OS"), unnumbered.
- **Dependencies:** `02-core-platform/`, `digital-operating-systems/`.
- **Status:** Planned.

### 2.9 `05-life-os/`

- **Purpose:** Life OS — one of the Digital Operating System instances
  named in `XP-0014` §9 and governed by the constitutional contract in
  `XP-0030`. As with every Digital Operating System, it is composed of
  Modules per `XP-0026`; it is not itself a Module or a generic module
  folder.
- **Scope:** A Domain Architecture document satisfying `XP-0030`'s
  contract for the domain of managing a personal life (`XP-0030` §3). Once
  `Approved`, its Modules are identified and bounded per `XP-0026` §7.
- **Audience:** Life OS Domain Architecture authors and, once that is
  Approved, its constituent Module Architecture authors.
- **Planned documents:** One Domain Architecture document ("Life OS"),
  unnumbered.
- **Dependencies:** `02-core-platform/`, `digital-operating-systems/`.
- **Status:** Planned.

### 2.10 Future Vertical OS — Domain Architecture (Documentation Planning Only)

- **Purpose:** The fourth Digital Operating System instance named in
  `XP-0014` §9 and in `XP-0030` §3 and §15, alongside Business OS,
  Community OS, and Life OS — a shared-pattern Domain Architecture
  document for future industry-specific domains, not a design for any
  specific future vertical.
- **Scope:** Per `XP-0030` §15, exactly one shared-pattern document
  satisfying the same constitutional contract `XP-0030` establishes for
  every Digital Operating System — never one document per hypothetical
  future vertical.
- **Audience:** Future vertical-specific Domain Architecture authors, once
  any specific future vertical is actually authorized.
- **Planned documents:** One shared-pattern Domain Architecture document
  ("Future Vertical OS"), unnumbered. This roadmap plans for its
  existence only; it does not design, name, or scope any specific future
  vertical — `XP-0030` §15 explicitly reserves that for a future,
  separately authorized revision of `XP-0014`'s own roadmap.
- **Dependencies:** `02-core-platform/`, `digital-operating-systems/`
  (`XP-0014` §8–9, `XP-0030` §15).
- **Status:** Planned. **Open placement question:** no folder currently
  hosts this document. It is distinct from `16-future-verticals/`
  (speculative, non-binding exploratory concepts, §2.21) and from any
  single numbered vertical folder. Which folder it belongs in is a
  governance decision for Phase 2 (§3.1) — not decided by this roadmap.

### 2.11 `06-marketplace/`

- **Purpose:** Marketplace module (buying, selling, listing, exchange).
- **Scope:** Per its `README.md`. Payment processing excluded (belongs to
  `07-payments/`).
- **Audience:** Marketplace feature authors.
- **Planned documents:** One document ("Marketplace"), unnumbered. Its
  tier (Domain Architecture vs. Module Architecture) depends on which
  Digital Operating System, if any, it is classified under per
  `XP-0027` — a classification question for Phase 2, not decided here.
- **Dependencies:** `02-core-platform/`; likely one or more of
  `03-business-os/`/`04-community-os/`/`05-life-os/` depending on
  classification.
- **Status:** Planned.

### 2.12 `07-payments/`

- **Purpose:** Payments architecture shared across all modules requiring
  payment functionality.
- **Scope:** Per its `README.md` — processing, settlement, compliance,
  ledger, fees, refunds, payouts, disputes.
- **Audience:** Any module handling money movement (Marketplace, Business
  OS, etc.).
- **Planned documents:** One document ("Payments"), unnumbered. Likely
  classifies as a Shared Ecosystem Service per the canonical hierarchy
  (`XP-0014` §5) — `XP-0014` §9 leaves this classification open; Phase 2
  resolves it before authoring, not this roadmap.
- **Dependencies:** `02-core-platform/`.
- **Status:** Planned.

### 2.13 `08-ai/`

- **Purpose:** AI Platform — how AI capability is architected, governed,
  and integrated across XETROIT.
- **Scope:** Per its `README.md` — AI platform architecture, AI feature
  specs, AI-agent consumption guidelines, data/privacy/safety, business
  rules. Distinct from `99-ai-context/`, which is agent operating context,
  not AI-as-product architecture.
- **Audience:** AI feature authors, developers integrating AI capability.
- **Planned documents:** One document ("AI Platform"), unnumbered.
- **Dependencies:** `02-core-platform/`.
- **Status:** Planned.

### 2.14 `09-mobile/`

- **Purpose:** Mobile architecture for XETROIT applications (Flutter).
- **Scope:** Per its `README.md` — app architecture, Flutter conventions,
  backend integration contracts, mobile-specific security/offline/
  performance, release process.
- **Audience:** Mobile engineers, AI agents generating Flutter code.
- **Planned documents:** One document ("Mobile Architecture"), unnumbered.
- **Dependencies:** `02-core-platform/`, `13-api/`.
- **Status:** Planned.

### 2.15 `10-devops/`

- **Purpose:** Infrastructure, deployment, operational practices.
- **Scope:** Per its `README.md` — hosting, environments, networking,
  CI/CD, monitoring, incident response, backup/DR/scaling.
- **Audience:** Engineers, operators.
- **Planned documents:** None currently identified; registered as needed
  per `README.md`.
- **Dependencies:** `02-core-platform/`.
- **Status:** Future.

### 2.16 `11-security/`

- **Purpose:** Security architecture and policy, platform-wide.
- **Scope:** Per its `README.md` — auth, encryption, data protection,
  threat modeling, vulnerability management, compliance.
- **Audience:** All engineers and AI agents generating code.
- **Planned documents:** None currently identified; registered as needed.
- **Dependencies:** `02-core-platform/` (notably Identity, Trust &
  Accountability).
- **Status:** Future.

### 2.17 `12-ui-ux/`

- **Purpose:** Shared design system and UX standards (web + Flutter).
- **Scope:** Per its `README.md` — design foundations, UX principles,
  accessibility, cross-platform consistency, component library docs.
- **Audience:** Frontend/mobile engineers, AI agents generating UI code.
- **Planned documents:** None currently identified; registered as needed.
- **Dependencies:** `02-core-platform/` (Platform Experience), `09-mobile/`.
- **Status:** Future.

### 2.18 `13-api/`

- **Purpose:** API contracts and standards.
- **Scope:** Per its `README.md` — design standards, auth contracts,
  endpoint documentation, rate limiting/pagination/response conventions.
- **Audience:** Backend, mobile, and future external integration
  consumers.
- **Planned documents:** None currently identified; registered as needed.
- **Dependencies:** `02-core-platform/`.
- **Status:** Future.

### 2.19 `14-database/`

- **Purpose:** Data architecture and schema standards.
- **Scope:** Per its `README.md` — technology rationale, schema
  conventions, data ownership boundaries, retention/privacy, multi-tenancy
  isolation.
- **Audience:** Backend engineers, AI agents generating migrations/models.
- **Planned documents:** None currently identified; registered as needed.
- **Dependencies:** `02-core-platform/` (notably Organization & Tenancy).
- **Status:** Future.

### 2.20 `15-development/`

- **Purpose:** Engineering standards and workflow practices.
- **Scope:** Per its `README.md` — coding standards, git workflow,
  testing standards, local environment setup, Definition of Done.
- **Audience:** Developers and AI coding agents.
- **Planned documents:** None currently identified; registered as needed.
- **Dependencies:** `00-governance/`.
- **Status:** Future.

### 2.21 `16-future-verticals/`

- **Purpose:** Exploratory documentation for uncommitted future product
  lines.
- **Scope:** Per its `README.md` — speculative concepts, market notes,
  non-binding sketches. Never reaches `Approved` while speculative.
  Distinct from §2.10's Future Vertical OS Domain Architecture, which is a
  committed roadmap item (`XP-0014` §9), not a speculative concept.
- **Audience:** Founder, architects evaluating expansion.
- **Planned documents:** None currently identified; opportunistic.
- **Dependencies:** `01-platform/` (Constitution, for fit-checking).
- **Status:** Future.

### 2.22 `99-ai-context/`

- **Purpose:** Structured, machine-consumable operating context for AI
  coding agents.
- **Scope:** Per its `README.md` — consolidated agent operating
  instructions, role/authority summaries, condensed rule extracts,
  constraints/guardrails, "never do this" lists. Never authoritative on
  its own; only summarizes `00-governance/` and elsewhere.
- **Audience:** Claude Code, Codex, any future AI coding agent.
- **Planned documents:** Per its own `README.md`, authoring begins only
  after `XP-0000`–`XP-0004` reach `Approved`.
- **Dependencies:** `00-governance/` (all of `XP-0000`–`XP-0004`, Approved).
- **Status:** Future — explicitly blocked on a governance precondition,
  not on documentation-planning sequence.

### 2.23 `archive/`

- **Purpose:** Historical/reference retention for documents that are
  superseded or were exploratory drafts, per `README.md` §7 ("Superseded
  or exploratory documents kept for history").
- **Scope:** Non-authoritative, retained-for-audit content only —
  currently `architecture-exploration/xp-0015a-core-platform-interaction-model.md`,
  an early interaction-model draft superseded before the Core Platform
  Domain Architecture phase completed (per `DOCUMENT-INDEX.md`'s "Core
  Platform Domain Architecture Complete" note). This roadmap does not
  restate or summarize that document's content — its existence and
  superseded status are noted here only to place the folder in context.
- **Audience:** Anyone auditing how the architecture reached its current
  state; never consulted as a source for current specification.
- **Planned documents:** None. This folder is never a target for newly
  authored content — a document arrives here only when a live document
  elsewhere is retired to it under the `Deprecated`/`Archived` statuses
  already defined in `xp-0000-documentation-governance.md`, never the
  reverse.
- **Dependencies:** None. An archive folder is, by definition, cited
  authoritatively by nothing and cites nothing; each item it holds
  depends only on whatever document superseded it, for context.
- **Status:** Completed — the folder itself needs no further planning or
  authoring. It grows only as a side effect of `Deprecated`/`Archived`
  transitions in other folders (see §3.1), never through an execution
  phase of its own.

---

## 3. Documentation Execution Plan

### 3.1 Documentation Phases

| Phase | Name | Contents | Gate to Enter |
|---|---|---|---|
| 0 | Foundation | `00-company/`, `00-governance/`, `01-platform/`, `02-core-platform/`, `modules/`, `digital-operating-systems/` | None — already underway |
| 1 | Foundation Closeout | Advance `00-governance/` (`XP-0000`–`XP-0008`) and `modules/`, `digital-operating-systems/` (`XP-0026`–`XP-0030`) from `Draft` to `Approved` (**complete**, 2026-07-07); add the two missing folder READMEs (§3.4, complete) | Phase 0 documents drafted (already true) — **gate satisfied** |
| 2 | Digital Operating Systems | `03-business-os/`, `04-community-os/`, `05-life-os/` Domain Architecture documents; the Future Vertical OS shared-pattern Domain Architecture (§2.10 — folder not yet assigned) | Phase 1's `digital-operating-systems/` and `modules/` documents `Approved` (`XP-0014` §8, `XP-0030` Dependencies) |
| 3 | Shared Ecosystem Capabilities | `06-marketplace/`, `07-payments/`, `08-ai/` — classified per `XP-0027` before authoring | Relevant Phase 2 Domain Architecture(s) `Approved`, or classified as Shared Ecosystem Service against `02-core-platform/` directly |
| 4 | Client & Platform Standards | `09-mobile/`, `12-ui-ux/`, `13-api/` | Phase 2/3 domains it serves are `Approved` enough to have stable contracts to document against |
| 5 | Operational Standards | `10-devops/`, `11-security/`, `14-database/`, `15-development/` | Can proceed in parallel with Phase 3–4 once `02-core-platform/` is `Approved`; not blocked on Digital Operating System content |
| 6 | AI Agent Context | `99-ai-context/` | `00-governance/` `XP-0000`–`XP-0004` `Approved` (its own `README.md` precondition) |
| Ongoing | Exploratory | `16-future-verticals/` | None — opportunistic, never blocks or is blocked by other phases |
| Ongoing | Historical / Reference | `archive/` | None — receives content only as a side effect of a `Deprecated`/`Archived` transition elsewhere (`XP-0000`); never itself a target for new authoring or phase-gated work |

### 3.2 Execution Order

Within each phase, order follows `XP-0014` §8 (Documentation Dependency
Order) and §9 (Future Architecture Document Roadmap):

1. Complete Phase 1 (Foundation Closeout) before authoring any new Domain
   Architecture content — the Approval Gate (`XP-0002`) blocks it
   otherwise.
2. Author the Digital Operating System Domain Architecture documents
   (Phase 2) — the three named instances and the Future Vertical OS
   shared pattern — in any order relative to each other; `XP-0014` §9
   states no required order among the roadmap items beyond the dependency
   chain itself.
3. For each Shared Ecosystem candidate in Phase 3, first resolve its
   classification per `XP-0027` (Module vs. Capability vs. Shared
   Ecosystem Service vs. Core Platform responsibility) before choosing
   which folder's Domain/Module Architecture tier it is written at.
4. Phase 4 and Phase 5 folders may proceed in parallel with each other and
   with later Phase 3 items, since neither depends on the other per
   Section 3.3's graph.
5. Phase 6 (`99-ai-context/`) starts only when its named governance
   precondition is met, independent of every other phase's progress.

### 3.3 Folder Dependencies

```
00-company/  ─┐
00-governance/ ┴─→ 01-platform/ ─→ 02-core-platform/ ─┬─→ modules/ ─→ digital-operating-systems/
                                                        │                        │
                                                        │   ┌────────────┬───────┼───────┬────────────────────┐
                                                        │   ▼            ▼       ▼       ▼                    │
                                                        │  03-business-os/ 04-community-os/ 05-life-os/  Future Vertical OS
                                                        │   │            │       │       (folder TBD, §2.10)
                                                        │   └────────────┴───────┴───────┬──────────────────┘
                                                        │                                ▼
                                                        ├─→ 06-marketplace/ ── 07-payments/   08-ai/
                                                        │
                                                        ├─→ 09-mobile/ ←── 13-api/
                                                        ├─→ 12-ui-ux/  ←── 09-mobile/
                                                        ├─→ 10-devops/
                                                        ├─→ 11-security/
                                                        ├─→ 14-database/
                                                        └─→ 15-development/ ←── 00-governance/

00-governance/ (XP-0000–XP-0004 Approved) ─→ 99-ai-context/
01-platform/ (Constitution) ─→ 16-future-verticals/ (opportunistic, non-blocking)
```

This graph reflects each folder's own stated Dependencies (Section 2); it
does not introduce a dependency any folder's `README.md` does not already
state.

### 3.4 Immediate Next Actions (Phase 1 Scope Only)

Two gaps originally identified inside already-authored folders, while
compiling Section 2, have since closed:

- The `modules/` folder's `README.md` was added 2026-07-06, describing
  the folder consistent with `XP-0026`–`XP-0029`.
- The `digital-operating-systems/` folder's `README.md` was added
  2026-07-06, consistent with `XP-0030`.

Both were documentation-hygiene actions (adding a folder README to match
an existing pattern), not architecture decisions, and both fell under the
Docs-First / Minimal-Edit rules already in force — they extended, not
replaced, anything.

The remaining Phase 1 item — advancing `00-governance/`
(`XP-0000`–`XP-0008`) and `modules/`, `digital-operating-systems/`
(`XP-0026`–`XP-0030`) to `Approved` — is complete: per Founder decision
(2026-07-07), all fourteen documents are now `Approved` per
`DOCUMENT-INDEX.md`. Phase 1 is closed and Phase 2's gate (§3.1) is
satisfied. This closeout does not constitute a Freeze for any of the
fourteen documents — Freeze remains a separate, not-yet-performed step.

### 3.5 Review Workflow

Refer to the official governance documents: `.claude/context/review-workflow.md`,
`.claude/workflows/review-cycle.md`, and `XP-0001`. This roadmap defines
no review workflow of its own and restates none of theirs.

### 3.6 Approval Workflow

Refer to the official governance document:
`00-governance/xp-0002-approval-workflow.md`. This roadmap defines no
approval workflow of its own and restates none of it.

### 3.7 Freeze Process

Refer to the official governance document:
`.claude/workflows/freeze-process.md`. This roadmap defines no freeze
process of its own and restates none of it.

### 3.8 Cross-Reference Rules

Refer to the official governance documents:
`00-governance/xp-0010-documentation-writing-standard.md` and
`DOCUMENT-INDEX.md`'s "Adding a New Document" section. This roadmap
defines no cross-reference rule of its own and restates none of theirs.

### 3.9 Naming Standards

Refer to the official governance document:
`00-governance/xp-0003-repository-standards.md`. This roadmap defines no
naming convention of its own and restates none of it.

### 3.10 Definition of Complete

A folder in Section 2 is **Completed** when:

1. Every document its own `README.md` identifies as belonging there
   exists and is registered in `DOCUMENT-INDEX.md`.
2. Every such document has reached at least the lifecycle status its
   governing process requires for its purpose (e.g. a Domain Architecture
   document intended to gate downstream work must be `Approved`, per the
   Approval Gate in `XP-0002`).
3. The folder's `README.md` "Current Status" section accurately reflects
   1 and 2.

A folder is **Planned** when its document(s) are identified and registered
but not yet `Approved`; **Future** when no document is yet identified but
the folder's purpose is already defined; and **Ongoing/Exploratory**
(`16-future-verticals/` only) when it is never expected to reach
Completed by design. These are roadmap-only planning categories for
tracking folders, distinct from the document-level lifecycle statuses
(`Planned`/`Draft`/`In Review`/`Approved`/`Deprecated`/`Archived`) defined
in `xp-0000-documentation-governance.md` and used in `DOCUMENT-INDEX.md`.

### 3.11 Overall Documentation Progress

| Phase | Folders | Status |
|---|---|---|
| 0 — Foundation | `00-company/`, `00-governance/`, `01-platform/`, `02-core-platform/`, `modules/`, `digital-operating-systems/` | Documents authored; both folder READMEs added (§3.4, complete); `00-governance/` and the `modules/`/`digital-operating-systems/` series are `Approved` |
| 1 — Foundation Closeout | (same folders, README + lifecycle gaps) | **Complete** (2026-07-07) — folder READMEs complete; all fourteen documents `Approved`; Freeze not yet performed (separate step) |
| 2 — Digital Operating Systems | `03-business-os/`, `04-community-os/`, `05-life-os/`, Future Vertical OS (folder TBD, §2.10) | Planned |
| 3 — Shared Ecosystem Capabilities | `06-marketplace/`, `07-payments/`, `08-ai/` | Planned |
| 4 — Client & Platform Standards | `09-mobile/`, `12-ui-ux/`, `13-api/` | Future |
| 5 — Operational Standards | `10-devops/`, `11-security/`, `14-database/`, `15-development/` | Future |
| 6 — AI Agent Context | `99-ai-context/` | Future (blocked on named governance precondition) |
| Ongoing | `16-future-verticals/` | Opportunistic |
| Ongoing | `archive/` | Completed (historical/reference only; no execution phase of its own) |

This table is a planning snapshot, not a lifecycle record — `DOCUMENT-INDEX.md`
remains the sole authoritative source for any individual document's status.

---

## 4. Revision History

| Version | Date | Author | Summary |
|---|---|---|---|
| 0.1 | 2026-07-05 | Claude Code | Initial documentation roadmap: folder-by-folder reference and execution plan covering every `docs/` area, per Founder request to organize remaining documentation work without inventing architecture. |
| 0.2 | 2026-07-05 | Claude Code | Applied Codex governance findings: added an explicit no-relocation/no-restatement caveat (§0); added the Future Vertical OS shared-pattern Domain Architecture as a planning-only entry (§2.10) per `XP-0014` §9 and `XP-0030` §3/§15; realigned Business OS, Community OS, and Life OS entries (§2.7–2.9) with `XP-0030`'s Digital Operating System contract, removing wording that implied they were generic module folders; replaced the restated Review Workflow, Approval Workflow, Freeze Process, Cross-Reference Rules, and Naming Standards sections (§3.5–3.9) with references to their single authoritative source each; corrected the `modules/README.md` note to reflect that the file does not exist rather than exists-but-empty. No `XP-NNNN` document, `README.md`, or `DOCUMENT-INDEX.md` was touched by this revision. |
| 0.3 | 2026-07-05 | Claude Code | Added the missing `archive/` folder entry (§2.23), listed in `README.md` §7 but previously uncovered — Purpose, Scope, Audience, Planned Documents, Dependencies, and Status, treated strictly as historical/reference with no execution phase of its own; added corresponding rows to the Documentation Phases (§3.1) and Overall Documentation Progress (§3.11) tables. Does not restate or summarize any archived document's content, and does not touch any `XP-NNNN` document or `README.md`. |
| 0.4 | 2026-07-07 | Claude Code | Synchronization only, per a repository audit that found this roadmap out of date relative to `DOCUMENT-INDEX.md`: updated §2.2, §2.5, §2.6, §3.1, §3.4, and §3.11 to reflect that (a) the `modules/` and `digital-operating-systems/` folder READMEs identified as missing in v0.3 were added 2026-07-06, and (b) `XP-0000`–`XP-0008` and `XP-0026`–`XP-0030` advanced from `Draft` to `In Review` in `DOCUMENT-INDEX.md` on 2026-07-07. Phase 1's approval gate is unchanged — `Approved` remains the required end-state for all fourteen documents, and Phase 1 is recorded as still open ("In progress," not "Not started" or "Completed"). No roadmap sequencing, phase gate, dependency, or scope was altered; no `XP-NNNN` document, `DOCUMENT-INDEX.md`, or architecture content was touched by this revision. |
| 0.5 | 2026-07-07 | Claude Code | Synchronization only, following the Founder's approval of all fourteen Phase 1 documents: updated §2.2, §2.5, §2.6, §3.1, §3.4, and §3.11 to record Phase 1 ("Foundation Closeout") as **complete** and its gate as satisfied, matching `DOCUMENT-INDEX.md`'s `Approved` status for `XP-0000`–`XP-0008` and `XP-0026`–`XP-0030`. Explicitly notes Freeze has not been performed for any of the fourteen and remains a separate step. No roadmap sequencing, dependency graph, or scope was altered; this revision only reflects a status this roadmap already gated on, now met. |
