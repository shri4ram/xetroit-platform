# XP-0021 — Communication & Content Domain Architecture

## 1. Purpose

This document defines the constitutional architecture of the
Communication & Content Domain, a domain within the Core Platform
established by `XP-0015 — Core Platform Domain Architecture`. It
elaborates the Communication & Content Foundation named in `XP-0015`'s
Capability Map — the Communication, Notification, File/media, and Search
foundations — and the Communication, Notifications, Media, and Files
capabilities already named at the Constitution tier in `XP-0011`, at the
level of constitutional architecture — principles, responsibilities, and
boundaries — without design, protocol, or implementation detail. Like
`XP-0020 — Process & Events Domain Architecture`, Communication & Content
is a cross-cutting Core Platform service domain: it governs platform-level
communication and reusable content patterns rather than establishing a
new foundational context of its own. It is subordinate to, and does not
modify, `XP-0015`, `XP-0016`, `XP-0017`, `XP-0018`, `XP-0019`, `XP-0020`,
or any other frozen document.

## 2. Why Communication & Content Exists

Every Digital Operating System needs a consistent way to reach people
with relevant information and a consistent way to represent reusable
content — messages, media, and files — wherever it appears. Without one
shared foundation for this, each Digital Operating System would build
its own notion of a message, its own notion of a template, and its own
notion of content, producing fragmented and inconsistent communication
and content handling across the platform — the same fragmentation
`XP-0016` through `XP-0020` already guard against for identity, context,
rules, accountability, and process.

Communication & Content exists to be that one, shared foundation for
platform-level communication and reusable content patterns — consistent
with Reuse Before Duplication and Platform Before Product (`XP-0005`,
`XP-0011`, `XP-0012`), with the Communication, Notifications, Media, and
Files capabilities already named in `XP-0011`, and with `XP-0015`'s
naming of the Communication & Content Foundation as a Core Platform
foundation.

## 3. Scope

Communication & Content owns the universal, platform-level concepts of:

- Communication boundary — what constitutes a governed unit of
  communication between people or organizations, in the abstract.
- Content boundary — what constitutes reusable, platform-managed
  content, in the abstract.
- Message structure — the constitutional shape of a communication
  (sender, recipient, subject matter), independent of any delivery
  channel.
- Notification concept — a communication outcome that reaches a
  recipient, distinct from the event or process that may have triggered
  it.
- Communication consistency — the platform-wide expectation that
  communication behaves consistently regardless of which Digital
  Operating System initiates it.
- Delivery boundary — the constitutional distinction between governing
  what may be communicated and how it is technically transported.
- Content reusability — the concept that content may be shared and
  referenced consistently across contexts, rather than duplicated per
  Digital Operating System.

That is the entire scope of this domain. It does not extend into
anything context-specific, business-specific, or Digital Operating
System–specific.

## 4. Out of Scope

The following are explicitly outside the Communication & Content Domain:

- **Universal identity and authentication** — these remain the Identity
  Domain (`XP-0016`); this domain does not redefine or extend Identity.
- **Organizations, tenants, and membership** — these remain the
  Organization & Tenancy Domain (`XP-0017`); this domain does not
  redefine organizational or tenant boundaries.
- **Configuration and policy definition** — these remain the
  Configuration & Policy Domain (`XP-0018`); this domain does not decide
  what communication rules apply, it only operates within them.
- **Accountability, auditability, and evidence** — these remain the
  Trust & Accountability Domain (`XP-0019`); this domain does not decide
  what remains attributable or traceable.
- **Process and event coordination** — these remain the Process & Events
  Domain (`XP-0020`); this domain does not decide what qualifies as a
  process or an event, only what communication a triggered need results
  in.
- **General content management** — a full CMS, editorial workflow, or
  publishing platform.
- **Marketing systems** — campaign management, audience segmentation for
  marketing purposes, or promotional content strategy.
- **Inbox products** — a specific messaging application or inbox
  experience.
- **File storage systems** — the technical storage, retention
  infrastructure, or file system underlying file and media handling.
- **Vertical-specific content ownership** — content whose meaning only
  exists within one Digital Operating System's domain.
- **Business meaning of messages** — the reason a message exists, or
  what it means to the domain that generated the need for it.
- **Email, SMS, push, or any other delivery provider or channel
  implementation.**
- **User interface or screen design for any communication or content
  experience.**

Each of these belongs to a different Core Platform domain, a future
domain, or an individual Digital Operating System — never to
Communication & Content.

## 5. Core Responsibilities

Communication & Content owns:

- The concept of a communication boundary and a content boundary.
- Message structure, at a constitutional level.
- The notification concept, as a communication outcome distinct from an
  event or a process.
- Communication consistency across Digital Operating Systems.
- The delivery boundary — governing what may be communicated, not how it
  is technically transported.
- Content reusability, as a platform-wide concept.

Deliberately, nothing more.

## 6. Non-Responsibilities

Communication & Content is not responsible for:

- Universal identity or authentication (`XP-0016`).
- Organizations, tenants, or membership (`XP-0017`).
- Configuration or policy definition (`XP-0018`).
- Accountability, auditability, or evidence (`XP-0019`).
- Process or event coordination (`XP-0020`).
- General content management, marketing systems, or inbox products.
- File storage infrastructure.
- Vertical-specific content whose meaning only exists within one Digital
  Operating System.
- The business meaning of a message generated by another domain.
- Any delivery provider, channel, or vendor implementation.
- Any user interface or screen design.

Communication & Content governs platform-level communication and
reusable content patterns; it does not own the business reason a message
or piece of content exists, and it must not become a general CMS,
marketing system, inbox product, file storage system, or
vertical-specific content owner for convenience.

## 7. Relationship to Foundational Domains

Communication & Content depends on all four foundational Core Platform
domains as established context. It does not bypass any of them, and it
does not redefine, extend, or duplicate any part of what they own.

- **Identity (`XP-0016`).** Identity determines who can send, receive,
  author, approve, or access a communication or piece of content.
  Communication & Content references Identity to know who is party to a
  communication; it does not decide who an identity is.
- **Organization & Tenancy (`XP-0017`).** Organization & Tenancy
  determines the tenant, organization, audience, and visibility
  boundary a communication or piece of content is scoped to.
  Communication & Content references that boundary; it does not define
  organizational or tenant boundaries.
- **Configuration & Policy (`XP-0018`).** Configuration & Policy
  determines communication rules, templates, approvals, retention
  expectations, and allowed delivery behavior. Communication & Content
  operates within those rules; it does not decide what the rules are.
- **Trust & Accountability (`XP-0019`).** Trust & Accountability
  determines what communication or content activity must remain
  auditable. Communication & Content relies on that accountability
  boundary; it does not decide what remains attributable or traceable.

The relationship runs in one direction only: Communication & Content
depends on all four foundational domains to govern communication and
content consistently; none of them depends on Communication & Content,
and none has any awareness of the communication or content activity that
may occur on top of it.

## 8. Relationship to Process & Events

`XP-0020` establishes that a process progresses through, and is marked
by, meaningful events. A process or an event may create a need for
communication — for example, a process reaching a stage that requires
reaching someone. Process & Events may trigger a communication need, but
Communication & Content governs the resulting message and content
structure, the delivery boundary, and communication consistency; it does
not decide what qualifies as a process or an event, and Process & Events
does not decide what a communication or piece of content is.

Events are not notifications: an event is a meaningful platform fact,
recognized within `XP-0020`'s boundary. A notification is a
communication outcome — governed by this domain — that may be triggered
by an event, but the two are not the same concept and one is not
automatically the other.

The relationship runs in one direction only: Communication & Content may
be triggered by a process or an event; Process & Events does not depend
on Communication & Content for its own correctness, and has no awareness
of how a resulting communication is structured or delivered.

## 9. Communication Model

Communication, as this domain defines it, is a governed exchange of
information between an identity and one or more recipients, always
attributable to an identity, scoped to an organizational or tenant
audience and visibility boundary, and subject to applicable
configuration and policy. This domain owns the constitutional structure
of a communication — that it has an author or sender, a recipient or
audience, and subject matter — independent of the channel it is
eventually delivered through.

This domain does not define what any specific communication says, who
specifically initiates it in a given business context, or what channel
carries it. It establishes only that communication, wherever it occurs
on the platform, is grounded in the same structural concept and the same
foundational domains named in Section 7, rather than each Digital
Operating System inventing its own notion of what a communication is.

## 10. Content Model

Content, as this domain defines it, is reusable, platform-managed
material — message content, media, or files — that may be authored,
approved, referenced, and governed consistently wherever it appears.
Content is not automatically public, marketing, editorial, or document
storage content; those are specific uses a Digital Operating System may
put content to, not properties inherent to the concept of content
itself. This domain owns only the constitutional boundary of what
qualifies as governed, reusable content, and the concept that content
may be referenced consistently across contexts rather than duplicated
per Digital Operating System.

This domain does not define any specific content type, storage
mechanism, file format, or editorial process. Those remain either
Digital Operating System–specific concerns or implementation concerns
deferred to a future Module Architecture or Implementation Plan
document.

## 11. Notification and Delivery Boundaries

Communication & Content owns the platform-level, reusable boundary for
what may be communicated and how communication remains consistent — the
constitutional concepts established in Sections 3, 9, and 10 — as a
foundation every Digital Operating System may build on. It does not own
the technical mechanism by which a notification is delivered. The
distinction between governing communication and delivering it is
constitutional: this domain governs message and content structure,
delivery boundaries, and communication consistency; it does not select
or design any provider, channel, or transport mechanism.

Vertical Operating Systems may define their own domain-specific
communication needs — what triggers a communication, and what it says in
that business context — on top of this foundation. What belongs here is
only the shared communication and content rules that apply regardless of
which Digital Operating System is involved. This document defines no
delivery provider, channel implementation, or storage design; those
remain deferred to a future Module Architecture or Implementation Plan
document.

## 12. Cross-Domain Coordination Rules

- Communication & Content may reference another domain's declared
  constitutional boundary — an identity, an organizational or tenant
  audience, an applicable configuration or policy, an accountability
  boundary, a triggering process or event — as context for governing a
  communication or piece of content, but it may never redefine what that
  boundary means to the domain that owns it.
- Communication & Content may recognize that a process or event created
  a communication need, without owning what that process or event
  represents.
- Coordination is scoped to what is genuinely platform-level — a
  communication or content pattern that applies regardless of which
  Digital Operating System is involved. A concern that is entirely
  internal to a single domain's own boundary does not become
  communication or content merely because it involves reaching someone
  or storing something.
- Communication & Content must not become a general CMS, marketing
  system, inbox product, file storage system, or vertical-specific
  content owner. A content or communication concern that belongs
  entirely within one Digital Operating System's boundary is not
  elevated into this domain for convenience.
- No domain depends on Communication & Content for its own internal
  correctness. Each foundational domain named in Section 7, and Process
  & Events, remains fully correct and complete on its own; Communication
  & Content adds governed communication and content on top of them, and
  is never a required intermediary for a domain to fulfill its own
  responsibility.

## 13. Risks

- **General CMS/marketing/inbox drift.** The greatest risk to this
  domain is expanding from governed platform-level communication and
  content patterns into a full content management system, marketing
  platform, or inbox product. Guardrail: Section 6 and Section 12 state
  this explicitly; any such expansion shall follow the platform's formal
  architecture governance process, never an informal addition.
- **Business-meaning absorption.** This domain could drift into owning
  why a message exists, rather than only how it is structured and
  governed. Guardrail: Section 6 states explicitly that the business
  meaning of a message belongs to the domain that generated the need for
  it, not to Communication & Content.
- **Event/notification conflation.** "Notification" risks being treated
  as synonymous with "event." Guardrail: Section 8 draws that
  distinction explicitly, and future documents must preserve it.
- **Content-property assumption.** "Content" risks being assumed to be
  automatically public, marketing, editorial, or document storage
  content. Guardrail: Section 10 states explicitly that these are uses a
  Digital Operating System may put content to, not inherent properties.
- **Storage/delivery implementation drift.** Governing content and
  communication invites the temptation to specify a storage mechanism,
  file format, or delivery provider. Guardrail: Section 11 states that
  this domain governs structure and boundaries only; provider, channel,
  and storage design are deferred to a future Module Architecture or
  Implementation Plan document.
- **Foundational bypass.** Governing communication or content without
  properly grounding it in Identity, Organization & Tenancy,
  Configuration & Policy, or Trust & Accountability would produce
  ungoverned, unaccountable communication. Guardrail: Section 7 states
  that this domain depends on all four foundational domains and must
  never bypass them.

## 14. Architecture Governance

This document is subordinate to the Platform Constitution, `XP-0014`,
`XP-0015`, `XP-0016`, `XP-0017`, `XP-0018`, `XP-0019`, and `XP-0020`.
Where anything here ever appears to conflict with any of them, that
document is correct and this one must be revised to match — never the
reverse.

Domain Minimalism applies: any future expansion of the Communication &
Content Domain's scope shall follow the platform's formal architecture
governance process, not an informal revision of this document.

This document follows the established review workflow — CTO, Founder
Review, Claude, CTO Review, Codex, CTO Review, Claude Fixes, Final CTO
Review, Governance Closeout, Freeze — and does not become authoritative
until it completes that process and is registered `Approved` in
`DOCUMENT-INDEX.md`, per `XP-0002`.
