<!-- markdownlint-disable -->

# Hardening Report: ScottBrenner--cfn-lint-action/v2.8.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **ScottBrenner--cfn-lint-action/v2.8.0** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### broad-permissions (severity: medium)

The workflow file .github/workflows/scorecards-analysis.yml has a top-level `permissions: read-all` setting. This grants overly broad read access across all scopes and should be replaced with specific minimal permissions (e.g., `contents: read`, `security-events: write`, `id-token: write` as needed per job).

Locations:

- `.github/workflows/scorecards-analysis.yml:10`

## Iteration Notes

### Iteration 1

**Fixes applied:** broad-permissions

**Notes:**

Replaced top-level `permissions: read-all` in `.github/workflows/scorecards-analysis.yml` with specific minimal permissions `contents: read`. The job-level permissions (`security-events: write` and `id-token: write`) were already correctly scoped and remain unchanged.

