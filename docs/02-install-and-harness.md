# 02 · 安装与 harness

## 概述

pstack 以 **Agent Skills** 目录发布。独立镜像强调：不必只用 Cursor。安装入口因 harness 而异；模型配置文件路径也不同。

## 安装方式（仓库文档）

### 通用（skills CLI）

```bash
npx skills add backnotprop/pstack
```

CLI 列出技能供搜索勾选，并选择目标 agent（Claude Code、Codex、Pi、Cursor、OpenCode 等）。说明见 README 与 [skills.sh](https://skills.sh)。

### Cursor

```text
/add-plugin pstack
```

也可走 Cursor 官方 plugins 市场中的 pstack（源头在 `cursor/plugins`）。

### Claude Code

```text
/plugin marketplace add cursor/plugins
/plugin install pstack@cursor-plugins
```

注意（README）：第三方 marketplace **默认不自动更新**；可在 `/plugin` → marketplaces → `cursor-plugins` 打开 auto-update，或手动 `claude plugin update pstack@cursor-plugins`。

Claude Code 会对插件命令加前缀：`/poteto-mode` → `/pstack:poteto-mode`。适配细节见上游 [`docs/harness/claude-code.md`](https://github.com/cursor/plugins/tree/main/pstack/docs/harness)（镜像仓库同样含 `docs/harness/`）。

## 上手两步（官方建议）

1. 跑 [`/setup-pstack`](https://github.com/backnotprop/pstack/blob/main/skills/setup-pstack/SKILL.md)：选 reasoning budget，配置各角色模型。  
2. 需要严谨工程时用 [`/poteto-mode`](https://github.com/backnotprop/pstack/blob/main/skills/poteto-mode/SKILL.md)。

新人可走 [pstack guide](https://github.com/backnotprop/pstack/tree/main/docs/guide)；不确定技能时用 `/poteto-help`。

## 模型配置落盘路径

| Harness | 设置文件 |
| --- | --- |
| Cursor | `~/.cursor/rules/pstack-models.mdc`（always-applied） |
| Claude Code | `~/.claude/rules/pstack-models.md` |
| 其它（Codex / Pi / OpenCode…） | `~/.agents/pstack-models.md`（由技能主动读取） |

旧版 Claude Code 路径曾写到 `~/.agents/`；近期 commit（2026-10-20）改为优先 `~/.claude/rules/`。

## Harness 映射（poteto-mode「Harness」节摘要）

| Cursor 概念 | 其它 harness |
| --- | --- |
| `Task` 子代理 | Claude Code `Agent`；OpenCode `task`；Codex `spawn_agent`；无子代理时串行自做 |
| `poteto-agent` 类型 | 若不存在，用 general 子代理并先读完整 `poteto-mode/SKILL.md` |
| `AskQuestion` | Claude Code `AskUserQuestion`；OpenCode `question`；否则聊天编号选项 |
| `environment: "cloud"` | 他处改为本地 worktree |
| `deslop` / control-* | 无 `cursor-team-kit` 时手动去 slop / 用 Playwright、tmux 等替代 |
| 技能目录 | `.cursor/skills/`、`.claude/skills/`、`.pi/skills/`、`.agents/skills/` 等 |

## 自定义模式（Cursor）

在 `/` 菜单选中 `/poteto-mode` 后用 **option+enter / alt+enter** 可变成 custom mode，跨回合保持；普通 enter 只附着单条消息。可与 Cursor `/loop` 组合做长时运行。

## 参考链接

- https://github.com/backnotprop/pstack#install  
- https://skills.sh  
- https://agentskills.io  
- https://github.com/backnotprop/pstack/blob/main/skills/setup-pstack/SKILL.md  
