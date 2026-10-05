# Rubric: is this plan ready to post and build from?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here (via your procedure.md). It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the plan's scope statement, the test plan read against
     the repro evidence's steps, the plan comment read against the
     thread highlights, the repo-facts block) or a location from your
     references/evidence-guide.md. "The plan" is not a source; "the
     plan's stated cause read against what the repro evidence shows"
     is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (is
     this one bounded change? could a stranger start executing it?),
     never the write-up's shape (how many sections it has, how long it
     is, whether it uses headings). Structure-shaped checks are what
     make graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad plans posted. The lecture named the
failure families: the diagnosis ignores or contradicts the reproduced
evidence, the change is unbounded (scope creep), the plan targets the
symptom while the evidence points at the cause, a stranger could not
start executing it, the test plan proves nothing observable, the
unknowns are dressed up as certainty, and the comment ignores what the
thread or the repo's stated conventions ask. A rubric that ignores a
family will fail eval packages designed around that family.
-->

## Checks

 | Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| diagnosis | Compare the cause described in the plan with the issue and the Repro evidence. | Pass if the cause makes sense based on what the reproduction actually showed. Fail if the evidence contradicts the cause or points to a different cause. Use unclear if there is not enough evidence to tell. | required |
| scope | Look at what the plan says it will change and compare that with the reproduced problem. | Pass if the changes stay focused on the problem and the plan is not changing unrelated parts of the project. Fail if the plan goes outside the problem or focuses on an area the evidence does not support. | required |
| implementation | Look at the files, components, and changes described in the plan. | Pass if there is enough detail for another developer to understand where to start and what needs to change. Fail if the plan is too vague or leaves the main implementation details unclear. | required |
| test-plan | Compare the plan's test steps with the Repro evidence and the original bug. | Pass if the test would recreate the important behavior and clearly show whether the bug is fixed. Fail if the test does not actually prove that the reproduced problem is gone. | required |
| uncertainty | Compare the plan's claims with the issue and Repro evidence, and look at any risks or unknowns it mentions. | Pass if the plan is honest about important things that are still unknown. Fail if it treats an unsupported assumption as a fact and depends on that assumption for the fix. | required |
| thread-conventions | Compare the plan comment with the thread highlights and Repo facts. | Pass if the plan follows relevant maintainer guidance and repository requirements. Fail if it ignores or conflicts with guidance or requirements that matter to the proposed change. | required |

## Verdict rule
Accept the plan if every required check passes. Reject the plan if any required check fails or is unclear. Preferred checks do not affect the final verdict.
<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict;
unclear counts as fail." -->
