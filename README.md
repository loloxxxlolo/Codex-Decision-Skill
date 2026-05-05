# Codex Decision Skill

一个用于 Codex / AI 助手的轻量决策记忆 skill。

它的目标不是做万能人生数据库，而是在反复出现的决策问题里，让 AI 先恢复已有结论，再继续当前讨论，避免每次都从零开始。

## 解决什么问题

- 方向选择反复纠结。
- 项目是否继续、暂停、放弃没有标准。
- 上次已经聊过的结论，下次又被当成新问题。
- AI 只回答当前问题，不承接历史上下文。
- 决策讨论结束后，没有稳定写回记忆。

## 不解决什么问题

- 不做全量人生记忆。
- 不存所有聊天全文。
- 不用于普通技术排错。
- 不用于一次性事实查询。
- 不替用户脑补计划、风险或待办。
- 不追求复杂知识库或云端同步。

## 核心流程

1. 判断问题是否属于历史决策主题。
2. 先读取短期记忆。
3. 只读取相关长期项目记忆。
4. 先回顾已有结论，再回答当前问题。
5. 如果形成稳定结论，再压缩写回记忆。

## 推荐目录结构

```text
记忆/
  短期记忆.md
  长期记忆/
    当前决策看板.md
    项目列表.md
    项目列表/
      travel_plan.md
      side_project.md
      career_plan.md
```

如果你不想使用中文目录，也可以改成：

```text
memory/
  short-term-memory.md
  long-term-memory/
    decision-board.md
    project-index.md
    projects/
```

## 关键原则

- 只记录稳定结论，不记录每次情绪波动。
- AI 的建议只有在用户确认后才写入长期记忆。
- 每个项目最好有判断标准：继续、暂缓、升级、放弃。
- 当前决策看板只保留当前最重要的几件事。
- 不要为了模板完整而扩写低价值内容。

## 建议仓库名

```text
codex-decision-skill
```

## 文件说明

- `SKILL.md`：Codex skill 主文件。
- `SKILL.zh-CN.md`：中文精简版 skill 文件。
- `README_EN.md`：英文说明。
- `templates/`：短期记忆、长期项目、当前决策看板模板。
- `examples/`：旅行决策、项目取舍、记忆写回案例。

## 使用方式

## 快速开始

### 1. 安装 skill

如果你主要用英文或想用更通用版本，复制 `SKILL.md` 到你的 Codex skill 目录。

如果你主要用中文，建议复制 `SKILL.zh-CN.md`，并重命名为 `SKILL.md`：

```text
~/.codex/skills/decision-skill/SKILL.md
```

Windows 示例：

```text
C:\Users\<your-name>\.codex\skills\decision-skill\SKILL.md
```

### 2. 在你的项目工作区创建记忆目录

复制 `templates/` 里的模板，得到类似结构：

```text
记忆/
  短期记忆.md
  长期记忆/
    当前决策看板.md
    项目列表/
      your_project.md
```

如果你更喜欢英文目录，也可以用：

```text
memory/
  short-term-memory.md
  long-term-memory/
    decision-board.md
    projects/
      your-project.md
```

### 3. 开始使用

在 Codex 里提问时，可以直接说：

```text
使用 decision-skill，帮我判断这个项目要不要继续。
```

或：

```text
使用 decision-skill，把这次结论写入长期记忆。
```

### 4. 推荐使用方式

- 先维护 `短期记忆.md`，保存最近关注点。
- 再维护 `当前决策看板.md`，保存当前最重要的 1~3 件事。
- 每个长期项目单独一个 `.md` 文件。
- 每次只更新稳定结论，不保存完整聊天记录。

## 示例

你可以先看：

- `examples/travel-decision.md`
- `examples/project-decision.md`
- `examples/memory-update.md`

## v0.1 边界

这个版本只追求一个最小闭环：

> 同一个问题第二次出现时，不要像第一次见到一样回答。

后续再考虑自动化、同步、图形界面或云端汇总。
