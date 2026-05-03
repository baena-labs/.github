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
| Lint | `reusable-lint.yml` | `node-version` (default `20`), `lint-command` (default `npm run lint`), `install-command` (default `npm ci`) | `contents: read` |
| Test | `reusable-test.yml` | `node-version` (default `20`), `test-command` (default `npm test`), `install-command` (default `npm ci`) | `contents: read` |
| Security | `reusable-security.yml` | `language` (default `javascript`) | `contents: read`, `security-events: write` |
| Render diagrams | `reusable-render-diagrams.yml` | `python-version` (default `3.12`), `diagrams-version` (default `0.25.1`), `source-dir` (default `diagrams`), `output-dir` (default `docs/diagrams`), `commit-message` (default `chore(diagrams): render architecture diagrams [skip ci]`) | `contents: write` |
| Sync labels | `reusable-sync-labels.yml` | `labels-source` (default `baena-labs/.github`), `labels-ref` (default `main`), `labels-path` (default `labels.yml`) | `issues: write` |

### Caller requirements

- **`reusable-lint.yml` and `reusable-test.yml`** are Node-based and assume an npm project with a `package-lock.json` (used for `cache: npm` and the default `npm ci`). For yarn/pnpm, override `install-command` — note that the dependency cache will still be configured for npm. Non-Node repos should use their own workflow.
- **`reusable-security.yml`** uses CodeQL. For TypeScript-heavy repos, pass `language: javascript-typescript` (the modern identifier covers both JS and TS).
- **`reusable-render-diagrams.yml`** assumes diagrams are written with the [`diagrams`](https://diagrams.mingrammer.com/) Python library, one Python file per diagram, sourced from `source-dir`. The job pushes rendered PNGs back to the calling branch — callers must grant `permissions: contents: write` and should invoke this on `push` events (not `pull_request` from forks, where the push will fail). Branch-protected branches that require signed or reviewed commits will reject the bot push; in those cases call this on a separate branch and open a PR.
- **`reusable-sync-labels.yml`** is **additive only** — it creates missing labels and updates color/description on existing matches, but never deletes labels. Repo-specific labels (e.g. `area: brain` in `legal-brain`) survive untouched. Edit `labels.yml` in this repo to update the canonical set; consumers re-sync on `workflow_dispatch` or whatever trigger they configure on their caller. Callers must grant `permissions: issues: write`.

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
- All jobs have `timeout-minutes` set to bound runner usage.
- All third-party actions are pinned to commit SHAs (with a trailing `# vX.Y.Z` comment) and bumped weekly via Dependabot — see `.github/dependabot.yml`.

## What does not belong here

- organization rulesets
- `gh api` automation
- audit scripts
- environment-specific rollout plans

Those belong in the separate `org-config` repository.
