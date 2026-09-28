# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

 ## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| environment | Look at the environment section of the repro report and compare it with the environment in the original issue. | Pass if the report includes the software/tool version and operating system. If the environment is different from the original issue, the difference should be clearly stated. | required |
| reproduction-steps | Look at the setup, input, commands, and steps in the repro report and compare them with the trigger described in the original issue. | Pass if another person could follow the steps without guessing and the steps actually test the same issue. Fail if an important command, input, or setup detail is missing or changed in a way that tests something different. | required |
| behavior | Compare the actual output, error, or other result in the repro report with the behavior described in the original issue. | Pass if the evidence shows the same problem described in the issue. Fail if it shows a different error, output, or behavior and the contributor claims they reproduced the issue. | required |
| evidence | Look at the terminal output, logs, screenshots, or other artifacts in the repro report and compare them with what the contributor says happened. | Pass if actual evidence is provided and supports what the contributor says happened. Fail if they only claim the issue was reproduced without showing proof, or if the proof shows something different. | required |
| outcome-honest | Compare what the contributor says happened in the claim/repro report with the actual evidence. | Pass if their statement matches the evidence. An honest cannot-reproduce can pass when the evidence supports it. Fail if they claim they reproduced the issue when the evidence shows a different result. | required |
| claim-specific | Look at the claim comment and compare it with the original issue. | Pass if the claim clearly identifies the specific issue, behavior, file, or investigation the contributor plans to work on. Fail if the claim is generic enough that it could be posted on almost any issue. | required |
| ai-disclosure | Look at the repo facts and contribution rules first, then check the claim comment and repro report if disclosure is required. | Pass if the repo does not require AI disclosure, or if it requires disclosure and the contributor provides it. Fail only when the repo clearly requires AI disclosure and the contributor does not disclose it. | required |
| no-guaranteed-deadline | Look at the contributor's claim comment and repro report for promises about completion or fixes. | Pass if the contributor does not guarantee a fix or a specific deadline. Fail if they make promises such as "I'll fix this tomorrow" or "I'll have this done in two days guaranteed." | preferred |

## Verdict rule

The package is ready if every required check passes. If any required check fails or there is not enough information to tell, the package is hold. Preferred checks do not change the final ready/hold verdict.
