&#x20;# Plan for Issue #73



\## Diagnosis



The issue is that the README and `.env.example` are giving different instructions for the LLM setup.



The README tells the user to add an `OPENROUTER\_API\_KEY` to the `.env` file. But when I checked `.env.example`, it only shows `mock` and `openai` as the options and only has an `OPENAI\_API\_KEY`.



I also checked `core/config.py` and it already has settings for `openrouter\_api\_key`, `openrouter\_base\_url`, and `openrouter\_model`. Based on that, I think the main problem is that the setup instructions are not consistent with each other.



\## Reproduction evidence



In the README I found:



> Configure environment (add your OPENROUTER\_API\_KEY to .env)



But `.env.example` says:



> Options: "mock" (default, no API key needed), "openai"



It also only includes:



> OPENAI\_API\_KEY=sk-your-key-here



Then in `core/config.py` I found:



> openrouter\_api\_key: str = Field(default="")



There are also settings for the OpenRouter base URL and model.



\## Scope



I want to keep this change small and only fix the setup instructions that are causing the confusion.



The main files I expect to work with are:



\- `README.md`

\- `.env.example`



I do not plan on changing the actual LLM code or anything unrelated to this issue.



 



## Approach
 

1. Update `.env.example` to include an `OPENROUTER_API_KEY` placeholder because the README tells users to provide that key and `core/config.py` has a matching `openrouter_api_key` setting.
2. Do not add `openrouter` to the `LLM_PROVIDER` options unless I can confirm from the implementation that it is actually a supported provider value.
3. Keep the existing `LLM_PROVIDER=mock` default and the existing OpenAI configuration.
4. Review the README and `.env.example` together and make the smallest change needed so they no longer give conflicting setup instructions.
5. Review the final diff and make sure I did not change unrelated files or application behavior.
 

\## Test plan



1\. Compare the README and `.env.example` after my changes and make sure they no longer give different LLM setup instructions.

2\. Make sure the OpenRouter environment variable matches the name used in `core/config.py`.

3\. Copy `.env.example` to a temporary `.env` and check that the default `mock` setup can still be used without an API key.

4\. Check the final diff to make sure I only changed files related to this issue.



 




## Risks and unknowns

I confirmed that `core/config.py` contains OpenRouter settings, including `openrouter_api_key`, but my reproduction does not show whether `openrouter` is a valid value for `LLM_PROVIDER` or where that provider value is handled.

Because of that, I will not document `openrouter` as an `LLM_PROVIDER` option unless I can verify it from the implementation. I also do not know whether OpenRouter or OpenAI is supposed to be the preferred provider, so I will avoid changing that behavior and keep the fix focused on the setup mismatch I reproduced.

If I find evidence during implementation that changes this plan, I will record it under Deviations.
 

 ## Deviations

I did not have any major deviations from my plan. I kept the change focused on `.env.example` and added the missing `OPENROUTER_API_KEY` placeholder. I did not add `openrouter` as an `LLM_PROVIDER` option because I could not verify from the implementation that it is a supported provider value.



