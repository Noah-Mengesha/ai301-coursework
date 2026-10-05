# Evidence guide: where evidence lives in a plan package

<!--
THIS IS THE PART YOU WRITE (second week running: the judgment files
stay in your hands). The skill uses this guide as its map: for every
kind of evidence a rubric check names, this file says WHERE to find it
in a plan package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repro-evidence block,
  the candidate plan's scope statement or test plan, the plan comment,
  the repo-facts block). In live mode (where on GitHub or in the
  draft: the issue thread, the student's posted repro comment, the
  repo's docs, the draft plan and comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the stated cause cites behavior the
  repro evidence actually shows") over adjectives ("diagnosis is
  solid").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts twice: your
procedure.md tells the skill WHEN to gather each family, and this
guide tells it WHERE. Write the map you wish your executor had.
-->

## Diagnosis and grounding

 **Where it lives:** In eval packages, look at the Candidate plan's diagnosis and compare it with the Issue and Repro evidence. In live mode, look at the diagnosis in plan.md and compare it with the GitHub issue and the reproduction comment.

**What good looks like:** The cause described in the plan should make sense based on what the reproduction actually showed. A diagnosis should not ignore or contradict important reproduction results.

## Scope
**Where it lives:** In eval packages, look at the Candidate plan's scope, files, and proposed changes. In live mode, look at the scope, files to touch, and approach in plan.md.

**What good looks like:** The plan should stay focused on the reproduced problem and clearly identify the files or areas that need to change. It should avoid unrelated changes or unnecessary rewrites.
 

## Executability
**Where it lives:** In eval packages, look at the Candidate plan's proposed changes, files, and implementation approach. In live mode, look at the files and approach described in plan.md.

**What good looks like:** Another developer should be able to understand where to start and what the plan intends to change without having to guess the main implementation steps.
 

## Test plan

 **Where it lives:** In eval packages, compare the Candidate plan's test plan with the steps, expected behavior, and actual behavior in the Repro evidence. In live mode, compare the test plan in plan.md with the student's reproduction comment.

**What good looks like:** The test should exercise the important behavior from the reproduction and have an observable result that shows whether the bug is still present or has been fixed.

## Honesty

 **Where it lives:** In eval packages, look at the Candidate plan's diagnosis, risks, unknowns, and any claims that depend on information not proven by the Repro evidence. In live mode, look at the risks, unknowns, and Deviations section in plan.md.

**What good looks like:** Important unknowns should be described honestly instead of being presented as facts. If the implementation later differs from the original plan, the difference and reason should be recorded under Deviations.

## Comms

 **Where it lives:** In eval packages, compare the Candidate plan comment with the Thread highlights and Repo facts. In live mode, compare the draft comment with the GitHub issue thread and relevant repository contribution documentation.

**What good looks like:** The comment should be specific to the issue and should not ignore relevant maintainer guidance or repository requirements. If the repository requires something such as AI-use disclosure, the comment should follow that requirement.
