# Procedure: how this tool grades a PR package

## Read order

1. Determine whether the request is in live mode or eval mode. In live mode, read `scope.md` first and confirm the repository is allowed. In eval mode, use only the provided package.
2. Read `rubric.md` and `references/evidence-guide.md` to understand the checks and where the evidence should come from.
3. Read the issue and accepted plan before examining the PR. Record the problem being solved, planned files, scope boundaries, test plan, and any documented deviations. This gives a baseline for checking the implementation.
4. Read the repository facts, PR template, and contribution requirements. In live mode, obtain these from the repository and issue thread. In eval mode, use only what the package provides.
5. Read the candidate PR's title, description, checklist, and test claims. Record what the contributor says was changed and tested.
6. Examine the diff and commit information. In live mode, run `git diff main...HEAD` from the repository working copy. In eval mode, use the diff included in the package.
7. Read the test evidence last, comparing the actual commands and output with the plan's test requirements and the PR's claims. In live mode, also read `voice-guide.md` and note any problems with the outgoing title or description.

## Evidence gathering

1. **Plan fidelity:** List the files and behavior the accepted plan allows. Compare each changed file and meaningful diff hunk against that list. Check whether additional or omitted work is explained under the plan's Deviations section. Record any unexplained differences.
2. **Test evidence:** List the checks required by the plan and repository. Compare them with the test-evidence section, before/after reproduction output, regression test assertions in the diff, and reported command results. Accept specific summarized test outcomes when they are consistent with the supporting evidence. Do not demand full terminal logs when the package already provides credible, observable proof. Record missing, contradictory, or undisclosed testing gaps.
3. **Diff quality:** Inspect the changed code for unrelated edits, debugging statements, commented-out experiments, accidental files, or changes that are not needed for the issue. Record the exact file or hunk where a problem appears.
4. **Standards compliance:** Compare the PR description and checklist with the repository's PR template, contribution guidelines, and disclosure requirements. Record which applicable requirements are satisfied or missing.
5. **Description accuracy:** Compare every important implementation, testing, and documentation claim with the diff and test evidence. Record claims that are contradicted or cannot be verified.
6. **Reviewer clarity:** Check whether the title and description explain the purpose, relevant changes, test results, and limitations clearly enough for review. Record specific confusing or missing information rather than judging writing style alone.

## Check execution

1. Execute the checks in the order listed in `rubric.md`: `plan-fidelity`, `test-evidence`, `diff-quality`, `standards-compliance`, `description-accuracy`, and `reviewer-clarity`.
2. For each check, use its stated pass condition and the evidence already gathered. Assign `pass`, `fail`, or `unclear` and record one concrete fact or quotation explaining the grade.
3. Mark a check `pass` when the available evidence satisfies its condition. Mark it `fail` when the evidence shows a violation. Mark it `unclear` when necessary evidence is missing or the result cannot be determined.
4. Do not treat an honestly disclosed limitation as an automatic failure. Determine whether the actual change, evidence, and description still meet the check's written requirements.
5. Do not invent missing evidence, assume tests passed, or infer changes that are not shown. Revisit a source only when needed to verify a specific fact.
6. Grade every check, even if an earlier required check already failed. Do not stop early or change the rubric during a run.

## Verdict assembly

1. Apply the verdict rule in `rubric.md` after all checks have been graded.
2. Return `accept` only if every required check passes. Return `reject` if any required check is `fail` or `unclear`. Preferred checks do not change the verdict.
3. If the verdict is `reject`, identify the first failing or unclear required check in rubric order as the primary reason. Mention other failures in the summary so the contributor knows what to fix.
4. Support the primary reason with the specific file, diff detail, missing evidence, or repository requirement that caused the decision.
5. Produce a readable per-check summary, then the fixed JSON block defined in `SKILL.md`. Include the package identifier, all check names, their grades, and one evidence line for each check.
6. Use only `accept` or `reject` as the final verdict. The fenced JSON block must be valid and must be the last content in the response, with nothing after it.
