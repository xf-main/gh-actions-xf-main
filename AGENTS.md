# AGENTS.md (repo guidance)

## Repository purpose
Org-specific GitHub Actions wrapper workflows that call shared reusable workflows in the shared org.

## Non-negotiables
- No workflow logic here beyond thin wrappers.
- No secrets committed; use BWS via repo secrets.
- No `workflow_dispatch` (manual runs are disallowed). Only `repository_dispatch` and scheduled poller.
- `uses:` references must be pinned to a commit SHA in the shared repo.

## Permissions
- Default `contents: read`. Only elevate if absolutely required.
