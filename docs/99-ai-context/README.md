# 99 — AI Context

**Status:** Foundation Draft

## Purpose

This folder is reserved for structured, machine-consumable context
specifically for AI coding agents (Claude Code, Codex, and any future AI
agent) working on the XETROIT Platform. Its sole job is to reduce
ambiguity so an agent picking up work here acts on exactly what is
documented, rather than inferring intent from scattered context.

This README describes *why this folder exists and what will eventually go
in it*. It intentionally does not yet contain the detailed AI context
documents themselves — those are created in a later pass, once the
governance foundation (`../00-governance/`) that defines what an AI agent
is allowed to do is itself Approved.

## Type of Documents That Will Belong Here

- **Canonical AI-agent operating instructions** — a consolidated,
  agent-facing entry point summarizing how to navigate `docs/`, what
  `Approved` means, and when implementation is permitted, distilled from
  `../00-governance/xp-0000-documentation-governance.md` and
  `../00-governance/xp-0002-approval-workflow.md`.
- **Role and authority summaries for AI agents** — a quick-reference
  restatement of the roles and approval authority matrix defined
  authoritatively in `../00-governance/xp-0001-ai-engineering-governance.md`.
- **Machine-readable or highly structured rule summaries** — condensed,
  structured extracts of platform rules that are otherwise spread across
  multiple documents, formatted for reliable parsing rather than prose
  readability.
- **Known constraints and guardrails** — e.g. Laravel-first modular
  monolith, Flutter for mobile, Node.js reserved for specialized services
  only, and the Docs-First / Approval Gate rules.
- **Explicit "never do this without human approval" lists** — a
  concentrated list of actions (e.g. marking a document Approved,
  implementing against a non-Approved document) that no AI agent may take
  unilaterally.

This folder will never be the authoritative source for any rule — it only
summarizes and links to the authoritative document in `00-governance/` or
elsewhere. If a summary here ever disagrees with the document it
summarizes, the linked document wins and this folder's content must be
corrected.

## Current Status

**Foundation Draft** — folder purpose defined; no AI context documents
authored yet. Authoring begins only after the governance documents in
`../00-governance/` (XP-0000–XP-0004) reach `Approved`, since those
documents define the rules any AI context summary here would restate.
Documents will be registered in `../DOCUMENT-INDEX.md` as they are
identified.
