# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

**GitHub username**
 Noah-Mengesha

**Plan comment**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/73#issuecomment-5988625260

I looked into the setup mismatch from my reproduction. The README tells users to add `OPENROUTER_API_KEY`, while `.env.example` only includes `OPENAI_API_KEY`.

I plan to keep the change focused on the setup files. I'll update `.env.example` to include an `OPENROUTER_API_KEY` placeholder so it matches the key referenced in the README and the setting in `core/config.py`. I'll also review the README and `.env.example` together and make the smallest change needed so the setup instructions are consistent.

I found OpenRouter settings in `core/config.py`, but I have not confirmed that `openrouter` is a supported value for `LLM_PROVIDER`, so I won't document it as a provider option unless I can verify that from the implementation.

---

## Your branch

**Branch**

 docs/73-align-llm-env-docs

**Evidence**

 Before

Command:
Get-Content README.md | Select-String "OPENROUTER|LLM_PROVIDER"

Output:
# Configure environment (add your OPENROUTER_API_KEY to .env)

Command:
Get-Content .env.example | Select-String "OPENROUTER|OPENAI|LLM_PROVIDER"

Output:
# Options: "mock" (default, no API key needed), "openai"
LLM_PROVIDER=mock
OPENAI_API_KEY=sk-your-key-here

Command:
Get-Content core/config.py | Select-String "OPENROUTER|OPENAI|LLM_PROVIDER"

Output:
llm_provider: str = Field(default="mock")
openai_api_key: str = Field(default="")
openrouter_api_key: str = Field(default="")
openrouter_base_url: str = Field(default="https://openrouter.ai/api/v1")
openrouter_model: str = Field(default="google/gemma-3-27b-it:free")

Before the change, README.md told users to add OPENROUTER_API_KEY, but .env.example did not include that key.

After

Command:
Get-Content README.md | Select-String "OPENROUTER|LLM_PROVIDER"

Output:
# Configure environment (add your OPENROUTER_API_KEY to .env)

Command:
Get-Content .env.example | Select-String "OPENROUTER|OPENAI|LLM_PROVIDER"

Output:
# Options: "mock" (default, no API key needed), "openai"
LLM_PROVIDER=mock
OPENAI_API_KEY=sk-your-key-here
OPENROUTER_API_KEY=your-openrouter-key-here

Command:
Get-Content core/config.py | Select-String "OPENROUTER|OPENAI|LLM_PROVIDER"

Output:
llm_provider: str = Field(default="mock")
openai_api_key: str = Field(default="")
openrouter_api_key: str = Field(default="")
openrouter_base_url: str = Field(default="https://openrouter.ai/api/v1")
openrouter_model: str = Field(default="google/gemma-3-27b-it:free")

After the change, .env.example includes the OPENROUTER_API_KEY placeholder referenced by README.md and supported by the configuration. I kept the existing LLM_PROVIDER options unchanged because I did not verify that openrouter is a supported provider value.

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

 19/20

**Package analysis**

 pkg-20 was a thread-convention package. The gold label was reject, but my rubric decided accept. This was the only scored package where my result did not match the gold label. My thread-conventions check looks for conflicts with relevant maintainer guidance and repository requirements, but in this case it was not strict enough to catch the problem in pkg-20.

**Check rationale**

 | thread-conventions | Compare the plan comment with the thread highlights and Repo facts. | Pass if the plan follows relevant maintainer guidance and repository requirements. Fail if it ignores or conflicts with guidance or requirements that matter to the proposed change. | required |

I wrote this check so the plan is not judged only by whether the technical approach sounds reasonable. It also has to follow guidance from the issue thread and requirements from the repository. I kept it as a required check because ignoring relevant maintainer guidance can make a plan unacceptable even if the implementation itself looks reasonable.

**Trade-offs**

 My thread-conventions check still missed pkg-20. The final evaluation accepted that package even though the gold label was reject. Making this check much stricter could catch cases like pkg-20, but it could also reject good plans when the thread guidance is vague or not relevant to the proposed change. I kept the check focused on guidance and requirements that actually matter to the proposed work. The final result was 19/20, with every other scored package matching the gold label.

---

Related paths: `plan.md` and `eval-run.txt` in this directory; your skill's files in
`tools/plan-check/`.
