# AGENTS.md (repo guidance)

## Repository purpose
Org-specific GitHub Actions wrapper workflows that call shared reusable workflows in the shared org.

## Non-negotiables
- No workflow logic here beyond thin wrappers.
- No secrets committed; use BWS via repo secrets.
- No `workflow_dispatch` (manual runs are disallowed). Only `repository_dispatch` and scheduled poller.
- `uses:` references must be pinned to a commit SHA in the shared repo.
- Wrapper workflows must pass event context inputs (`event-context`, `event-name`, `expected-event-action`).
- Summary workflow must pass BWS secrets for event validation.

## Permissions
- Default `contents: read`. Only elevate if absolutely required.
