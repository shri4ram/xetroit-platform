# Template: Governance Checklist

> Reusable readiness check before moving a document through its
> lifecycle (`docs/00-governance/xp-0000-documentation-governance.md`,
> `xp-0002-approval-workflow.md`). Mirrors the Approval Checklist already
> required by `docs/DOCUMENT-TEMPLATE.md` and the Definition of Done in
> `xp-0010-documentation-writing-standard.md` §17 — use this to check
> readiness before proposing the transition, not as a replacement for
> either.

# Governance Checklist: [Document]

## Before `Draft → In Review`

- [ ] Every required section present, or explicitly `N/A` with a reason
- [ ] Every cross-reference resolves to a real document/section
- [ ] Open Questions list is current
- [ ] Language follows the writing standard (rule-strength words, no
      marketing language, ISO dates)
- [ ] `Version` and `Last Updated` are in sync with actual edits

## Before `In Review → Approved`

- [ ] All Codex findings resolved (fixed, or explicitly deferred with
      written Founder reasoning)
- [ ] No open blocking questions remain
- [ ] Document does not contradict any `Approved` document it depends on
- [ ] `docs/DOCUMENT-INDEX.md` row matches the document's own metadata
- [ ] Approval Checklist (in the document itself) fully satisfied

## Before Freeze (Approved documents only)

- [ ] Founder has actually set status to `Approved` — not assumed
- [ ] Revision History / Architecture Governance section reflects the
      approved content accurately
- [ ] No further content change is bundled into the freeze step
