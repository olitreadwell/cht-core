# medic/cht-core context
> refreshed 2026-10-07 | upstream default: master @ f71f188e3e5c21b5f0996b346c9a18158009ae62

## Identity & policies
- upstream: medic/cht-core, default branch master, primary language JavaScript/TypeScript, English-first (yes — all docs/UI English).
- CLA/DCO: none (no CLA bot, no DCO in CONTRIBUTING).
- AI-assisted PR policy: no repo-level CONTRIBUTING AI text, but `.github/PULL_REQUEST_TEMPLATE.md` (live master) carries an "AI disclosure" checklist item ("Please disclose use of AI" -> docs.communityhealthtoolkit.org/community/contributing/ai-guidelines/). Per config `ai_policy_check.rules.ai_disclosure_required` + `preflight_scan.critical_filters_hard_skip`, a PR-template checkbox means `ai_disclosure_required=true` -> HARD SKIP (outcome `skip-requires-ai-disclosure`). Passport CORRECTED 2026-10-04 to `pr_template_present=true, ai_disclosure_required=true`; engine/policy-worker.sh patched the same day to detect `.github/PULL_REQUEST_TEMPLATE.md` and to scan PR-template text for AI disclosure, so a future sweep cannot regress it (detector gap originally flagged 2026-09-24).
- signed commits required: no (policy passport signed_commits_required=false).
- PR template: .github/PULL_REQUEST_TEMPLATE.md (semantic title `<type>(#issue): subject`; fill verbatim).
- external tracker: github.

## Conventions (verified from merged PRs)
- branch naming: `<issue>-<kebab-description>` (e.g. 11359-dont-assert-revs-when-unordered, 11338-improve-utils-start-service) or `<issue>_<desc>`; dependabot uses its own. No issue -> use descriptive `fix-<kebab>`.
- commit style: Conventional Commits `type(#issue): subject` (fix/feat/chore/test/ci). No issue -> `type: subject`.
- test command: per-package mocha (webapp/api/sentinel); lint: eslint. CI: GitHub Actions "Build and test".
- outside PRs merge: responsive; many external contributors (megha1807, jkuester, witash, bc004346) merged Jul-Aug 2026.

## Maintainer picture
- active maintainers: medic core team; responsive to small PRs.

## Issue-area health
- Large monorepo (webapp/api/sentinel/shared-libs). Trivial-fix pass targets typos/dead links/stale commands in docs + comments.

## Gap ledger (dedupe — READ FIRST, never re-pick)
- 2026-08-24 dropped — no small verifiable pick (GFIs assigned/in-flight).
- 2026-08-25 issue #11051 — pr-opened (fork PR #1, authorization.js getUserSettings error swallow).
- 2026-08-25 issue #6495 — pr-opened (fork PR #2, sentinel TZ-independent tests).
- 2026-09-09 trivial-fix pass — pr-opened (fork PR #17, bundled 10 meaning-preserving typo fixes across 10 files docs/comments/test-desc). Parallel worker opened PR #18 (8 fixes/6 files) with 6-file overlap; consolidated: added PR #18 unique README fix to PR #17, closed PR #18. Lesson: bundled docs-typo PRs work well here; dedupe overlapping parallel trivial-fix PRs into one.

- 2026-09-24 trivial-fix pass — pr-opened (fork PR #29, bundled 18 typos across 10 files: comments, jsdoc, error strings, test descriptions). No overlap with PR #17/#18 files.
- 2026-10-01 trivial-fix pass — pr-opened (fork PR #32, bundled 11 typos across 10 files: comments, jsdoc, package.json description, docs, test descriptions). No overlap with PR #17/#18/#29 files. Upstream master advanced 8eb5bb3c -> 3572c9bb since the 2026-09-24 refresh; header re-verified live at 3572c9bb.
- 2026-10-02 issue #11449 — pr-opened (fork PR #33, `shared-libs/cht-datasource` `fetchAndFilter` set the page cursor with a document count while `skip` counts rows, so accepted docs were dropped and `cursor: null` was returned early; now consumes only the rows needed to fill the page and derives the cursor from rows consumed, with a unit regression test). Self-found/maintainer-filed bug, unassigned, no in-flight PR. Lesson: the datasource paging cursor is a tested invariant; keep row-vs-doc accounting explicit.
- 2026-10-03 trivial-fix pass — SKIPPED, no PR (`skip-requires-ai-disclosure`): verified live on master that `.github/PULL_REQUEST_TEMPLATE.md` has an "AI disclosure" checklist item; config treats a PR-template checkbox as `ai_disclosure_required` -> hard skip before any coding. No typo hunt run. Lesson: loop-trivial re-picks this repo on the stale passport (`ai_disclosure_required=false`); correct the passport (or fix policy-worker.sh to scan the PR template) so it stops re-picking.
- 2026-10-04 trivial-fix pass — SKIPPED, no PR (`skip-requires-ai-disclosure`): upstream master unchanged at f71f188e; the PR-template AI-disclosure gate still applies (re-verified live). Root cause of the recurring re-pick fixed in the pipeline repo: passport corrected + engine/policy-worker.sh now scans `.github/PULL_REQUEST_TEMPLATE.md` for AI disclosure. Loop should no longer pick this repo for trivial PRs (substantive non-AI-disclosable work is also barred by the same gate until Oli reconciles the policy).
- 2026-10-05 trivial-fix pass — SKIPPED, no PR (`skip-requires-ai-disclosure`): upstream master unchanged at f71f188e; the PR-template AI-disclosure gate was re-verified LIVE (`.github/PULL_REQUEST_TEMPLATE.md` still carries the "AI disclosure: Please disclose use of AI" checklist item) -> `ai_disclosure_required=true` -> HARD SKIP before any coding. Passport already corrected 2026-10-04 and engine/loop-trivial.sh `hard_blocked()` skips this repo, so no typo/link/stale-command hunt was run. Lesson: the trivial loop must not re-pick this repo; if it appears again the pick was forced rather than queue-selected.
- 2026-10-06 trivial-fix pass — SKIPPED, no PR (`skip-requires-ai-disclosure`): upstream master re-verified LIVE unchanged at f71f188e; `.github/PULL_REQUEST_TEMPLATE.md` still carries the "AI disclosure: Please disclose use of AI per the guidelines" checklist item -> `ai_disclosure_required=true` -> HARD SKIP before any coding (config `ai_policy_check.rules.ai_disclosure_required`, `engine/loop-trivial.sh` `hard_blocked()` line 192). 4th consecutive skip; this pick was forced/manual, not queue-selected. No typo/link/stale-command hunt run. Lesson: medic/cht-core stays ineligible for AI-disclosure-free fork PRs until Oli reconciles the PR-template disclosure item (or explicitly authorises disclosure on the fork PR body, which config forbids).

- 2026-10-07 trivial-fix pass — SKIPPED, no PR (`skip-requires-ai-disclosure`): upstream master re-verified LIVE unchanged at f71f188e3e5c21b5f0996b346c9a18158009ae62 (fork master identical); `.github/PULL_REQUEST_TEMPLATE.md` still carries the "AI disclosure: Please disclose use of AI per the guidelines" checklist item -> `ai_disclosure_required=true` -> HARD SKIP before any coding (config `ai_policy_check.rules.ai_disclosure_required`, `engine/loop-trivial.sh` `hard_blocked()`). 5th consecutive skip; pick was forced/manual, not queue-selected. No typo/link/stale-command hunt run. Lesson: medic/cht-core stays ineligible for AI-disclosure-free fork PRs until Oli reconciles the PR-template disclosure item.

## Mined gaps (discovered, not yet attempted)
- 2026-09-08 trivial-fix pass: hunt typos/dead links/stale commands across whole repo; bundle >=3 genuine fixes into <=10 files.
