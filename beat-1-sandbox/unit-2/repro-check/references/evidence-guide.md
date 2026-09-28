 # Evidence guide: where proof lives in a reproduction package

## Environment

**Where it lives:**  
In an eval package, look at the environment information in the repro report and compare it with the environment or version mentioned in the original issue. The repo-facts block can also show the version or environment information the repository asks contributors to provide. In live mode, look at the original GitHub issue and the environment information in the student's draft repro comment.

**What good looks like:**  
The report should include the relevant software/tool version and operating system. If the contributor tested a different version or environment from the original issue, they should clearly say what is different instead of leaving the reader to guess.

## Steps

**Where it lives:**  
Look at the setup, input, commands, and reproduction steps in the repro report. Compare them with the input, command, or trigger described in the original issue. In live mode, compare the student's draft steps with the original GitHub issue and the repo's setup instructions when needed.

**What good looks like:**  
Another person should be able to follow the steps from setup to the trigger without guessing important information. The steps also need to test the same problem described in the issue. A small change in the input or command that causes a different problem does not count as reproducing the same issue.

## Behavior shown

**Where it lives:**  
Look at the actual evidence in the repro report, such as terminal output, error messages, logs, screenshots, or other artifacts. Compare that evidence directly with the behavior described in the original issue.

**What good looks like:**  
The evidence should show the same behavior, error, or problem described in the issue if the contributor says they reproduced it. Getting an error is not enough if it is a different error. If the issue could not be reproduced, the evidence should clearly show what happened instead.

## Honesty

**Where it lives:**  
Compare the contributor's claim comment and statements in the repro report with the actual output, logs, screenshots, or other evidence they provided.

**What good looks like:**  
What the contributor says happened should match what the evidence actually shows. If they reproduced the issue, the evidence should support that. If they could not reproduce it, they should say that honestly and show the result they actually received. They should not claim the bug was reproduced when the evidence shows a different problem.

## Comms

**Where it lives:**  
Look at the claim comment and repro report and compare them with the original issue and the repo-facts block. Check the repository's contribution rules, templates, and any stated AI-use disclosure requirements. In live mode, check the GitHub issue, repository contribution documentation, and the student's draft comment.

**What good looks like:**  
The claim should be specific to the issue by mentioning the behavior, file, or investigation the contributor is working on instead of using a generic comment. The contributor should follow any communication or disclosure rules stated by the repository. If the repository requires AI-use disclosure, it should be included. The contributor should also avoid guaranteeing a fix or giving a fixed deadline.