# Monday's Walkthrough — What to Show at Each Step

A self-contained demo of how a change flows through GitHub: branch → pull request → CI run → issue tracking.

## Outline

1. **The repo & the workflow**
   - Show the repo landing page and the README.
   - Open `.github/workflows/smoke.yml` — point out the workflow name `Smoke Check`, the `workflow_dispatch` trigger (that's why we can run it on demand), the single job `smoke-job`, and its one step that echoes `pipeline smoke check complete`.

2. **Trigger the workflow**
   - Go to the **Actions** tab, select **Smoke Check**, click **Run workflow**.
   - Watch the run appear in the list, click into it, open the `smoke-job` log, and scroll to the final line to see `pipeline smoke check complete`.
   - Mention the run number, the conclusion, and where billed usage shows up (the run's "Set up job"/telemetry — usage is per-job milliseconds).

3. **The branch**
   - Show the `demo/change-notes` branch in the branch dropdown — this branch contains exactly one change: this file, `docs/walkthrough.md`.
   - Explain why we work on a branch instead of committing straight to `main`.

4. **The pull request**
   - Open the draft pull request "Add walkthrough notes for the demo" from `demo/change-notes` → `main`.
   - Show the **Files changed** tab and explain draft vs. ready-for-review.
   - Point at the PR description — it references the Smoke Check run number and its conclusion, showing how CI evidence gets attached to a change.

5. **Issue tracking**
   - Open the issue "Demo walkthrough checklist" — its body records the run number, the job's conclusion, and the PR number.
   - Show the sub-issue "Clean up the demo repo after the walkthrough" nested under it.
   - Show the comment on the checklist issue summarizing the CI result.

6. **Security surface**
   - Open the **Security** tab → **Dependabot** — show what the alert list looks like for a tiny repo (and that an empty list is a normal result).

7. **Wrap-up**
   - Share the secret gist that captures the whole demo in one place: repo, PR, issues, run, job conclusion, usage, Dependabot result, and the printed line.
