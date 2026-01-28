# AGENTS.md (repo guidance)

## Repository purpose
Org-specific GitHub Actions wrapper workflows that call shared reusable workflows in the shared org.

## Non-negotiables
- No workflow logic here beyond thin wrappers.
- No secrets committed; use BWS via repo secrets.
- Use `workflow_dispatch` only (no `repository_dispatch`).
- Polling is triggered by the Worker cron via `polling.yml` (no polling repos).
- `uses:` references must be pinned to a commit SHA in the shared repo.
- Wrapper workflows must pass event context inputs (`event-context`, `event-name`, `expected-event-action`).
- Summary workflow must pass BWS secrets for event validation.
- Workflow-level permissions must be `{}`; set minimal permissions per job.

## Permissions
- Default `contents: read`. Only elevate if absolutely required.
