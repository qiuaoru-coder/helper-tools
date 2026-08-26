# 辅助软件：通用 Agent Skills

[English](README.md)

这里收录帮助普通人安全完成真实软件操作的通用 Agent Skills。它们不要求用户熟悉命令行，也不会把所有人都塞进同一套固定步骤。

## 当前包含

### `github-first-publish`：第一次发布 GitHub 项目助手

适合以下情况：

- 第一次把代码、Skill、文档或其他项目发布到 GitHub；
- 希望 AI 一次只教一步，完成后再继续；
- 已经有仓库，但不知道还缺什么；
- 遇到按钮找不到、上传失败、推送冲突或权限问题；
- 想检查项目是否适合公开。

它不是把一份“20多步教程”机械重放，而是先判断用户目前走到哪里，再跳过已经完成或不适用的步骤。

## 三种使用方式

- **新手带领模式：** 一次只给一个明确动作，说明为什么做以及成功后应该看到什么。
- **协助发布模式：** 在用户授权范围内准备文件、检查项目并完成本地或 GitHub 操作。
- **仓库检查模式：** 检查已有仓库的发布风险、使用障碍和最值得改进的地方。

## 最简单的输入

~~~text
使用 $github-first-publish。

我想把自己的第一个项目发布到 GitHub。
我不熟悉 GitHub，请一次只教我一步，等我说完成后再继续。
~~~

如果愿意提供更多信息，最好补充：

- 本地项目文件夹或仓库链接；
- 项目是做什么的、给谁使用；
- GitHub账号、仓库名和公开或私有；
- 希望一步步指导、让 AI 协助操作，还是只检查已有仓库；
- 页面不同时的截图或完整错误提示。

## 它可以帮助完成什么

- 检查密钥、隐私、版权风险和不应上传的文件；
- 准备真实易懂的 README、`.gitignore` 和许可证选择；
- 安全建立本地 Git 与 GitHub 仓库；
- 完成首次上传并在 GitHub 页面验证；
- 设置 About、Topics、Release、Issues、Discussions 和必要的安全选项；
- 处理登录失败、历史冲突、文件缺失、大文件和页面变化；
- 最后以陌生访客的角度检查别人能否看懂、安装和使用。

## 安装

直接下载安装包：

- [下载 github-first-publish.zip](https://github.com/qiuaoru-coder/helper-tools/releases/latest/download/github-first-publish.zip)

### Codex

~~~bash
git clone https://github.com/qiuaoru-coder/helper-tools.git
mkdir -p ~/.codex/skills
cp -R helper-tools/github-first-publish ~/.codex/skills/
~~~

### Claude Code

~~~bash
git clone https://github.com/qiuaoru-coder/helper-tools.git
mkdir -p ~/.claude/skills
cp -R helper-tools/github-first-publish ~/.claude/skills/
~~~

### Cursor

把 `github-first-publish` 文件夹复制到用户目录 `~/.cursor/skills/`，或者项目里的 `.cursor/skills/`。Cursor也可以读取兼容的 `.codex/skills/` 和 `.claude/skills/` 目录。

### WorkBuddy及其他兼容工具

在技能页面导入 `github-first-publish` 文件夹，或者复制到对应软件的 Agent Skills 目录。通用部分是 `SKILL.md` 和 `references/`；`agents/openai.yaml` 是 OpenAI 界面使用的附加信息，其他软件忽略它也不影响核心流程。

## 使用边界

这个 Skill不能替用户获得 GitHub 权限，不能判断用户是否拥有第三方资料的发布权，也不能保证项目一定安全、一定获得关注或 Star。正式公开之前，仍然需要确认账号、权限、公开范围和最终文件列表。

## 许可证

本项目采用 [MIT License](LICENSE)。

欢迎提交具体使用反馈。如果它帮助你顺利发布了第一个项目，也欢迎给仓库一个 Star。
