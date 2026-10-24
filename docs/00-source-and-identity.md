# 00 · 来源与身份

## 概述

调研对象是公开仓库 **[backnotprop/pstack](https://github.com/backnotprop/pstack)**。仓库顶部明确写明：它是 [`cursor/plugins/pstack`](https://github.com/cursor/plugins/tree/main/pstack) 的 **standalone mirror**，为在 Cursor 之外（Claude Code、Codex、Pi、OpenCode 等）独立安装 Agent Skills 而维护，并与上游保持同步。

`plugin.json`（版本 **0.15.32**，核验于 2026-10-24）中：

- `name`: `pstack`
- `author.name`: Lauren Tan
- `homepage` / `repository` 仍指向 Cursor plugins 上游树
- `description`: “if you want to go fast, go deep first…”

README 正文以第一人称 **poteto**（[x.com/poteto](https://x.com/poteto)）介绍作者背景：React core / React Compiler，曾在 Meta、Netflix、Cursor 等工作过大量代码。GitHub 用户 [poteto](https://github.com/poteto) 与 `plugin.json` 署名 Lauren Tan 对应同一公开身份；本调研不扩展未公开履历。

## 镜像如何同步

仓库根目录 [MIRROR.md](https://github.com/backnotprop/pstack/blob/main/MIRROR.md) 规定两条分支：

| 分支 | 含义 |
| --- | --- |
| `upstream` | Cursor `pstack/` 原样拷贝，无本地改动 |
| `main` | `upstream` + 本镜像的编辑（README 顶部说明、部分技能的 harness-neutral 改写） |

同步步骤概要（原文流程）：sparse-checkout 拉取 `cursor/plugins` 的 `pstack/` → 落到 `upstream` → merge 进 `main` → 刷新 Comment Sicko 内嵌 prompt → 检查是否引入新的 Cursor 专有路径 → push 两条分支。

近期 commits（API，UTC 时间戳已换算思路见 README）：多次 `upstream: cursor/plugins/pstack @ <sha>` 与 `Sync upstream … (0.15.x)`，最新一次对应 **0.15.32**（2026-10-24）。

## 仓库结构（根目录）

| 路径 | 作用 |
| --- | --- |
| `skills/` | Agent Skills（每技能一目录 + `SKILL.md`） |
| `agents/` | `poteto-agent.md`、`comment-sicko.md` |
| `automations/benny/` | 休眠的 Cursor automations 包 |
| `docs/guide/`、`docs/harness/` | 上游指南与 harness 适配文档 |
| `plugin.json`、`.cursor-plugin/` | 插件清单与 Cursor 插件元数据 |
| `MIRROR.md` | 镜像同步手册 |
| `LICENSE` | MIT |

## 与「官方插件」的关系

- **内容源头**：Cursor 官方 monorepo [`cursor/plugins`](https://github.com/cursor/plugins) 中的 `pstack` 目录。
- **独立价值**：`npx skills add backnotprop/pstack` 等路径不依赖 Cursor marketplace；技能内含 **Harness** 映射（Task→各家 subagent 工具、模型配置路径等）。
- **非 GitHub `mirror_url` 字段镜像**：API 中 `mirror_url` 为 null；这里的「mirror」是文档与工作流意义上的独立副本。

## 参考链接

- https://github.com/backnotprop/pstack  
- https://github.com/cursor/plugins/tree/main/pstack  
- https://github.com/backnotprop/pstack/blob/main/MIRROR.md  
- https://github.com/backnotprop/pstack/blob/main/plugin.json  
