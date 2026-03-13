# Requirement Analysis Assistant

A project-grounded Codex skill for product managers that turns messy requirement signals into structured analysis before spec writing or solutioning.

It helps PMs:
- read the current project context first
- organize messy requirement inputs without upgrading them too early
- surface user value, business value, missing information, and conflicts
- give suggestion-oriented guidance instead of final decisions

## Best For

Use this skill when:
- the input is messy, incomplete, or inconsistent
- you are not sure whether something is a real requirement yet
- project context matters
- you want to know what to verify next before writing a spec

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
Please use $requirement-analysis-assistant, read the current project first, and help me analyze this messy requirement input.
```

Recommended Chinese invocation:

```text
请使用 $requirement-analysis-assistant，先读取当前 project 的已有材料，再帮我梳理下面这条散乱需求输入。
```

## What The Output Looks Like

The skill is designed to surface:
- current understanding
- user value
- business value
- supporting evidence
- counter-evidence or doubts
- missing information
- conflicts
- suggestion-oriented next steps

It should not jump straight to:
- solution proposals
- spec writing
- PRD generation
- final requirement decisions

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

## Notes

- This repository is meant for direct skill installation, not as a full product application.
- The skill works best when used inside a relevant project with local context available.
