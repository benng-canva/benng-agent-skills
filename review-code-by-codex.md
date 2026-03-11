---
name: review-code-by-codex
description: Review dirty code changes. When user say to "review" or "review changes" or "review dirty code"
---

All dirty repo changes are likely made in this session, though not always

if you are Codex, just review the dirty code and ignore the rest in this skill. If you are not Codex, continue:

Do not modify anything unless I tell you to. Use the Agent tool to spawn a general-purpose sub-agent with the following prompt: "Do not modify anything unless I tell you to. Run this cli command (using codex as our reviewer) passing in the original prompt to review the changes: `codex -m gpt-5.3-codex -c model_reasoning_effort=\"xhigh\" exec \"Do not modify anything unless I tell you to. Review the dirty repo changes which are to implement: $ARGUMENTS. If a plan file path is mentioned, read it first for full context.\"`. Do it with Bash tool. Make sure if there's a timeout to be at least 1 hour. Return the full review output."

If $ARGUMENTS contains a file path to a plan, include it in the prompt so the reviewer can read the plan and compare the implementation against it.
