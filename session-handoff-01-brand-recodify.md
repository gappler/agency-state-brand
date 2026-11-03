---
title: Session refresh - re-codify the Agency State brand and redeploy the MCP (AGE-110)
status: current
last_updated: 2026-11-02
---

# Session refresh - re-codify the Agency State brand and redeploy the MCP (AGE-110)

> **To resume:** open a fresh Claude Code chat in `agency-state-brand` and paste the block below.

```
Continuing brand work in /Users/gregappler/agency-state-workspace/10-active/agency-state-brand. Read this handoff first, then proceed:
/Users/gregappler/agency-state-workspace/10-active/agency-state-brand/session-handoff-01-brand-recodify.md

Goal: re-codify the Agency State brand from brand platform v3.4 and the current guidelines, have Codex (not Greg) review the changed values for fidelity to the approved platform, then compile, push, and run railway redeploy -s brand-os-mcp (AGE-110). Never record Codex's review under Greg's name; do not edit brand-platform.md or brand-guidelines.md.
```

Continuing work in `/Users/gregappler/agency-state-workspace/10-active/agency-state-brand`. Goal: the brand MCP (`agency-state-brand-os`, Railway service `brand-os-mcp`) serves the 2026-10-27 codification. It still says "AI Enablement practice," lacks the v3.3 framing and the three v3.4 voice rules, and carries the old homepage exemplar. Bring it current.

Last updated 2026-11-02 by Claude (Opus 5.5), at the end of the homepage and article relaunch session.

## Where things stand

- **Platform approved and pushed:** `brand-platform.md` v3.3 (bea5999) and v3.4 (078722e), both approved by Greg 2026-11-02. Raw GitHub URL confirmed serving v3.4. Changes: new identity (Brand OS is what Greg partners with teams to build; "AI Enablement" and "practice" retired), merged descriptor and positioning line, value lines, separate client source, brand-readiness assessment, BrandBuilder runs checks and routing, three new §5 rules (establish relevance before capability; give the result its own sentence; close with a next step the reader can take). The decision log is `agency-state-practice/projects/brand/brand-platform-decisions.md`.
- **Site launched:** agencystate.ai homepage, `brand-os.html`, and `404.html` were pushed and verified live 2026-11-02 (agency-state commit 42dad61). AGE-110 says to re-codify after launch so the codified brand captures the launched homepage as the exemplar.
- **Codified brand is stale:** `codified/brand-book.md` is v1.0 dated 2026-10-27 and begins "Agency State is Greg Appler's AI Enablement practice." The `.brand/` files compile as `human_reviewed` from Greg's 2026-10-27 review.

**Review decision (Greg, 2026-11-02):** Greg does not want to review this re-codification. Codex reviews instead. Greg already approved the content in platform v3.3/v3.4, so the review is a fidelity check: does each changed `.brand/` value match the approved platform and guidelines? Record each confirmation honestly, for example `--by "Codex (fidelity to platform v3.4; content approved by Greg 2026-11-02)"`. Never record it as Greg. Anything Codex finds that does not match the platform, or any value that needs a new judgment the platform does not settle, goes to Greg as a short list with a recommendation. Before relying on `human_reviewed`, check what the engine does with a non-person reviewer, and tell Greg in one line what status the brand ends at.

## Next steps

1. Read `docs/codify.md` and `docs/brand-codification-workflow.md` in the builder, and the prior run's README and logs, to see how `brand-book.md` was assembled and codified on 2026-10-27.
2. Regenerate `codified/brand-book.md` from `brand-platform.md` v3.4 and `brand-guidelines.md` the same way; bump its version.
3. Re-codify with the `codifying-brand` skill into `codified/.brand/source/`. Preserve Greg's 2026-10-27 human decisions in `needs-review.yaml` that are not verbatim brand-book content (imagery policy, icon policy, review-sheet section A rows 6 to 8) unless the platform now contradicts them.
4. From the builder (activate its `.venv`; `brandos` is not on the global PATH), run `brandos verify`, `brandos check`, and `brandos review status` against `codified/`.
5. Codex review: run read-only, `codex exec -s read-only --skip-git-repo-check -o <reply-file> "$(cat <prompt-file>)" < /dev/null`. Stdin must be closed or it hangs; run it in the background with a timeout. Keep prompt and reply files in the session scratchpad. Give it the changed values plus the platform text they come from.
6. Record confirmations, `brandos compile`, commit and push `agency-state-brand` (this repo pushes without asking), then `railway redeploy -s brand-os-mcp`.
7. Verify the live MCP: `get_brand_status`, `get_voice` (the three v3.4 rules are present), `get_context` (no "AI Enablement"), and `check_copy` on a homepage line.
8. Update `00-dashboard/status.md` (lines for agency-state-brand and brand-os-mcp, task-list item 3) and close AGE-110 in Linear with what shipped.

## Files to open (read these, don't re-derive)

- `brand-platform.md`, `brand-guidelines.md` (this repo): the approved source. Canonical; do not edit.
- `codified/brand-book.md`, `codified/.brand/`: what gets regenerated and re-reviewed.
- `/Users/gregappler/agency-state-workspace/60-tools-infrastructure/agency-state-brandos-builder/README.md`: commands, and how approval works ("Approval is earned, not tagged").
- `.../agency-state-brandos-builder/docs/codify.md` and `docs/brand-codification-workflow.md`: the codification steps.
- `/Users/gregappler/agency-state-workspace/10-active/agency-state-practice/projects/brand/brandbuilder/agency-state/` (README, `review-sheet.md`, `logs/`): the 2026-10-27 run and Greg's decisions.
- `/Users/gregappler/agency-state-workspace/10-active/agency-state-practice/projects/brand/brand-platform-decisions.md`: the v3.3 and v3.4 entries, with the retired "AI Enablement" term.

## Where the work lives

- **Task board:** Linear, Agency State team. AGE-110 is this task.
- **Directories in play:** `agency-state-brand/codified/` (served brand files the MCP reads); `60-tools-infrastructure/agency-state-brandos-builder/` (engine, `.venv`, `deploy/railway/start.py`); `agency-state-practice/projects/brand/brandbuilder/agency-state/` (run records for the Agency State codification).
- **Canonical sources:** brand content is `brand-platform.md` v3.4 and `brand-guidelines.md` in this repo. `codified/brand-book.md` is generated from them, never edited by hand. The served files are `codified/`, not the practice working folder (moved 2026-10-27).
- **Known non-canonical (don't use):** `agency-state-practice/projects/website/framing-draft*.md` are the homepage drafts. The live site and platform supersede them, and Greg plans to delete them.
