# Procedure: how this skill grades a plan package

<!--
THIS IS THE PART YOU WRITE, and it is a new kind of part. Weeks 1 and
2, SKILL.md carried a numbered workflow and you only wrote judgment
files. This week the workflow is gone from the frame: SKILL.md says
"execute procedure.md", and these are the operating steps you author.
The machinery is in your hands now.

Your operator swap is the design brief. When your executor stalled
because your rubric said WHAT to decide but not HOW to find the
evidence, that was a procedure gap. This file is where those gaps get
closed: a complete procedure lets someone who has never seen a plan
package before (a groupmate, or the skill itself) grade one exactly the
way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
repro evidence before the plan, and note what behavior it pins down"
is a step; "understand the context" is a wish.
-->

## Read order

 1. Read the Issue first and note the reported problem, expected behavior, and what triggers the bug.
2. Read the Repro evidence next and note what was actually tested, what happened, and any evidence that points toward or away from a possible cause.
3. Read the Repo facts and Thread highlights and note any relevant maintainer guidance, contribution rules, or project conventions.
4. Read the Candidate plan last, including its diagnosis, scope, proposed changes, test plan, risks or unknowns, and plan comment.
5. Keep the reproduction evidence separate from claims made in the plan or thread. A claim should not be treated as proven just because someone stated it.

## Evidence gathering

 1. For diagnosis, compare the cause stated in the Candidate plan with the Issue and Repro evidence. Record any evidence that supports or contradicts the proposed cause.
2. For scope, record the files and components the plan will change, anything it says it will not change, and whether those choices match the reproduced problem.
3. For implementation, record the specific files, components, and changes the plan gives another developer to work from.
4. For the test plan, compare the proposed tests with the original reproduction. Record whether the tests exercise the same important behavior and whether the result would clearly show if the bug is fixed.
5. For uncertainty, note important gaps in the evidence and check whether the plan treats those gaps as unknowns or assumes an answer without support.
6. For thread-conventions, compare the plan comment with relevant Thread highlights and Repo facts. Record any maintainer guidance or repository requirement that affects the proposed work.

## Check execution
1. Grade the checks in this order: diagnosis, scope, implementation, test-plan, uncertainty, and thread-conventions.
2. Use only the evidence gathered from the package for each check. Do not assume missing information or treat an unsupported claim as evidence.
3. Give a check a pass when its pass condition in rubric.md is satisfied.
4. Give a check a fail when the evidence contradicts the plan or the pass condition is not met.
5. Give a check unclear when the evidence needed to make the decision is genuinely missing or too ambiguous to judge.
6. Once the needed evidence has been gathered, grade from those notes instead of changing the standard based on the overall quality of the plan.
 

## Verdict assembly
1. Review the grade for every required check.
2. Accept the plan only when every required check passes.
3. Reject the plan if any required check fails or is unclear.
4. Preferred checks, if any are added later, do not change the final verdict.
5. In the output, briefly explain the evidence behind each grade. For a rejection, clearly identify the required check or checks that caused the rejection and quote or point to the evidence that supports that decision.
 
