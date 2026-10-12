 # Evidence guide: where evidence lives in a PR package

## Plan fidelity (harness category: silent-drift)

Where to look:
- Eval mode: Read the plan-context block, including its scope, boundaries, and deviations. Compare these with the candidate PR's unified diff, changed files, and description.
- Live mode: Read plan.md, especially the scope and Deviations section. Run `git diff main...HEAD` from the repository working copy. Compare the diff with the issue and pr_draft.md.

What good looks like:
Every meaningful change in the diff matches the accepted plan or a clearly documented, relevant deviation. Planned work that was not completed is disclosed accurately.

Fail when the PR silently changes more or less than planned, or the description claims work that the diff contradicts. An honestly disclosed deviation is not automatically a failure.

## Test evidence (harness category: not-tested)

Where to look:
- Eval mode: Compare the plan-context test plan and reproduction steps with the candidate PR's test-evidence section, including commands, printed results, and before/after behavior.
- Live mode: Compare plan.md's test plan with test_evidence.md. Check actual command output for the reproduction steps and repository checks.

What good looks like:
The evidence identifies what was tested, the expected outcome, and the observed result. Successful test claims are supported by actual commands and output.

Fail when the PR claims tests passed without observable proof, omits relevant tests without disclosure, or misrepresents failing results. Clearly disclosed limitations are evaluated according to the rubric rather than rejected automatically.

## Diff quality (harness category: unreviewable)

Where to look:
- Eval mode: Inspect the candidate PR's unified diff, changed-file list, and commits.
- Live mode: Inspect `git diff main...HEAD`, the changed-file list, and the branch's commits. Compare them with the issue and plan.

What good looks like:
The fix is visible in the diff, and the changes are focused on the issue. A reviewer can identify what changed without unrelated edits obscuring the implementation.

Fail when the diff includes unrelated files, debugging leftovers, dead code, accidental artifacts, large unnecessary formatting changes, or drive-by edits that make the change difficult to review.

## Standards and comms (harness category: standards-wall)

Where to look:
- Eval mode: Read the repo-facts block for PR template requirements, contribution rules, stated policies, and AI-use disclosure requirements. Compare these with the candidate PR's title, description, checklist, and issue discussion.
- Live mode: Read the repository's PR template, docs/CONTRIBUTING.md, and relevant maintainer instructions in the issue thread. Compare them with pr_draft.md. Read voice-guide.md for title and description style.

What good looks like:
The PR addresses applicable template questions with meaningful information, follows repository contribution requirements, includes required disclosures, and responds to relevant maintainer instructions.

Fail when mandatory sections, policies, or disclosures are ignored. Boilerplate that does not answer a required question is not sufficient. Voice-guide.md violations should be reported in live mode but do not independently change the verdict.

Also verify that important statements in the description match the actual diff and test evidence. Unsupported claims should be graded under the relevant rubric checks.
