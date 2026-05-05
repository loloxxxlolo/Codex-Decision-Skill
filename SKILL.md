---
name: decision-skill
description: Use this skill for recurring decision topics, direction choices, tradeoff ranking, next-step decisions, and lightweight decision-memory updates. It reads short-term memory first, then relevant long-term project memory, reviews existing conclusions, answers the current question, and writes back confirmed stable conclusions when needed. Do not use it for ordinary debugging, one-off fact lookup, rewriting, translation, or unrelated casual chat.
---

# Decision Memory Loop

This skill does one thing:

> In recurring decision topics, recover existing conclusions, avoid repeated hesitation, and write confirmed stable conclusions back into memory.

It is not a full life-memory system, emotional diary, or complex weekly reporting framework.

## Core Workflow

1. Decide whether the current question continues a historical decision topic.
2. Read short-term memory first.
3. Identify the relevant long-term project memory.
4. Review existing conclusions before answering.
5. If the user confirms a stable conclusion, update memory.

## Memory Location

Default memory root:

```text
记忆/
```

Fallback memory root:

```text
memory/
```

Default files:

```text
记忆/
  短期记忆.md
  长期记忆/
    当前决策看板.md
    项目列表.md
    项目列表/
```

English alternative:

```text
memory/
  short-term-memory.md
  long-term-memory/
    decision-board.md
    project-index.md
    projects/
```

## Read Order

1. Read short-term memory.
2. Read the current decision board if it exists.
3. Read only the relevant project memory.
4. Do not load every long-term memory file by default.

## When To Trigger

Use this skill for:

- Recurring decision topics.
- Direction choices.
- Project continue / pause / stop decisions.
- Tradeoff ranking.
- Current priorities and next-step questions.
- Requests to record stable conclusions.

Do not use this skill for:

- Ordinary technical debugging.
- One-off fact lookup.
- Translation, rewriting, or polishing.
- Casual chat unrelated to a historical decision.

## Output Pattern

Default response shape:

```md
## Existing Context

Briefly recover relevant previous conclusions and open issues.

## Current Answer

Give the current judgment, reason, cost, and next step.

## Memory Update

Say whether memory should be created, updated, or left unchanged.
```

For short answers, keep the structure implicit and concise.

## Write-Back Rules

Only write to memory when the content is:

- stated by the user,
- confirmed by the user,
- or clearly formed as a stable conclusion in the current discussion.

Do not write:

- temporary emotions,
- casual chat,
- unconfirmed AI suggestions,
- invented plans,
- invented risks,
- low-value details added only to complete a template.

When the user says things like "ok, let's do this", "就先这样", or "先按这个", treat the current stable conclusion as confirmed, but still write only the confirmed content.

## Long-Term Project Memory

Recommended sections:

```md
# Project Name

## summary

## status

## plan

## decision criteria

## question

## warning

## todo

## log

## note
```

Do not fill empty sections with invented content.

## Decision Board

The decision board should answer:

- What are the current top priorities?
- What conclusions are already settled?
- What should not be discussed repeatedly for now?
- What are the next review points?

Keep it short.

## Principle

The first version should optimize for one outcome:

> When the same problem appears again, the assistant should not answer as if seeing it for the first time.
