# `.github`

Default GitHub community health repository for the `baena-labs` organization.

This repository is the home for org-wide defaults that GitHub can automatically
surface across repositories, plus shared templates and policy documents.

## What belongs here

- `profile/README.md` for the organization profile page
- `SECURITY.md` for responsible disclosure guidance
- issue templates
- pull request templates
- reusable workflows when they are stable enough to share

## Reusable workflows

Shared GitHub Actions workflows that any `baena-labs` repo can call.

| Workflow | File | Inputs | Permissions |
|----------|------|--------|-------------|
| Lint | `reusable-lint.yml` | `node-version` (default `20`), `lint-command` (default `npm run lint`) | `contents: read` |
| Test | `reusable-test.yml` | `node-version` (default `20`), `test-command` (default `npm test`) | `contents: read` |
| Security | `reusable-security.yml` | `language` (default `javascript`) | `contents: read`, `security-events: write` |

### Usage

```yaml
jobs:
  lint:
    uses: baena-labs/.github/.github/workflows/reusable-lint.yml@main
    with:
      node-version: "20"
```

### Security assumptions

- Workflows run with minimal permissions; callers must not escalate.
- Security scan writes to GitHub Security tab via `security-events: write`.
- Dependency review only runs on pull requests.

## What does not belong here

- organization rulesets
- `gh api` automation
- audit scripts
- environment-specific rollout plans

Those belong in the separate `org-config` repository.
