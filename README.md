<div align="center">

# TestShift AI
### Public Skill Patterns for Agentic QA and Governed Automation

[![GitHub stars](https://img.shields.io/github/stars/nirtal85/testshift-ai?style=social)](https://github.com/nirtal85/testshift-ai/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![AI Skills](https://img.shields.io/badge/AI-Skill_Patterns-8b5cf6)
![Agentic QA](https://img.shields.io/badge/Agentic_QA-Governed-22c55e)
![Test Architecture](https://img.shields.io/badge/Test_Architecture-Quality_Gates-3b82f6)

[Read The Article](https://www.testshift.dev/posts/from-prompts-to-skills-agentic-ai-dev-qa/) • [Browse Skills](skills/bug-scout/SKILL.md) • [Visit TestShift](https://www.testshift.dev)

</div>

---

## About The Project

**TestShift AI** is a public library of sanitized AI Skill patterns for modern Quality Engineering.

The goal is simple: turn agentic AI from loose prompting into governed engineering workflows. These patterns help AI agents investigate failures, collect evidence, classify uncertainty, and produce useful proposals without silently mutating systems or flooding teams with noisy tickets.

This repository starts with **Bug Scout**, a Skill pattern for CI failure investigation and RCA triage.

> Code is cheap. Context is King. Skills are the new currency.

---

## What Is a Skill Pattern?

A **Skill pattern** is a reusable behavioral contract for an AI agent.

It defines:

| Contract Area | What It Controls |
|---|---|
| Evidence | Which artifacts, logs, reports, timestamps, and code changes the agent must inspect |
| Boundaries | What the agent may read, what it may write, and where human approval is required |
| Classification | How to separate product defects, stale automation, flaky infrastructure, and weak signals |
| Output | The exact format of a concise, evidence-backed proposal |
| Governance | Confidence gates, read-only defaults, and explicit approval before write actions |

Prompts ask the model to behave. Skills constrain the system so behavior becomes repeatable.

---

## Available Skills

| Skill | Purpose | Status |
|---|---|---|
| [`bug-scout`](skills/bug-scout/SKILL.md) | Investigate CI and test automation failures, classify the signal, and propose evidence-backed issues only when confidence is high enough. | Available |

---

## Bug Scout

**Bug Scout** turns a red CI signal into a governed RCA proposal.

It is designed for cases where an automation failure may represent a real product defect, but the evidence must be classified before a ticket is opened.

### What It Does

- Extracts failure context from test titles, file paths, reports, traces, screenshots, logs, and CI metadata.
- Classifies the failure as product defect, stale automation, flaky infrastructure, or insufficient evidence.
- Searches recent code changes and historical issues when RCA is requested.
- Ranks suspects by confidence.
- Produces a lean issue proposal with only high-confidence RCA candidates.
- Requires explicit human approval before any write action.

### What It Avoids

- Opening weak tickets.
- Treating correlation as confirmed causation.
- Leaking raw investigator notes into issue bodies.
- Including Medium/Low RCA guesses in final proposals.
- Weakening tests to hide product defects.
- Exposing private repository names, internal Jira projects, production logs, or company-specific workflows.

---

## Governance Model

Bug Scout follows a conservative workflow:

| Stage | Default Behavior |
|---|---|
| Evidence collection | Read-only |
| Failure classification | Required before drafting |
| RCA suspect ranking | High / Medium / Low internally |
| Ticket proposal | High-confidence suspects only |
| Jira/GitHub creation | Human approval required |
| Product fix proposal | Draft/hypothesis only |

This is the difference between agentic assistance and uncontrolled automation.

---

## How To Use

1. Open [`skills/bug-scout/SKILL.md`](skills/bug-scout/SKILL.md).
2. Adapt the placeholders to your own engineering environment.
3. Replace generic references such as `ORG/REPO`, `ISSUE-KEY`, and artifact links with your own safe conventions.
4. Keep sensitive implementation details private.
5. Start with read-only integrations before enabling ticket or pull request creation.

For Codex-style Skill usage, copy the Skill folder into your local skills directory:

```bash
skills/bug-scout/
  SKILL.md
```

Then invoke it when triaging CI failures, flaky automation signals, or automation-found product bugs.

---

## Key Concepts

| Concept | Meaning |
|---|---|
| Agentic QA | AI-assisted quality workflows where agents investigate evidence, not just summarize failures |
| RCA triage | Root Cause Analysis that correlates failure timing, artifacts, historical issues, and recent code changes |
| Quality Gate | A deterministic control point that decides whether evidence is strong enough to proceed |
| Human-in-the-loop | Required approval before creating tickets, changing code, or opening PRs |
| Contextual IP | Organization-specific judgment encoded as reusable agent instructions and guardrails |

---

## Repository Structure

```text
testshift-ai/
  README.md
  LICENSE
  skills/
    bug-scout/
      SKILL.md
```

The repository is intentionally small. Each Skill should stay focused and portable. Extra examples, docs, and eval suites can be added later only when they earn their weight.

---

## Related Reading

This repository implements the ideas discussed in the following TestShift article:

- [Bug Scout: From Prompts to Skills in Agentic QA](https://www.testshift.dev/posts/from-prompts-to-skills-agentic-ai-dev-qa/)

Related TestShift architecture essays:

- [Code is Cheap, Context is King](https://www.testshift.dev/posts/code-is-cheap-context-is-king/)
- [The Rise of Autonomous AI Agents in Playwright](https://www.testshift.dev/posts/the-rise-of-autonomous-ai-agents-in-playwright/)
- [The Real Quality Gate](https://www.testshift.dev/posts/the-real-quality-gate-a-paradigm-shift/)

---

## License

This project is licensed under the [MIT License](LICENSE).

---

<div align="center">

Found this useful?

Star the repo, adapt the pattern, and build safer AI-native quality workflows.

<br />

[Visit TestShift for more architectural insights](https://www.testshift.dev)

</div>
