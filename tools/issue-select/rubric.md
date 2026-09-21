# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.

## Checks

|Check|Evidence|Pass condition|Weight|
|-|-|-|-|
|Maintainer activity|"last 5 default-branch commits" and "maintainer first-response sample" under Repo facts; maintainer comments in the Comments section|Pass if there is at least one non-bot default-branch commit within 90 days of the capture date, or a maintainer response/comment within 90 days. Bot-only activity does not count by itself.|required|
|Repository in use|"archived:", "latest release", and "last push to any branch" under Repo facts|Pass if the repository is not archived and either the latest release or last push occurred within 180 days of the capture date.|required|
|Newcomer-sized scope|Issue body and Comments section| Pass if the issue describes one bounded problem or contribution with a<br />clear goal. Judge the required outcome, not the length of the issue or<br />the number of possible implementation ideas listed. Optional,<br />additional, or suggested improvements do not make an otherwise bounded<br />issue fail.<br /><br />Fail if the issue is explicitly an umbrella/tracking issue intended to<br />be split into separate work, is a pure usage/support question, requires<br />core-internal changes according to a maintainer, or has unresolved<br />design debate with no maintainer-settled direction.<br /><br />Also fail when the issue's history shows multiple abandoned contributor<br />attempts or closed unmerged PRs indicating that the task has repeatedly<br />proven difficult to complete. A long or technically detailed issue<br />without that history can still pass.|required|
|Issue unclaimed|"this issue: assignees:" and "linked PRs:" under Repo facts, plus claim statements and PR mentions in the Comments section|Pass if there is no current assignee, no open linked or mentioned PR implementing the issue, and no active claim from another contributor. Closed unmerged PRs or clearly abandoned claims do not fail this check.|required|
|AI contribution allowed|"contribution policy" under Repo facts, including referenced AI policy files|Pass if the repository is silent about AI use or permits AI-assisted contributions. Fail if the repository explicitly bans AI-generated or AI-assisted contributions applicable to this work.|required|
|First-issue signal|Issue labels and issue body|Pass if a maintainer has labeled or explicitly described the issue as appropriate for a new or first-time contributor.|preferred|

## Verdict rule

Accept if every required check passes. Reject if any required check fails. Treat unclear evidence on a required check as a failure unless the check's pass condition explicitly says that silence passes. Preferred checks never change the final accept/reject verdict; they are only used to rank issues that pass all required checks.

