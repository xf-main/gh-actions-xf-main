# gh-actions-xf-main

Org-specific wrapper workflows for the xf-main GitHub org. These workflows are
**thin wrappers** that call shared reusable workflows from `gh-actions-shared`.

## Triggers
- `repository_dispatch` for `orchestrator`, `discover`, and `summary`
Polling runs in the dedicated public repo: `gh-actions-xf-main-polling`.

## Requirements
- `BWS_ACCESS_TOKEN` and `BWS_PROJECT_ID` repo secrets
- `BWS_VERSION` and `BWS_SHA256` repo variables

All workflow logic resides in the shared repo.
