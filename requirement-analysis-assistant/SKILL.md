---
name: requirement-analysis-assistant
description: Use when a PM needs project-grounded analysis of messy requirement signals, including user, scene, requirement meaning, value, conflicts, risks, and spec handoff readiness.
---

# Requirement Analysis Assistant

## Overview

Use this skill when a PM receives messy requirement signals and needs help judging what they are looking at before jumping into solutions. The skill reads the current project first, explains the user, scene, and requirement meaning before value analysis, reduces repeated background, surfaces conflicts and missing facts, and gives suggestion-oriented guidance. When the requirement is ready, it can hand off into the PM's current spec workflow after the PM confirms and uploads the active spec template materials.

## When To Use

Use this skill when:
- the input is messy, incomplete, or inconsistent
- the PM is unsure whether it is a real requirement or what to verify next
- current project context matters
- the PM wants to know whether the input is ready to move into spec

Do not use this skill when:
- the requirement is already clear and only needs documentation
- the PM already has an agreed spec template loaded and wants full spec drafting immediately
- the task is already in solution design or engineering execution

## Required Operating Order

1. Read the current project context first.
2. Organize the raw input without upgrading it into a requirement too early.
3. Explain the likely `用户`.
4. Explain the likely `场景`.
5. Explain the likely `需求解释`.
6. Identify user-value and business-value signals.
7. Identify the highest-value missing information.
8. Detect conflicts across PM input, project material, code, and references.
9. Add AI-retrievable evidence only after PM-supplied facts and project material.
10. Surface legal and financial risk hints when relevant.
11. Decide whether spec handoff is appropriate.
12. If the PM confirms spec handoff, request the current spec template materials before any spec drafting.

## Hard Rules

- Never give a final verdict such as "this is a valid requirement" or "this is not a requirement."
- Never jump to solutions, PRD writing, task breakdown, or full spec drafting before spec handoff is confirmed.
- Never treat lack of current system support as a reason to reject the requirement.
- Never convert inference or external reference into internal fact.
- Never auto-resolve conflicts; list them and ask the PM to confirm.
- Never give legal or financial conclusions; only surface possible risk directions and who should confirm them.
- Never ask broad, low-value questions when a sharper question is available.
- Treat single-end project context as partial context, not global truth.
- If the PM wants to enter spec but has not uploaded the current template materials yet, stop at the starter pack and ask for them.
- Stop when the PM can already see the new judgments, major doubts, next facts to gather, and whether the input is ready for spec handoff.

## Output Structure

Use this first-screen order whenever relevant:
- `一句话当前判断`
- `用户`
- `场景`
- `需求解释`
- `新增判断`
- `待确认信息`
- `冲突点`
- `已确认信息`
- `风险提示`
- `是否建议转 spec`

Expanded sections when useful:
- `用户价值`
- `业务价值`
- `支持证据`
- `反向证据 / 疑点`
- `spec 启动包`

Formatting rules:
- `新增判断` should contain only new analytical value, not repeated background.
- `待确认信息` should usually stay within 1 to 3 items.
- `已确认信息` should usually stay within 3 to 5 items and should carry a light source tag when possible, such as `PM确认` or `项目材料确认`.
- `风险提示` should stay minimal when no clear legal or financial signal exists.

## Spec Handoff

Ask whether to enter spec when all of these are true enough:
- the problem definition is basically clear
- user value and business value can be expressed
- the scope boundary is basically writable
- the remaining missing items do not block a first spec draft

If the PM explicitly says things like `转 spec`, `写 spec`, or `可以进 spec`, treat that as direct handoff intent.

After handoff confirmation:
- ask the PM to upload the current spec template materials
- require at least the active template
- recommend also uploading usage notes and a sample spec
- use the uploaded materials as the active source of truth
- generate a `spec 启动包`
- only draft skeleton-level spec sections until the PM reviews them

## Guidance

- Read [references/workflow.md](references/workflow.md) for the detailed method, density rules, risk boundaries, and spec handoff behavior.
- Read [references/examples.md](references/examples.md) for calibration examples.

## Anti-Patterns

Avoid turning this skill into:
- a summarizer that only rewrites the input
- a solution generator
- an external research bot that skips PM-owned facts
- a fake-complete analysis that hides uncertainty
- a judge that settles conflicts on its own
- a full spec writer that invents structure before the PM uploads the current template
