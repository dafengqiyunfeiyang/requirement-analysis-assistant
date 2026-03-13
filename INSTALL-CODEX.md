# 如何给自己安装这个 skill

## 方式一：手动安装

适合直接从同事那里拿到这个发布包的情况。

### 步骤

1. 解压这个发布包
2. 找到里面的 `requirement-analysis-assistant/` 文件夹
3. 把这个文件夹复制到你的 Codex skills 目录：

```bash
mkdir -p ~/.codex/skills
cp -R requirement-analysis-assistant ~/.codex/skills/
```

4. 重启 Codex

### 安装完成后你应该看到

下面这些文件位于：

```text
~/.codex/skills/requirement-analysis-assistant/
```

包括：

```text
SKILL.md
agents/openai.yaml
references/workflow.md
references/examples.md
```

## 方式二：用 Codex 自带安装脚本从 GitHub 安装

适合 skill 已经上传到 GitHub 的情况。

### 场景 A：GitHub 仓库根目录直接放 skill 文件夹

如果你的仓库结构是：

```text
your-repo/
  requirement-analysis-assistant/
```

安装命令：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo <owner>/<repo> \
  --path requirement-analysis-assistant
```

### 场景 B：GitHub 仓库里用 skills 目录统一管理

如果你的仓库结构是：

```text
your-repo/
  skills/
    requirement-analysis-assistant/
```

安装命令：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo <owner>/<repo> \
  --path skills/requirement-analysis-assistant
```

### 如果你要从 GitHub URL 安装

也可以用 URL：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --url https://github.com/<owner>/<repo>/tree/main/skills/requirement-analysis-assistant
```

或：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --url https://github.com/<owner>/<repo>/tree/main/requirement-analysis-assistant
```

### 注意

- 如果目标目录已存在，安装脚本会中止，不会覆盖已有 skill
- 安装完成后，需要重启 Codex
- 公有仓库可直接下载
- 私有仓库需要本机已有 GitHub 访问权限

## 怎么调用这个 skill

你可以在 Codex 里直接说：

```text
Use $requirement-analysis-assistant to read the current project first, then help me analyze this messy requirement input.
```

也可以直接用中文描述任务，只要任务特征明显，Codex 也可能自动触发。

## 推荐的首条使用方式

```text
请作为需求判断助手，先基于当前 project 的已有材料理解业务上下文，再帮我梳理下面这条输入。

这次不要直接给方案、不要写 spec、不要替我下结论。
请优先做这几件事：
1. 梳理这条输入当前在说什么
2. 识别可能相关的用户价值和业务价值
3. 指出最关键的待补信息，并说明为什么要补
4. 如果已有材料与输入冲突，列出冲突点
5. 用自然语言给出建议性倾向和下一步建议
```
