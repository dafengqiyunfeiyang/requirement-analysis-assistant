# 如何上传到 GitHub 供别人下载

可以，完全可以上传到 GitHub 供别人下载。

## 推荐的两种仓库组织方式

## 方式一：单 skill 仓库

适合你现在只想分发这一个 skill。

推荐结构：

```text
your-repo/
  requirement-analysis-assistant/
  README.md
```

优点：
- 结构最简单
- 安装命令最短

对应安装命令：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo <owner>/<repo> \
  --path requirement-analysis-assistant
```

## 方式二：多 skill 仓库

适合你后续还会继续沉淀更多内部 skill。

推荐结构：

```text
your-repo/
  skills/
    requirement-analysis-assistant/
  README.md
```

优点：
- 后续扩展更自然
- 多个 skill 更好管理

对应安装命令：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo <owner>/<repo> \
  --path skills/requirement-analysis-assistant
```

## 建议一起放到仓库里的内容

### 运行必需

- `requirement-analysis-assistant/`

### 推荐附带

- `README.md`
- `docs/2026-03-13-需求自动分析工具-design.md`
- `docs/2026-03-13-requirement-analysis-assistant.md`

说明：
- 运行必需的只有 skill 文件夹本身
- 设计稿和实施计划不是安装必需，但适合给维护者和共建者看

## 上传步骤建议

1. 新建 GitHub 仓库
2. 把 `requirement-analysis-assistant/` 放到你选定的位置
3. 提交并 push
4. 在 README 里写清安装命令
5. 让同事用安装脚本安装

## README 里建议写的最小内容

```md
# 需求判断助手

一个给 PM 使用的 Codex skill，用于基于当前 project 上下文梳理散乱需求输入，识别用户价值、业务价值、待补信息和冲突点。

## 安装

python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo <owner>/<repo> \
  --path requirement-analysis-assistant
```

如果你采用 `skills/` 目录结构，就把 `--path` 改成：

```bash
--path skills/requirement-analysis-assistant
```

## 注意

- 当前环境下我可以帮你准备 GitHub-ready 的目录和说明
- 但真正上传到哪个 GitHub 仓库，取决于你是否提供仓库位置和本机 GitHub 权限
- 如果你给我一个现成 repo，我下一步可以继续帮你整理成适合直接 push 的结构
