# 开源项目与资料调研

本仓库不是凭空编一套“终极 Prompt”。初始结构参考了以下成熟做法，但不直接复制其内容。

## 重点参考

### OpenAI Codex

- `openai/codex` 使用分层 `AGENTS.md` 为具体目录提供规则。
- `openai/skills` 将可复用能力封装为按需发现和加载的 Skill。
- 结论：项目入口规则应简短，详细流程应放入按需文档或 Skill。

### wshobson/agents

该项目同时面向 Claude Code、Codex、Cursor、OpenCode 和 Gemini CLI，采用“短 `AGENTS.md` 作为目录，细节放在 docs 和 skills”的方式，并为不同工具生成适配层。

可借鉴：

- 单一 Markdown 源可适配多个 Agent 工具
- 根指令文件保持精简
- 子智能体与技能分开管理

不照搬：

- 该项目规模很大，插件和智能体数量远超本人的实际需求
- 当前仓库优先解决个人多仓库开发，而不是建设公开插件市场

### TheRealSeanDonahoe/agents-md

提供可直接放入仓库的单文件 `AGENTS.md`，重点约束冲动重构、无验证修改和迎合式回答。

可借鉴：

- 强制验证循环
- 限制无关重构
- 一份入口文件兼容多个编程 Agent

不照搬：

- 单文件无法承载本人的多仓库边界和项目专属流程

### MicrosoftDocs/Agent-Skills 与 Hugging Face Skills

两者都采用 `skills/<skill-name>/SKILL.md` 的标准化目录，并提供不同 AI 工具的安装位置说明。

可借鉴：

- Skill 应是可独立安装、按需加载的任务流程
- 项目级和用户级 Skill 应分开
- Skill 不应替代仓库自己的 `AGENTS.md`

### golbin/agent-skills

采用 `skills/` 加 `templates/` 的轻量仓库结构，包含 PRD、实现审查等可重复流程。

可借鉴：

- 把流程封装为 Skill
- 同时保留可复制的项目模板

## 研究结论

有关 `AGENTS.md` 效果的研究并不完全一致：有研究观察到运行时间和输出 Token 减少，也有研究发现过多或自动生成的规则会降低任务成功率并增加成本。共同点很朴素，甚至有点令人生气：规则不是越多越好，只有真正帮助 Agent 定位代码、理解边界和运行验证的内容才值得保留。

因此本仓库采用：

1. 根 `AGENTS.md` 保持短小。
2. 详细规则放入 `docs/`。
3. 重复性流程放入 `skills/`。
4. 每个业务仓库只记录无法从代码推断的边界、命令和风险。
5. 后续根据真实任务失败记录持续精简和修正，而不是不断堆字数。

## 许可证原则

只借鉴结构和公开做法。引入第三方 Skill 或文本前必须检查其许可证，并在仓库中记录来源。未经许可证确认，不直接复制大段内容。
