# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/73

**Verdict output**

Ranking caveat: the "Your fit profile" section of scope.md is still the unedited template — it ends with "(Write a few sentences here.)". With no profile to rank against, I used a neutral default: #73 first because it is a two-file documentation change with no test-marker or CI-marker work and zero classmate movement, which is the lowest-friction path to a first merged PR; #72 second because it additionally requires a Python behavior change plus the strict-xfail removal, and two classmates already have commits referencing it. Fill in that profile and the order may legitimately flip — neither verdict changes either way.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/73",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Human commits to main by Aburke225 on 2026-09-16 and COLLABORATOR comments closing #52/#43 on 2026-09-16, 5 days before capture."},
      {"name": "Repository in use", "grade": "pass", "evidence": "archived=False; last push to any branch 2026-09-16T21:50:20Z, within 180 days of 2026-09-21."},
      {"name": "Newcomer-sized scope", "grade": "pass", "evidence": "One bounded goal: 'Make the two files agree' across README.md and .env.example; discrepancy verified in the tree."},
      {"name": "Issue unclaimed", "grade": "pass", "evidence": "assignees: (none); comments_count: 0; no PRs exist in the repo; timeline shows only 4 'labeled' events."},
      {"name": "AI contribution allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PULL_REQUEST_TEMPLATE.md contain no AI clause; no AI policy file in the repo."},
      {"name": "First-issue signal", "grade": "pass", "evidence": "Labels applied by maintainer Aburke225 include 'good first issue'."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/72",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Human commits to main by Aburke225 on 2026-09-16 and COLLABORATOR comments closing #52/#43 on 2026-09-16, 5 days before capture."},
      {"name": "Repository in use", "grade": "pass", "evidence": "archived=False; last push to any branch 2026-09-16T21:50:20Z, within 180 days of 2026-09-21."},
      {"name": "Newcomer-sized scope", "grade": "pass", "evidence": "One bounded behavior change in core/security.py plus removing the confirmed xfail marker in tests/unit/test_security.py; no design debate, no prior attempts."},
      {"name": "Issue unclaimed", "grade": "pass", "evidence": "assignees: (none); 0 comments; no PRs in repo; the two 2026-09-20 'referenced' events are commits in classmates' own coursework forks, which the Path Review house rule says do not block."},
      {"name": "AI contribution allowed", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PULL_REQUEST_TEMPLATE.md contain no AI clause; no AI policy file in the repo."},
      {"name": "First-issue signal", "grade": "pass", "evidence": "Labels applied by maintainer Aburke225 include 'good first issue'."}
    ],
    "verdict": "accept"
  }
]
```

---

## Eval iterations

**Run history**

Run 1: 17/20 scored items.

Partial re-run of issue-01, issue-15, and issue-19: 3/3.

Final full run: 18/20 scored items (PASS).

**Issue analysis**

issue-09: My rubric decided reject, while the gold label was accept. The Newcomer-sized scope check caused the rejection. My rubric interpreted the issue as not meeting the bounded newcomer-scope requirement. Because this is a required check, failing it caused the final verdict to be reject.

**Check rationale**

"Newcomer-sized scope — Pass if the issue describes one bounded problem or contribution with a clear goal. Judge the required outcome, not the length of the issue or the number of possible implementation ideas listed. Optional, additional, or suggested improvements do not make an otherwise bounded issue fail. Fail if the issue is explicitly an umbrella/tracking issue intended to be split into separate work, is a pure usage/support question, requires core-internal changes according to a maintainer, or has unresolved design debate with no maintainer-settled direction. Also fail when the issue's history shows multiple abandoned contributor attempts or closed unmerged PRs indicating that the task has repeatedly proven difficult to complete. A long or technically detailed issue without that history can still pass."

I used this wording because my earlier version treated some long or technically detailed issues as too large even when the actual requested contribution was bounded. I changed the check to focus on the required outcome instead of issue length or optional suggestions. I also added issue history because repeated abandoned attempts can show that an apparently simple issue is actually difficult for a first contribution.

**Trade-offs**

Before the revision, issue-01 and issue-19 were rejected even though their gold labels were accept, while issue-15 was accepted even though its gold label was reject. I re-ran those three issues with `--only`, and the revised rubric agreed on all three (3/3). The final full run still disagreed on issue-09 and issue-20 and finished at 18/20.

---

## Selection rationale

**Selection rationale**

1. I selected issue #73 because it is a bounded documentation change that fits my interests and can realistically be completed within the time available.

2. The verdict correctly identified that the repository is active, the issue is unclaimed, the work has a bounded goal, and there is no AI policy blocking the contribution. I also considered my own comfort with the work and preferred the lower-friction documentation task over a code behavior change.

3. I expect claiming the issue to be straightforward because it currently has no assignee, no comments indicating an active claim, and no PR implementing it.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
