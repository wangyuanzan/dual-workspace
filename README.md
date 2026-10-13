# dual-workspace · 人机双空间

**AI 组织执行过程，你直接使用材料，并决定要了解多深。**

一个按项目适配的 Agent Skill。把用户需要阅读、审阅、修改和使用的实际材料整理到工作台，把工程过程按执行需要组织；需要深入时，再通过对话定位依据。

[English overview](#english-overview) · [使用示例](docs/examples.md) · [验证与限制](docs/validation.md) · [MIT License](LICENSE)

## 解决什么问题

AI 做完任务后，项目里常常留下很多目录和记录。人需要辨认哪份是主稿、哪个结果已过期、哪些材料可以交付。双空间把这部分整理工作纳入 AI 的任务。

- **我的工作台**：正文、图表、结果、交付成品，以及你正在学习或亲自修改的代码。
- **AI工作区**：执行需要的脚本、配置、详细计划、测试和中间材料。

两者是使用方式的划分，双方都能访问。讨论和计划照常进行；工作台提供实际材料，并能追溯来源。

## 如何适配项目

首次使用时，AI 了解项目目标、你的使用方式、已有主稿和固定路径，形成适合本项目的安排，并保存到项目实际生效的规则入口。再次使用时沿用这些约定，用途改变时只调整受影响部分。

软件项目中不能移动的配置和源码继续保留原位；学习项目中你要亲自编辑的模型可以直接成为工作台里的主版本。不会为了两个目录强行搬迁整个工程。

## 安装

这是文字指令技能，运行不需要 Python、API Key 或额外服务。当前技能正文以中文为主。

### 让 Codex 安装

把下面这段发给有文件访问能力的 Codex：

```text
请从 https://github.com/wangyuanzan/dual-workspace 安装人机双空间技能。
技能位于 skills/dual-workspace。
请根据本机 Codex 的技能发现配置选择个人技能目录；如有同名技能，先比较并保留已有定制。
本次只安装技能，不搬动业务文件或修改全局项目规则。
完成后区分说明“文件已安装”与“技能已被当前环境识别”。
```

### 手动安装

1. 下载本仓库并解压。
2. 将 `skills/dual-workspace` 文件夹复制到目标环境支持的技能目录。项目级安装可放在 `.agents/skills/dual-workspace/`；个人级位置请核对当前环境配置。
3. 保留本项目的 MIT 许可证。如果使用单独的技能 ZIP，包内也包含许可证。
4. 检查技能列表；如果尚未出现，重新打开会话，必要时重启客户端。避免在多个发现目录安装同名副本。

目录与调用方式请参见 [OpenAI 官方技能文档](https://learn.chatgpt.com/docs/build-skills)。这是可本地安装的 Skill，尚未发布为插件市场条目。

## 使用

在目标项目中选择“人机双空间”，或明确调用 `dual-workspace`。

首次启用：

```text
使用 $dual-workspace，结合当前项目用途和已有结构启用人机双空间，
并保存适合本项目的协作约定。
```

空项目可补充：“这是模型学习项目，我需要亲自阅读和修改代码。”

阶段交付：

```text
使用 $dual-workspace，按本项目已有约定整理这次交付，
检查主版本、材料入口和结果状态。
```

只讨论安排：

```text
使用 $dual-workspace，先提出适合这个项目的布置方案。
本轮只讨论，不改文件。
```

## 核心约定

- 按用途分类，工作台包含实际可用材料；固定路径下的材料提供清楚入口。
- 每份可编辑材料有唯一主版本，修改前读取当前内容并保护人的手动修改。
- 仅整理或解释时保留正文原文，状态和解释放在入口或针对性说明中。
- 结果关联数据、方法或代码；来源变化后更新产物，或标注过期。
- 已授权工作继续执行，额外的搬移、删除或覆盖先说明影响。
- 通用 Skill 保存适配方法，项目约定保存当地做法。
- 不为每次对话创建总结，不机械生成长、中、短三套记录。

## 范围与参与改进

这是一个初版协作方法，已进行软件、科研和学习项目的隔离场景验证。它依赖模型理解指令、宿主的文件能力和权限，并非文件访问控制、自动同步或后台监控程序。其他 Agent 环境可参考指令，但未逐一验证兼容性。参见[验证说明](docs/validation.md)。

欢迎提交 Issue 或 Pull Request，描述项目类型、你要使用的材料、预期行为和实际问题。请使用最小化、匿名的例子，不要提交凭据、个人绝对路径、私有业务文件或整份聊天记录。

## English overview

**Dual Workspace** is an instruction-only Agent Skill for separating a human-facing workbench from an AI execution workspace. It adapts to the project's purpose, existing structure and editable documents, then stores project-specific working agreements for later tasks.

The workbench contains usable materials, not just summaries. The skill preserves one editable source of truth, protects human edits, exposes stale or unverified results, and supports deeper explanations on request. Code belongs in the workbench when the user needs to study or edit it.

Install `skills/dual-workspace` into a skill directory supported by your host and explicitly invoke `dual-workspace`. The instructions are currently primarily Chinese. This is behavioral guidance, not a permissions boundary or synchronization service. See [examples](docs/examples.md), [validation notes](docs/validation.md), and the [MIT license](LICENSE).
