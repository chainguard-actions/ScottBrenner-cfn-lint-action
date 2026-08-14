<!-- markdownlint-disable -->

# Hardening Report: ScottBrenner--cfn-lint-action/v2.5.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **ScottBrenner--cfn-lint-action/v2.5.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### broad-permissions (severity: medium)

The workflow '.github/workflows/scorecards-analysis.yml' sets top-level 'permissions: read-all', which grants overly broad read access to all scopes. It should be replaced with specific minimal permissions. The single job already has its own scoped permissions block, so the top-level broad grant is unnecessary.

Locations:

- `.github/workflows/scorecards-analysis.yml:11`

## Iteration Notes

### Iteration 1

**Fixes applied:** broad-permissions

**Notes:**

Replaced top-level 'permissions: read-all' with 'permissions: contents: read' in .github/workflows/scorecards-analysis.yml. The single job already has its own scoped permissions block (security-events: write, id-token: write), so the top-level only needs 'contents: read' for the checkout step. This eliminates the overly broad read-all grant while preserving all necessary functionality.

