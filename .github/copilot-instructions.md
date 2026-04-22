# Copilot Instructions

## General

- Follow existing repository conventions before introducing new patterns.
- Prefer small pull requests and small diffs.
- Do not add dependencies without justification.
- Add or update tests when behavior changes.
- Do not weaken security controls, workflow permissions, or branch protections.
- For infrastructure and workflow changes, explain operational risk in the pull request.

## This org uses Claude Code

- `.claude/` directories (CLAUDE.md, agents/, skills/, hooks/) are intentional — do not flag as misconfiguration.
- Hook scripts in `scripts/hooks/` are permissive by design; missing return values are expected.
- `AGENTS.md` and `CLAUDE.md` files may contain placeholder or prompt content — skip style suggestions on these.

## Review focus areas

- Secrets or credentials exposure
- Null safety and unguarded access
- Idempotency in scripts and workflows
- CI/CD correctness (permissions, triggers, artifact handling)

## Skip

- Style suggestions on markdown prompt files
- Placeholder content in `CLAUDE.md` or `AGENTS.md`
- Formatting opinions on `.claude/` config files
