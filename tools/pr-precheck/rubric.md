# Rubric: is this pull request ready to submit?

 

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| plan-fidelity | Compare the changed files and code in the diff against the accepted plan, its scope, and documented deviations. Check the PR description against those changes. | Pass when the changes stay within the plan or clearly documented, relevant deviations, and the description accurately explains what was done. Fail when the diff silently adds, removes, or changes planned work, or falsely claims exact plan compliance. | required |
 | test-evidence | Compare the plan's test plan with the test-evidence section, reproduction output, regression tests in the diff, and reported repository check results. | Pass when the available evidence credibly supports the reported behavior and testing outcome, including reproduction output, relevant test assertions, or specific command results. A concise result such as "pytest tests/ -q passes (1462 passed, 12 skipped)" is acceptable when consistent with the other evidence. Fail when testing is absent without disclosure, evidence contradicts the claims, or claimed success has no meaningful supporting details. | required |
| diff-quality | Inspect the changed files and hunks in the diff, using the issue and plan to identify relevant work. | Pass when the diff contains focused, reviewable changes related to the issue. Fail when unrelated edits, debugging leftovers, accidental files, or unnecessary changes make the PR harder to review or introduce unplanned behavior. | required |
| standards-compliance | Compare the PR title and description with the repository's PR template, contribution requirements, and any stated disclosure policy in Repo facts or live repository files. | Pass when the PR follows applicable repository requirements, including required disclosures, or transparently identifies a genuine limitation without falsely claiming compliance. Fail when mandatory template sections, policy requirements, or required disclosures are ignored. | required |
| description-accuracy | Compare the PR description, checklist, and test claims directly against the diff and test evidence. | Pass when important claims are supported by the supplied artifacts and the description gives a reviewer an accurate picture of the change. Fail when it claims nonexistent tests, missing files, unsupported results, or functionality the diff does not demonstrate. | required |
| reviewer-clarity | Read the PR title, description, and evidence alongside the issue and planned work. | Pass when a reviewer can understand the purpose of the change, its boundaries, and known limitations without unnecessary guessing. Mark unclear when information is difficult to follow but no required factual or policy violation is established. | preferred |

## Verdict rule

Grade every check as pass, fail, or unclear using the available evidence.

Return `accept` only when every required check passes. Return `reject` if any required check fails or is unclear. Preferred checks should be reported but never change the final verdict.

A PR should not automatically fail because a test is unavailable, a limitation remains, or the implementation differs from the original plan. Judge whether the limitation or deviation is relevant, honestly disclosed, and supported by the available evidence. However, an unsupported claim of successful testing, hidden scope change, unrelated code change, or ignored mandatory repository requirement fails its corresponding required check.

Use the same verdict rule in live and eval modes. Every grade must cite a concrete fact, diff detail, or test result from the available materials.