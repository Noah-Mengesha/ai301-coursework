---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading
 
## The question

Decide whether one candidate pull request is ready to submit. Review the PR title, description, commits, diff, and test evidence against the accepted plan, any documented deviations, the issue, and repository requirements. Grade one PR package at a time and do not replace evidence-based review with general advice.

## Inputs and modes

In live mode, read plan.md including its Deviations section, the draft title and description from pr_draft.md, test results from test_evidence.md, and the issue URL and discussion. From the repository working copy, run git diff main...HEAD to inspect every committed change relative to main. Read the repository PR template and docs/CONTRIBUTING.md, and compare the change with the issue's requirements. For a house-chain submission, use the provided house plan and reproduction package in place of the student's originals.

In eval mode, use only the supplied evaluation package. It contains the plan context, issue information, candidate PR, diff, and test evidence needed for review. Do not fetch external information, inspect unrelated local files, or assume missing evidence exists. Run every rubric check and apply the complete verdict rule.

## The scope seam (live mode only)

Read scope.md before any other live-mode input. Confirm the repository matches its Repo line and follow the stated house rules. Refuse to grade a PR outside that repository. If the Repo line still contains a placeholder, stop and ask the user to fill it with the correct Path Review repository. Never guess the scope. Ignore scope.md entirely in eval mode.

## The voice seam (live mode only)

Read voice-guide.md and compare the outgoing PR title and description with its writing rules. Report any violations clearly in the readable summary. Voice issues do not independently change the verdict unless a rubric check specifically covers them. Do not read or apply voice-guide.md in eval mode.

## Component reads

Read rubric.md to identify the checks, evidence requirements, pass conditions, weights, and verdict rule. Read references/evidence-guide.md to locate and interpret evidence. Execute procedure.md in its stated order, without skipping or inventing steps. If the procedure does not explain a necessary step, report the gap instead of improvising a new method. If rubric.md or procedure.md has no substantive instructions, refuse to grade and explain which component needs to be completed.

## Verdict and output

Return exactly one final verdict: accept when the PR meets the rubric's readiness rule, or reject when it must be held for fixes or missing evidence. Give a short readable summary of each check, then end with the fixed fenced JSON block below. Include every check, its pass, fail, or unclear grade, and one specific evidence line. The JSON must be valid, follow the fixed schema, and be the last content in the response.

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}
```

## Grading discipline

Use actual facts, diff lines, or command output for every grade. Evaluate test evidence in context. Specific test commands with summarized results, before/after reproduction output, and regression assertions in the diff can establish credible testing evidence. Do not require complete terminal logs when the package provides consistent, verifiable details. Reject unsupported claims of testing, contradictory results, or missing tests required by the plan. Compare the PR's actual changes against the plan and issue, not how polished the description sounds. Apply rubric.md's written conditions consistently, even when a result feels surprising. Follow procedure.md rather than inventing checks during a run. If the rubric does not say otherwise, treat unclear or unverifiable required evidence as a failure for readiness. Do not claim tests ran, changes were reviewed, or requirements were met unless the available evidence supports that conclusion.