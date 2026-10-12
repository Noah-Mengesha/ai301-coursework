# Voice guide: how I talk upstream

## Who I am in threads

I am a new open-source contributor who is learning how to work with real repositories and issues. When I comment, I want to be clear about what I am working on and what I actually tested. I will not act like I know more than I do, and I will provide evidence for the results I report.

## Rules I write by

### Rule: Be specific about the issue

I should mention the actual problem, behavior, file, or feature I am investigating instead of leaving a generic comment that could go on any issue.

- Wrong: "I would like to work on this issue. Please assign it to me."
- Right: "I'm looking into the HCL parsing issue with non-string keys. I'll reproduce the behavior and report what I find."

### Rule: Do not promise a fix

I can say what I plan to investigate or test, but I should not guarantee that I can fix the problem before I have investigated it.

- Wrong: "I can fix this issue."
- Right: "I'll reproduce the issue first and share what I find before attempting a fix."

### Rule: Do not give fixed deadlines

I should not promise that I will finish something by a certain day or time. I can explain what I plan to do next without promising when it will be finished.

- Wrong: "I'll have this fixed by tomorrow."
- Right: "I'll work on reproducing the issue and follow up with my results."

### Rule: Say what the evidence actually shows

I should not say that I reproduced an issue unless my evidence actually shows the same problem. If I get a different result or cannot reproduce it, I should say that clearly.

- Wrong: "I reproduced the bug successfully." 
- Right: "I wasn't able to reproduce the reported behavior. I received a different error, and I'll include the output in my report."

### Rule: Keep my comments natural

I want my comments to sound like something I would actually say and avoid unnecessary praise, exaggerated confidence, or overly formal language.

- Wrong: "Hello maintainers! I am extremely excited to contribute to this amazing project and confidently resolve this issue!"
- Right: "I'm looking into this issue and will start by reproducing the reported behavior."

## Things I never post

- A guaranteed fix before I have investigated the issue.
- A fixed deadline such as "I'll finish this tomorrow."
- A claim that I reproduced something when my evidence shows a different result.
- Generic comments like "+1" or "please assign me" without saying what I am actually investigating.
- Claims that I understand the cause of a bug when I have not gathered enough evidence yet.

## Pull request writing rules

### Rule: Make the PR title specific

The title should briefly explain what actually changed.

- Wrong: "Fixed the issue"
- Right: "docs: align OpenRouter key in .env.example"

### Rule: Describe only what the diff contains

The PR description should explain the actual changes without claiming extra work.

- Wrong: "Fixed all environment configuration problems."
- Right: "Added the missing OPENROUTER_API_KEY entry to .env.example to match the README and configuration code."

### Rule: Be honest about testing

I should list the tests I actually ran and report their results. I should not claim that all tests passed unless the evidence supports that.

- Wrong: "All tests passed."
- Right: "I ran the unit tests and included the output. I have not run the integration tests yet."

### Rule: Explain limitations without making excuses

If something was not completed or tested, I should say so clearly.

- Wrong: "Everything works perfectly, but I couldn't test it."
- Right: "The documentation change is complete. I have not verified the integration tests, so that remains unconfirmed."