# medic/cht-core context
> refreshed 2026-09-08 | upstream default: master @ 372677567640d1d3e77e6e46f168fe69a8a9e218

## Identity & policies
- upstream: medic/cht-core, default branch master, primary language JavaScript/TypeScript, English-first (yes — all docs/UI English).
- CLA/DCO: none (no CLA bot, no DCO in CONTRIBUTING).
- AI-assisted PR policy: unstated at repo level; PR template has an "AI disclosure" checkbox (docs.communityhealthtoolkit.org/community/contributing/ai-guidelines/). Policy passport: ai_disclosure_required=false. Fork PRs carry no AI mention.
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

## Mined gaps (discovered, not yet attempted)
- 2026-09-08 trivial-fix pass: hunt typos/dead links/stale commands across whole repo; bundle >=3 genuine fixes into <=10 files.
