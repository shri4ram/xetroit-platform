# Template: Domain Architecture Document

> Skeleton for the Domain Architecture pattern
> (`docs/00-governance/xp-0010-documentation-writing-standard.md` §3),
> used by `XP-0015` onward and by cross-cutting foundations like the
> Module Foundation (`XP-0026`–`XP-0029`). No Document Metadata table and
> no Revision History unless the specific document's own governing
> instructions explicitly require one — status and lifecycle are tracked
> in `docs/DOCUMENT-INDEX.md` instead. Section names below are a starting
> point, not a fixed requirement — rename to fit the domain, but keep the
> opening-with-Purpose / closing-with-Architecture-Governance shape.

# XP-NNNN — [Domain / Foundation Name]

## 1. Purpose

Why this document exists, what it elaborates, and what it is explicitly
subordinate to (name every frozen document it depends on).

## 2. Why This [Domain / Layer] Exists

The problem this document solves once, and the fragmentation it
prevents if it did not exist.

## 3. Definition

What this domain/layer/concept is, stated precisely enough to be
testable.

## 4. Responsibilities

What this domain/layer owns.

## 5. Non-Responsibilities

What this domain/layer must never own — named explicitly, not implied.

## 6+. Relationships to Neighboring Layers/Domains

One section per relationship (e.g. Relationship to the Core Platform,
Relationship to Shared Ecosystem Services) — state direction of
dependency explicitly; note where the relationship runs one way only.

## N. Risks

Named failure modes this document is written to prevent, each paired
with the section that guards against it.

## N+1. Architecture Governance

Subordination statement (which frozen documents win in a conflict), a
note that Domain/Document Minimalism applies, and the review workflow
this document must complete before it is authoritative
(`.claude/context/review-workflow.md`).
