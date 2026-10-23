# Pipeline Demo — Monday Walkthrough Notes

Everything for the live demo in one place.

> **Note:** This file is a fallback. The plan was to capture these notes in a **secret gist** named `demo-walkthrough-notes.md`, but the API token in use cannot create gists (`POST /gists` → 403 Resource not accessible by personal access token, confirmed on retry). The same content is kept here instead.

## Repo
- Name: **mcpmark-eval-liuhezi/pipeline-demo-3**
- URL: https://github.com/mcpmark-eval-liuhezi/pipeline-demo-3
- Note: requested as `pipeline-demo` in the personal account; the token cannot create repos in the personal account, and in the accessible org `pipeline-demo` and `pipeline-demo-2` were already taken, so **`pipeline-demo-3`** was used.

## Pull request
- Number: **#1** — "Add walkthrough notes for the demo"
- Link: https://github.com/mcpmark-eval-liuhezi/pipeline-demo-3/pull/1
- Branch: `demo/change-notes` → `main`; adds `docs/walkthrough.md`. Opened as a draft, then marked ready for review. The description references Smoke Check run #1 and its `success` conclusion.

## Issues
- **#2** — "Demo walkthrough checklist" (body records the run number, the smoke-job conclusion, and the PR number): https://github.com/mcpmark-eval-liuhezi/pipeline-demo-3/issues/2
- **#3** — "Clean up the demo repo after the walkthrough" (attached as a sub-issue of #2): https://github.com/mcpmark-eval-liuhezi/pipeline-demo-3/issues/3

## Workflow run (Smoke Check, .github/workflows/smoke.yml)
- Run number: **#1**
- Conclusion: **success**
- Link: https://github.com/mcpmark-eval-liuhezi/pipeline-demo-3/actions/runs/39891741774

## Job
- Job: `smoke-job` — conclusion **success**
- Job link: https://github.com/mcpmark-eval-liuhezi/pipeline-demo-3/actions/runs/39891741774/job/120212887191
- Log tail ends with the step output line (see below) plus runner cleanup (`Cleaning up orphan processes`).

## Billed usage (as reported by the API)
- UBUNTU: total_ms **0**, jobs **1**, job run duration_ms **0** (job_id 120212887191)
- run_duration_ms: **11000** (~11 s wall-clock for the whole run)

## Dependabot result
- The check returned an error, not a list: `GET /repos/mcpmark-eval-liuhezi/pipeline-demo-3/dependabot/alerts` → **403 Resource not accessible by personal access token**. Retried once — same 403. The API token lacks the scope needed to read Dependabot alerts, so the alert list could not be retrieved via the API. Check the **Security → Dependabot** tab in the UI to view alerts directly.

## The line the workflow prints
- `pipeline smoke check complete`
