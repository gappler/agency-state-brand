---
title: Claude Code guidance for agency-state-brand
description: Working instructions for Claude Code sessions operating in the canonical Agency State brand repo
version: 0.2.0
last_updated: 2026-10-11
---

This repo is the **canonical source of truth** for how Agency State presents itself. It holds approved brand truth only — no drafts, no how-tos, no actors. It feeds the Agency State brand MCP, so anything served from here must be the approved answer, never a half-formed one.

## Contents

- `brand-platform.md` — AI-facing brand intelligence: identity, what Agency State delivers, positioning, audience, voice, vocabulary, never-say, proof, boundaries. Each section is written to be served whole as one MCP tool response.
- `brand-guidelines.md` — visual identity: logo, color, typography, layout, components, motion, assets.
- `codified/` — the platform and guidelines codified into BrandBuilder's `.brand/` schema (`brand-book.md` is its assembled source; `.brand/` holds the reviewed source files, review ledger and compiled outputs). Reviewed by Greg 2026-10-27 (human_reviewed). Served over the web by the BrandBuilder MCP service. When the platform or guidelines change, re-codify and review rather than hand-editing `.brand/`.

## Editing rule

**Edits to `brand-platform.md` and `brand-guidelines.md` require explicit user approval.** When you identify a gap, surface it as a proposal — quote the current text, propose the change, and wait for confirmation. Do not edit on inferred authorization.

When a document carries version metadata (`version`, `last_updated`), preserve and update those fields rather than strip them. Bump `version` on substantive change; refresh `last_updated` on any edit.

**A canonical edit is not complete until pushed.** The MCP live-reads these files from `main` on GitHub (raw.githubusercontent.com), so a committed-but-unpushed change looks landed in every local check while every client keeps getting the old version: Claude Code at user scope, the n8n On-Brand Writer, and any client MCP on the same pattern. Push after committing, and confirm the raw URL is serving the new version (it caches about 60 seconds) before reporting the change as landed. Any report that a platform change has landed states the pushed version, not the local one.

## What does not belong here

Drafts, work-in-progress, offers/pricing/engagement-shape detail, open questions,
how-to skills, and agents. Strategic-in-flight material belongs in
`agency-state-practice`, usually under a relevant `projects/`, `plans/`, or `refs/`
folder. The moment work-in-progress creeps in, this stops being a clean source of
truth and the MCP starts serving drafts.
