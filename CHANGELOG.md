# Changelog

All notable changes to the `.github` org defaults repository are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### Removed
- `.github/workflows/reusable-lint.yml`, `reusable-test.yml`, `reusable-security.yml`, `reusable-render-diagrams.yml` — reusable CI/CD workflows briefly published from this repo (introduced in unreleased state via PRs #17 and #22). Per the architecture decision making this repo public-defaults-only, they relocated to private `baena-labs/org-config/.github/workflows/`. No org-internal callers existed at the time of removal (verified via `gh search code` across `baena-labs`).
- `.github/dependabot.yml` — tracked actions used in the now-removed workflows; nothing else here uses third-party actions.
- `.github/copilot-instructions.md` — referenced internal Claude Code tooling (`.claude/`, hooks, agents) and so did not fit the public-minimal posture.

### Changed
- `README.md` rewritten to state the public-minimal posture explicitly and point readers at `baena-labs/org-config` for internal CI/CD, rulesets, governance, repo onboarding, and label taxonomy.
- `AGENTS.md` "Required Coordination" updated to record that reusable workflows / label taxonomies / rulesets / CI/CD standards belong in `org-config`, not here.

---

## [0.1.2] — 2026-04-22

### Added
- `copilot-instructions.md` — org-wide Copilot instructions with Claude Code awareness, review focus areas, and skip rules
- `profile/README.md` — added `ai-template` to the Repositories section

---

## [0.1.1] — 2026-04-22

### Fixed
- Removed duplicate root-level `ISSUE_TEMPLATE/*.md` files (redundant with `.github/ISSUE_TEMPLATE/*.yml`)
- Removed duplicate `.github/PULL_REQUEST_TEMPLATE.md` (superseded by root `PULL_REQUEST_TEMPLATE.md`)

---

## [0.1.0] — 2026-03-31

### Added
- `AGENTS.md` — identity, mission, hard rules, and expected outputs for AI agents
- `README.md` — repo purpose, what belongs here vs. `org-config`
- `SECURITY.md` — org-wide responsible disclosure policy
- `profile/README.md` — organization profile page with repos and working principles
- `PULL_REQUEST_TEMPLATE.md` — default PR template (Context, Description, Validation, Risks)
- `.github/ISSUE_TEMPLATE/bug_report.yml` — structured bug report form
- `.github/ISSUE_TEMPLATE/feature_request.yml` — structured feature request form
- `.github/ISSUE_TEMPLATE/config.yml` — disable blank issues, link security policy

---

[Unreleased]: https://github.com/baena-labs/.github/compare/v0.1.2...HEAD
[0.1.2]: https://github.com/baena-labs/.github/compare/v0.1.1...v0.1.2
[0.1.1]: https://github.com/baena-labs/.github/compare/v0.1.0...v0.1.1
[0.1.0]: https://github.com/baena-labs/.github/releases/tag/v0.1.0
