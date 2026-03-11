---
name: review-plan-by-codex
description: Review a Claude Code plan file using Codex. Usage: /review-plan-by-codex <path-to-plan.md>
---

Use the Agent tool to spawn a general-purpose sub-agent with the following prompt: "Run this cli command (using codex as our reviewer) to review the plan file: `codex -m gpt-5.4 -c model_reasoning_effort=\"xhigh\" exec \"Review this Claude Code implementation plan and provide feedback on correctness, completeness, and potential issues. Append ONLY new findings as a new section at the end of the plan file with the heading '## Codex findings:'. Do NOT modify, rewrite, or reorder any existing content in the file. If a finding duplicates something already covered in the plan, skip it. Only add genuinely new insights. The plan file path is: $ARGUMENTS\"`. Do it with Bash tool. Make sure if there's a timeout to be at least 1 hour. Return the full review output."

After the sub-agent completes, tell the user: "Codex findings have been appended to the plan file. To kick off implementation with fresh context, run: /plan $ARGUMENTS"
