# Changelog

All notable changes to the `.github` org defaults repository are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

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
