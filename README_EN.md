# Codex Decision Skill

A lightweight decision-memory skill for Codex or AI assistants.

It is not meant to be a universal life database. Its purpose is to help the assistant recover previous conclusions before discussing recurring decisions, so the same issue does not restart from zero every time.

## What It Helps With

- Recurring direction choices.
- Project continue / pause / stop decisions.
- Losing previous conclusions between conversations.
- AI answers that ignore historical context.
- Decision discussions that never get written back into memory.

## What It Does Not Do

- It does not store every conversation.
- It is not a full life-memory system.
- It is not for ordinary technical debugging.
- It is not for one-off fact lookup.
- It should not invent plans, risks, or tasks without user confirmation.
- It does not require cloud sync or a complex knowledge base.

## Core Workflow

1. Decide whether the question continues a historical decision topic.
2. Read short-term memory first.
3. Read only the relevant long-term project memory.
4. Review existing conclusions before answering the current question.
5. If a stable conclusion is confirmed, write it back in compressed form.

## Recommended Structure

```text
memory/
  short-term-memory.md
  long-term-memory/
    decision-board.md
    project-index.md
    projects/
      travel-plan.md
      side-project.md
      career-plan.md
```

## Key Principles

- Store stable conclusions, not every emotion or thought.
- AI suggestions should be written to long-term memory only after user confirmation.
- Each project should have decision criteria: continue, pause, upgrade, stop.
- The decision board should keep only the current top priorities.
- Do not expand low-value sections just to complete a template.

## Files

- `SKILL.md`: the main Codex skill file.
- `SKILL.zh-CN.md`: simplified Chinese version of the skill.
- `README.md`: Chinese README.
- `templates/`: memory templates.
- `examples/`: practical examples.

## Recommended Repository Name

```text
codex-decision-skill
```

## Quick Start

### 1. Install the skill

Copy `SKILL.md` into your Codex skills directory.

If you mainly use Chinese, copy `SKILL.zh-CN.md` and rename it to `SKILL.md`.

Example path:

```text
~/.codex/skills/decision-skill/SKILL.md
```

Windows example:

```text
C:\Users\<your-name>\.codex\skills\decision-skill\SKILL.md
```

### 2. Create memory files in your workspace

Copy the templates into your workspace:

```text
memory/
  short-term-memory.md
  long-term-memory/
    decision-board.md
    projects/
      your-project.md
```

### 3. Use it in Codex

Example prompts:

```text
Use decision-skill to help me decide whether to continue this project.
```

```text
Use decision-skill and write this conclusion into long-term memory.
```

### 4. Recommended usage

- Keep short-term memory small.
- Keep the decision board focused on the current top priorities.
- Use one file per long-term project.
- Write back only stable conclusions, not full chat logs.

## v0.1 Scope

The first version only aims to close one loop:

> When the same issue appears for the second time, the assistant should not treat it like a brand-new topic.

Automation, sync, UI, and cloud aggregation can come later.
