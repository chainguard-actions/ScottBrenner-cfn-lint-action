<!-- markdownlint-disable -->

# Hardening Report: ScottBrenner--cfn-lint-action/v2.7.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **ScottBrenner--cfn-lint-action/v2.7.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### broad-permissions (severity: medium)

The workflow file .github/workflows/scorecards-analysis.yml has a top-level `permissions: read-all` setting, which grants overly broad read access to all scopes. This should be replaced with specific minimal permissions (e.g., only the scopes actually needed). The job-level permissions block only adds `security-events: write` and `id-token: write`, but the top-level `read-all` still grants unnecessary broad access to all other scopes.

Locations:

- `.github/workflows/scorecards-analysis.yml:11`

## Iteration Notes

### Iteration 1

**Fixes applied:** broad-permissions

**Notes:**

Replaced top-level `permissions: read-all` in `.github/workflows/scorecards-analysis.yml` with specific minimal permissions: `contents: read` and `actions: read`. These are the only read scopes actually needed by the workflow steps (checkout and scorecard analysis). The job-level permissions block already specifies `security-events: write` and `id-token: write` for the scopes that require write access.

