# Skill: Future Expansion Review

Checks that anticipated future work is discussed without prematurely
authorizing, numbering, or designing it — the same discipline `XP-0014`
§9 and each Module Foundation document's "Future Documents Guided"
section already apply to themselves.

## Method

1. Identify whether the future item in question is already named in an
   existing roadmap (`XP-0014` §9) or "Future Documents Guided" section.
2. Confirm its prerequisite tier is `Approved` before treating it as
   ready to start (`XP-0014` §8, Documentation Dependency Order).
3. If the future item is only illustrative (e.g. `XP-0011`'s Future
   Expansion Strategy examples), keep it framed as an example of scope,
   not a commitment — restate that framing rather than dropping it.
4. Confirm no `XP-NNNN` number is assigned or reserved for it — numbers
   are assigned only at registration in `docs/DOCUMENT-INDEX.md`
   (`XP-0000`).

## Red Flags

- A roadmap or illustrative list being expanded without updating the
  document that owns that list (e.g. adding to `XP-0014` §9's five-item
  roadmap without revising `XP-0014` itself).
- A future document's content being drafted as if already authorized.
- An illustrative example being treated, later, as if it had been a
  commitment all along.

## Reference

`.claude/agents/future-planning-advisor.md` is the role built around this
same check.
