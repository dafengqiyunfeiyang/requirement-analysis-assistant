# Workflow

## Purpose

This skill helps a PM turn messy requirement signals into a structured analysis that is useful for judgment, not a substitute for judgment. In v2, it also supports controlled handoff into the PM's current spec workflow once the input is ready enough.

## Core Principle

The skill should answer these questions better than a generic assistant:
- What does this input currently seem to be saying?
- Who is involved, in what scene, and what does the requirement likely mean?
- What key information is still missing before a PM can judge it well?
- Is this ready to move into spec yet?

## Context Rules

### Read context first
- Always start with the current project.
- Prefer existing specs, README files, domain docs, and obvious product artifacts before wider exploration.

### Treat context coverage honestly
- A single-end project is usable.
- A single-end project is not full business truth.
- If the available context only covers one end, say what it covers and what it does not cover.

### If context is insufficient
- State the current context limit.
- Tell the PM what additional context would help most.
- Prefer suggesting the smallest missing context, not "read everything."

## Requirement Decomposition

Before value analysis, explain three things explicitly.

### `用户`
- Who is mainly affected?
- Who benefits if this becomes a real requirement?
- Is the requester the same as the affected user?

### `场景`
- In what business scene does this happen?
- Which step or node of the journey does it belong to?
- What preconditions seem to be required?

### `需求解释`
- What is this input really trying to change?
- What problem does it seem to be solving?
- Do not copy a solution-shaped sentence and call that the requirement.

## Turn-by-Turn Method

### First turn
1. Read the current project.
2. Restate the messy input as a neutral synthesis.
3. Separate problem statements, requests, and solution-shaped expressions.
4. Explain `用户`, `场景`, and `需求解释`.
5. Identify visible user-value signals.
6. Identify visible business-value signals.
7. List the top missing facts and why they matter.
8. Surface conflicts without resolving them.
9. Add evidence only after PM-supplied facts and project material.
10. Surface legal and financial risk hints when relevant.
11. Give a natural-language leaning, not a verdict.

### Later turns
1. Consume the PM's new facts.
2. Compare them with existing project material.
3. Surface any conflicts without resolving them.
4. Update supporting and counter evidence.
5. Update `新增判断`, `待确认信息`, and `已确认信息`.
6. Decide whether AI-retrievable evidence is now useful.
7. Update risk hints if new signals appear.
8. Decide whether spec handoff is now appropriate.

## Value Lens

### User value
- Default user groups are consumers and merchants.
- Make it explicit which side benefits.
- If the value statement is vague, say it is vague.

### Business value
- Do not force a single label.
- One requirement may map to one or more business values.
- Common examples include conversion, repeat purchase, and efficiency.

## Density Rules

The goal is not "shorter writing." The goal is "less repetition and more new signal."

### `新增判断`
- Only include analysis the PM is unlikely to already know.
- Do not repeat project background just to make the answer feel complete.

### `待确认信息`
- Prefer 1 to 3 items.
- Each item should explain why it matters to the next decision.

### `冲突点`
- Only include conflicts that materially affect judgment or spec handoff.
- Label the sources.

### `已确认信息`
- Keep it behind `冲突点`, not at the top.
- Prefer 3 to 5 items.
- Add a light source tag when possible:
  - `PM确认`
  - `项目材料确认`

## Evidence Rules

Use source-aware evidence:
- PM-supplied facts
- current project material
- fixed documentation packs
- external references

Do not blur these together.

## Conflict Rules

If two sources disagree:
- list the disagreement
- label the sources
- ask the PM what should be treated as current truth

Do not pick a side automatically.

## Risk Prompt Rules

Risk prompts are reminders, not judgments.

### Default scope
- legal
- finance

### Allowed output
- possible risk direction
- who the PM should confirm with
- why the current information is still insufficient

### Not allowed
- legal verdicts
- compliance verdicts
- financial feasibility verdicts
- pretending that no risk exists just because no one mentioned one

### When there is no strong signal
- keep it minimal
- a short line such as `暂未识别明显法务/财务风险信号` is enough
- do not force a long risk section just to match the structure

## Spec Handoff Rules

### Auto-ask conditions
Ask whether to enter spec when all of these are true enough:
- the problem definition is basically clear
- user value and business value can be expressed
- scope and non-scope are roughly writable
- the remaining missing facts do not block a first draft

### PM explicit trigger
If the PM explicitly says things like:
- `转 spec`
- `写 spec`
- `可以进 spec`

treat that as direct handoff intent.

### Template upload
After the PM confirms handoff:
- request the current spec template materials
- require at least the active template
- recommend also uploading usage notes and a sample spec

### If the PM has not uploaded the template yet
- stop at the starter pack
- do not invent a spec structure from memory
- tell the PM that drafting continues after the current template is uploaded

### Active source of truth
- Use the uploaded template materials as the active source of truth.
- If they differ from older method-pack wording, the uploaded materials win.

## Spec Starter Pack

Prepare this before spec drafting:
- problem definition
- `用户`
- `场景`
- `需求解释`
- user value / business value
- `已确认信息`
- `待确认信息`
- `冲突点`
- `风险提示`
- why it is ready for spec now

### Product optimization skeleton
When relevant, also prepare:
- current experience problem or opportunity
- optimization target
- optimization scene
- target action or key journey
- expected change
- non-goals
- affected pages / modules / surfaces
- expected observation metrics

## Auto-Drafting Boundary

When the template is uploaded, AI may draft only skeleton-level sections for PM review:
- problem to solve
- facts / inferences / unknowns
- scope / non-scope
- business objects and roles
- goals / non-goals
- main flow skeleton
- state skeleton
- exception skeleton
- manual handling skeleton
- open questions

Do not auto-fill:
- full transition rule tables
- full cross-surface matrices
- full metric definitions
- full rollback detail
- any section where guessing would turn inference into rule

## Stop Conditions

Stop requirement-analysis mode when all of these are true enough for the PM to act:
- the input has been synthesized clearly
- `用户`, `场景`, and `需求解释` are visible enough
- major user-value and business-value signals are visible
- major doubts, counter-evidence, or conflicts are visible
- the next 1 to 3 facts to gather are clear
- whether to hand off into spec is clear

## Common Failure Modes

- Rewriting without analyzing
- Jumping to solutions
- Over-trusting single-end context
- Overusing external references
- Asking too many questions
- Writing confident conclusions from weak evidence
- Repeating too much PM-known background
- Asking to enter spec too early
- Entering spec without the active template materials

## How PMs Should Read The Output

### `新增判断`
- Treat this as the highest-density section.
- It should justify why this output was worth reading.

### `待确认信息`
- Treat this as the most actionable gap list.
- These are the missing facts that most affect judgment or spec handoff.

### `冲突点`
- Treat this as a pause signal.
- The assistant should not continue as if the conflict were settled.

### `已确认信息`
- Treat this as the current fact ledger, not as a full background recap.

### `风险提示`
- Treat this as a coordination prompt.
- It tells the PM who else may need to be involved, not what the final answer is.

### `是否建议转 spec`
- Treat this as workflow guidance.
- It should explain whether the input is mature enough for the next step.
