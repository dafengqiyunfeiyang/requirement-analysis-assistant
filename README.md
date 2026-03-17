# Requirement Analysis Assistant

A project-grounded Codex skill for product managers that turns messy requirement signals into structured analysis before solutioning, and supports controlled handoff into spec when the input is ready.

## Latest Update

The repository now contains the v2 version of the skill.

- Update notes: [UPDATE-2026-03-17-v2.md](./UPDATE-2026-03-17-v2.md)
- Main additions in v2:
  - explain `user`, `scene`, and `requirement meaning` before value analysis
  - reduce repeated background and prioritize new judgment
  - add bounded legal/finance risk prompts
  - support spec handoff after PM confirmation
  - require the active spec template materials before any spec drafting

It helps PMs:
- read the current project context first
- organize messy requirement inputs without upgrading them too early
- explain user, scene, and requirement meaning before value analysis
- surface user value, business value, missing information, conflicts, and risk hints
- give suggestion-oriented guidance instead of final decisions
- hand off into spec in a controlled way after PM confirmation

## Best For

Use this skill when:
- the input is messy, incomplete, or inconsistent
- you are not sure whether something is a real requirement yet
- project context matters
- you want to know what to verify next before writing a spec
- you want help deciding whether the input is ready for spec handoff

Do not use it when:
- the requirement is already clear and only needs documentation
- you already want a full PRD, spec, or implementation plan
- you are already in solution design or engineering execution

## Install

Install from GitHub with Codex's built-in installer:

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo dafengqiyunfeiyang/requirement-analysis-assistant \
  --path requirement-analysis-assistant
```

Then restart Codex.

For manual installation or more install options, see [INSTALL-CODEX.md](./INSTALL-CODEX.md).

## How To Invoke

The formal skill name is:

```text
requirement-analysis-assistant
```

Recommended explicit invocation:

```text
Please use $requirement-analysis-assistant, read the current project first, explain the user, scene, and requirement meaning, and help me judge whether this messy input is ready for spec handoff.
```

Recommended Chinese invocation:

```text
请使用 $requirement-analysis-assistant，先读取当前 project 的已有材料，先解释用户、场景和需求含义，再帮我判断这条散乱输入是否具备转 spec 的基础。
```

## What The Output Looks Like

The skill is designed to surface:
- one-line current judgment
- user
- scene
- requirement meaning
- new judgment
- missing information
- conflicts
- confirmed information
- legal/finance risk hints when relevant
- user value
- business value
- supporting evidence
- counter-evidence or doubts
- suggestion-oriented next steps
- whether spec handoff is recommended

It should not jump straight to:
- solution proposals
- PRD generation
- final requirement decisions

When spec handoff is confirmed, it should ask the PM to upload the active spec template materials before drafting any skeleton-level spec content.

## Repository Contents

- `requirement-analysis-assistant/`
  The installable Codex skill
- `requirement-analysis-assistant/SKILL.md`
  Core behavior and constraints
- `requirement-analysis-assistant/references/workflow.md`
  Operating workflow, stop conditions, and failure modes
- `requirement-analysis-assistant/references/examples.md`
  Example inputs and outputs
- `requirement-analysis-assistant/agents/openai.yaml`
  UI metadata
- `INSTALL-CODEX.md`
  Installation guide
- `PUBLISH-TO-GITHUB.md`
  Publishing guide
- `UPDATE-2026-03-17-v2.md`
  v2 update notes and rollout guidance

## Notes

- This repository is meant for direct skill installation, not as a full product application.
- The skill works best when used inside a relevant project with local context available.
