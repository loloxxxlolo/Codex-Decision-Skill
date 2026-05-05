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

## Examples

The following examples are anonymized from real workflows. They keep the decision structure but remove personal identity, exact locations, accounts, income details, and private relationships.

### Example 1: Publishing a Codex skill

User question:

```text
I built a Codex skill. Should I publish it to GitHub, or will it become extra work?
```

The skill should recover context first:

- The current phase should not turn new projects into high-pressure work.
- The skill already has a minimal working loop.
- The main value of publishing is clarification, reuse, and public proof of work, not immediate traffic.

Suggested answer:

```text
Publish it, but only as a v0.1 minimal public version.
Limit the scope to README files, SKILL files, templates, and a few examples.
Do not build a website, video course, complex installer, or open-source operation plan yet.
```

Possible memory write-back:

```md
- The decision skill can be published to GitHub as a v0.1 minimal public version.
- The goal is clarification, reuse, and public proof of work, not full open-source operations.
```

### Example 2: Adding summaries to a mobile recording app

User question:

```text
My recording app can already capture daily life manually. Should I add a summary feature next?
```

The skill should recover context first:

- The core of a recording app is fast capture.
- The basic recording loop already works.
- It is too early to build a complex cloud aggregation system.

Suggested answer:

```text
Add summaries, but start with gentle life summaries and weekly/monthly reviews.
Do not start with complex reports, annual summaries, or cloud aggregation.
```

Possible decision criteria:

```md
Upgrade:
- The feature turns existing records into gentle life summaries.
- The feature improves review value, such as weekly/monthly reviews or favorites.

Pause:
- The feature slows down capture.
- The local recording loop is not stable enough for complex AI aggregation.
```

### Example 3: Paid promotion for a content project

User question:

```text
A niche content account is just starting. Should I run paid promotion? How much should I spend, and what should I measure?
```

The skill should recover context first:

- The account is still in early validation.
- The user should not act like an investor or boss too early.
- Content direction and collaboration stability need to be validated first.

Suggested answer:

```text
Run a small test, but the goal is not to buy views.
Use paid promotion to validate topics and real demand.
Look at saves, comments, messages, and conversion signals, not only impressions.
```

Possible decision criteria:

```md
Continue:
- Small paid tests produce real demand signals.
- 1-2 topics are clearly worth further testing.

Do not upgrade spending:
- Do not increase budget before validating stable topics.
- Do not increase responsibility before validating stable collaboration.
```

### Example 4: Long travel versus life rhythm

User question:

```text
Should I keep working for a few more months to build a buffer, or start long-term travel now?
```

The skill should recover context first:

- The current phase is about building buffer and recovering life rhythm.
- Long travel should not become a way to avoid real decisions.
- Short trips can be used as a transition.

Suggested answer:

```text
Keep the work-and-recovery rhythm for now.
Short trips are fine, but start long travel only when cash, energy, and handover are all under control.
```

Possible decision criteria:

```md
Continue long travel:
- Cash, life rhythm, and handover are all under control.

Downgrade to short or segmented trips:
- Energy is average, but the user still wants some travel experience.

Pause travel:
- Budget is not enough, or travel is becoming a way to avoid real problems.
```

## v0.1 Scope

The first version only aims to close one loop:

> When the same issue appears for the second time, the assistant should not treat it like a brand-new topic.

Automation, sync, UI, and cloud aggregation can come later.
