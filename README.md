# TestShift AI

Public, sanitized AI patterns for agentic QA, governed automation, RCA triage, and quality engineering workflows.

This repository contains reusable Skill patterns inspired by the TestShift philosophy:

- Code is cheap. Context is King.
- Prompts are conversations. Skills are governed contracts.
- AI can reason. Deterministic gates must still decide.

## Skills

| Skill | Purpose |
|---|---|
| [`bug-scout`](skills/bug-scout/SKILL.md) | Investigate CI and test automation failures, classify the signal, and propose evidence-backed issues only when confidence is high enough. |

## Principles

These patterns are intentionally generic. They do not include private repository names, internal Jira projects, proprietary domain vocabulary, production logs, or company-specific workflows.

Each Skill should:

- collect evidence before producing conclusions
- classify uncertainty explicitly
- prefer read-only investigation by default
- require human approval before write actions
- suppress noisy Medium/Low RCA claims from final tickets
- avoid weakening tests to hide product defects

## Related Reading

Read the article: [Bug Scout: From Prompts to Skills in Agentic QA](https://www.testshift.dev/posts/from-prompts-to-skills-agentic-ai-dev-qa/)
