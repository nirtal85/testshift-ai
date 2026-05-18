# Bug Scout

Bug Scout is a public, sanitized Skill pattern for turning CI and test automation failures into governed RCA proposals.

It is not a workplace-specific implementation. It is a reusable pattern for teams that want AI agents to investigate failures without creating noisy tickets or hiding real product defects.

## Purpose

Bug Scout helps an AI agent answer one question:

> Is this automation failure likely a product defect, stale automation, flaky infrastructure, or insufficient evidence?

Only after classification should the agent draft an issue proposal.

## Core Flow

| Step | Action | Governance Rule |
|---|---|---|
| 1 | Collect evidence from CI, traces, reports, logs, and failure text | Read-only by default |
| 2 | Classify the failure signal | Product defect / stale automation / flaky infrastructure / insufficient evidence |
| 3 | Search recent code changes and similar historical issues | Treat correlation as suspicion, not proof |
| 4 | Rank RCA candidates | Keep Medium/Low internally |
| 5 | Draft a lean issue proposal | Include High-confidence suspects only |
| 6 | Ask for approval | No ticket or PR without human confirmation |

## What It Produces

Bug Scout produces a concise issue proposal with:

- product-facing summary
- environment and artifact link
- reproduction steps
- failing test names
- first-fail time when available
- high-confidence RCA candidates
- missing data checklist kept outside the final ticket body

## What It Prevents

Bug Scout is designed to prevent common agentic QA failure modes:

- polished but wrong bug reports
- speculative RCA presented as certainty
- flakiness misclassified as product failure
- test rewrites that hide product defects
- long Jira bodies full of raw investigator notes
- write actions without approval

## Skill Contract

The executable agent-facing contract is here:

[`SKILL.md`](SKILL.md)

Use that file when installing or adapting the Skill. This README is only the human guide.

## Related Article

[Bug Scout: From Prompts to Skills in Agentic QA](https://www.test-shift.com/posts/from-prompts-to-skills-agentic-ai-dev-qa/)
