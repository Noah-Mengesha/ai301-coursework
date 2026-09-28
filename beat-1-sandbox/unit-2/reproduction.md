# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

Record of your claim and reproduction on the issue you chose in Unit 1, and of the
evaluation runs that produced `eval-run.txt`. This file is graded at the path above; a copy
kept anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your identity upstream

**GitHub username**
 Noah-Mengesha

---

## Posted upstream

**Claim comment**
 https://github.com/codepath/pathreview-ai301-fa26-s3/issues/73#issuecomment-5864152218

Hi, I'd like to work on this issue. I'll start by checking the OPENROUTER_API_KEY and LLM_PROVIDER differences between README.md and .env.example and confirm the inconsistency described here. I'll follow up with what I find.
 

**Reproduction comment**
https://github.com/codepath/pathreview-ai301-fa26-s3/issues/73#issuecomment-5864623284
 Reproduction Report Issue #73

Environment

OS: Microsoft Windows NT 10.0.26200.0
Python: 3.11.9
Repository commit: 2f4e82f
Steps

I cloned my fork of the Path Review repository and checked the files mentioned in the issue.

I checked README.md using:

Get-Content README.md | Select-String "OPENROUTER|LLM_PROVIDER"

The output included:

# Configure environment (add your OPENROUTER_API_KEY to .env)

I then checked .env.example using:

Get-Content .env.example | Select-String "OPENROUTER|OPENAI|LLM_PROVIDER"

The output was:

# Options: "mock" (default, no API key needed), "openai"
LLM_PROVIDER=mock
OPENAI_API_KEY=sk-your-key-here

I also checked core/config.py using:

Get-Content core/config.py | Select-String "OPENROUTER|OPENAI|LLM_PROVIDER"

The output included:

llm_provider: str = Field(default="mock")
openai_api_key: str = Field(default="")
openrouter_api_key: str = Field(default="")
openrouter_base_url: str = Field(default="https://openrouter.ai/api/v1")
openrouter_model: str = Field(default="google/gemma-3-27b-it:free")

Result

I was able to reproduce the inconsistency described in #73. README.md tells the user to add OPENROUTER_API_KEY to .env, while .env.example does not list OPENROUTER_API_KEY and only mentions mock and openai as LLM_PROVIDER options. core/config.py includes configuration fields for OpenRouter.

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

Partial run of pkg-01: 1/1 scored items.

Full run: 20/20 scored items (PASS).
 

**Package analysis**
 pkg-01: My rubric decided accept, and the gold label was also accept. The package recorded the environment as HTTPie 3.2.4, Python 3.12.4, multidict 6.6.0, and macOS 14.5. The reproduction used an offline command with exactly one custom header, and the output showed that `Content-Type: application/json` was missing. The report also included a control run where the `Content-Type` header appeared correctly. This evidence matched the behavior described in the original issue, and the stated outcome matched the evidence. Because the required checks passed, my rubric returned accept, which agreed with the gold label.
 

**Check rationale**
 
 | behavior | Compare the actual output, error, or other result in the repro report with the behavior described in the original issue. | Pass if the evidence shows the same problem described in the issue. Fail if it shows a different error, output, or behavior and the contributor claims they reproduced the issue. | required |

I used this check because a reproduction should show the same problem described in the original issue, not just a related error or behavior. During calibration, I saw that a report could look complete but still produce a different error from the one described in the issue. I wanted this check to focus on the actual evidence and whether it matches the original issue instead of accepting a report just because the contributor says they reproduced it.
 

**Trade-offs**
 
The behavior check is strict because a report can be rejected even if it finds a related problem when the evidence does not show the specific behavior described in the original issue. I accept that trade-off because finding a different error does not prove that the reported issue was reproduced. My final full eval run matched all 20 scored packages, so this check did not cause a disagreement with the gold labels in that run.
 

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
