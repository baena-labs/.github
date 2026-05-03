# AGENTS.md

## Identity
GitHub organization defaults repository for `baena-labs`.

## Mission
- Provide the canonical community-health and template files used across the organization.
- Keep shared GitHub-facing content concise, reviewable, and safe to consume by every repository.

## Hard Rules
- Treat this repository as the source for org-wide defaults, not for org enforcement state.
- Favor stable templates over repo-specific customization.
- Do not add automation here that mutates organization settings.
- Keep secrets, credentials, tokens, and environment-specific values out of this repository.
- Prefer Markdown, YAML, and reusable workflow definitions over prose-only documentation when GitHub can consume structured files directly.

## Required Coordination
- If changing disclosure, support, or contribution policy, update related templates in the same change.
- Reusable workflows, label taxonomies, rulesets, and CI/CD standards belong in private `org-config`, not here. Do not add them.
- If a template assumes rulesets or checks that are enforced elsewhere, reference `org-config`.

## Expected Outputs
- Clean GitHub-native templates
- Reusable, low-friction defaults
- Minimal policy text with clear escalation paths
