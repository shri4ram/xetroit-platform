# Workflow: Freeze Process

What happens after a document reaches `Approved`, and what the further
**Frozen** marker means for a document that carries it. This workflow
describes the mechanism only — which specific documents currently hold
either status is not tracked here. Check `docs/DOCUMENT-INDEX.md`
directly, every time, for current lifecycle status.

## Preconditions

Freeze only ever follows `Approved` — it is never a way to reach
`Approved`. Before starting:

- The Founder has set the document's status to `Approved`, in both its
  own metadata and `docs/DOCUMENT-INDEX.md` (`XP-0002` step 6).
- Every Codex finding against it is resolved — fixed, or explicitly
  deferred with written Founder reasoning.
- Its Approval Checklist (or, for the Domain Architecture pattern, its
  Architecture Governance section) is fully satisfied.

## Steps

1. **Confirm approval is real**, not assumed — check the current
   `docs/DOCUMENT-INDEX.md`, not memory of an earlier session
   (`.claude/agents/governance-auditor.md`).
2. **Add a closing governance-closeout entry** — a Revision History row,
   or an Architecture Governance note for the Domain Architecture
   pattern — recording the freeze date and the review chain it
   completed (`.claude/workflows/review-cycle.md`).
3. **Mark the document Frozen**, if `docs/DOCUMENT-INDEX.md` or the
   document itself calls for that additional marker, alongside (never
   instead of) `Approved`.
4. **Leave substantive content untouched** at this step — Freeze closes
   out bookkeeping; it is not an opportunity for a last content edit.

## After Freeze

- Approved-and-Frozen documents are not edited casually
  (`docs/00-governance/xp-0007-repository-constitution.md` §8, Change
  Management Philosophy). Any future change requires a new revision, a
  fresh review cycle, and re-approval — never a silent edit to unblock
  unrelated work.
- New, subordinate work cites a Frozen document; it never restates,
  duplicates, or reinterprets it (`.claude/CLAUDE.md` §3, §7).

## Related

- `.claude/commands/freeze.md` — the operational command for this step.
- `docs/DOCUMENT-INDEX.md` — the only place to check which specific
  documents are currently `Approved` or `Frozen`.
