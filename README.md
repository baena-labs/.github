# `.github`

Default GitHub community health repository for the `baena-labs` organization. **Public.**

This repository holds only what GitHub auto-surfaces across the org or what is genuinely safe to publish — community policies, default templates, and the org profile page. **Internal CI/CD logic, governance, and platform standards live elsewhere** (see below).

## What belongs here

- `profile/README.md` — the organization profile page
- `SECURITY.md` — responsible disclosure
- `CODE_OF_CONDUCT.md`
- `CONTRIBUTING.md`
- `AGENTS.md` — public self-description of this repo's purpose for AI maintainers
- `CHANGELOG.md` — history of this repo itself
- `.github/FUNDING.yml`
- `.github/ISSUE_TEMPLATE/` (the issue templates)
- `PULL_REQUEST_TEMPLATE.md` (root-level — the canonical PR template; per the project's own `CHANGELOG.md` entry for `0.1.1` the duplicate `.github/PULL_REQUEST_TEMPLATE.md` was removed)

If a file would expose internal implementation, governance, repo purposes, deployment logic, CI/CD standards, or AI tooling internals to the public, it does not belong here.

## What does not belong here

These live in the **private** `baena-labs/org-config` repository, the platform control plane:

- Reusable CI/CD workflows (lint, test, security, render-diagrams, label sync, etc.)
- Terraform workflow standards
- GitHub Actions permissions defaults
- Label taxonomy and the canonical labels manifest
- Org rulesets
- Repo onboarding and bootstrap automation
- Internal repo context, purposes, and governance documentation
- `gh api` admin scripts and audit tooling

If you are looking for a reusable workflow to call from a `baena-labs` repo, check `baena-labs/org-config/.github/workflows/`.
