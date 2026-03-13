# Workflow

## Purpose

This skill helps a PM turn messy requirement signals into a structured analysis that is useful for judgment, not a substitute for judgment.

## Core Principle

The skill should answer two questions better than a generic assistant:
- What does this input currently seem to be saying?
- What key information is still missing before a PM can judge it well?

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

## Turn-by-Turn Method

### First turn
1. Read the current project.
2. Restate the messy input as a neutral synthesis.
3. Separate problem statements, requests, and solution-shaped expressions.
4. Identify visible user-value signals.
5. Identify visible business-value signals.
6. List the top missing facts and why they matter.
7. Ask 1 to 3 high-value follow-up questions.
8. Give a natural-language leaning, not a verdict.

### Later turns
1. Consume the PM's new facts.
2. Compare them with existing project material.
3. Surface any conflicts without resolving them.
4. Update supporting and counter evidence.
5. Decide whether AI-retrievable evidence is now useful.
6. Update the leaning and next step.

## Value Lens

### User value
- Default user groups are consumers and merchants.
- Make it explicit which side benefits.
- If the value statement is vague, say it is vague.

### Business value
- Do not force a single label.
- One requirement may map to one or more business values.
- Common examples include conversion, repeat purchase, and efficiency.

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

## Stop Conditions

Stop when all of these are true enough for the PM to act:
- the input has been synthesized clearly
- major user-value and business-value signals are visible
- major doubts, counter-evidence, or conflicts are visible
- the next 1 to 3 facts to gather are clear

## Common Failure Modes

- Rewriting without analyzing
- Jumping to solutions
- Over-trusting single-end context
- Overusing external references
- Asking too many questions
- Writing confident conclusions from weak evidence

## How PMs Should Read The Output

### `待补信息`
- Treat this as the highest-value part of the output.
- These are the missing facts that most affect judgment.

### `冲突点`
- Treat this as a pause signal.
- The assistant should not continue as if the conflict were settled.

### `建议性倾向`
- Treat this as a direction, not a decision.
- It should explain the current lean and its uncertainty.
