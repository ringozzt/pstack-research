# 04 · 技能目录

## 概述

镜像仓库 `skills/` 下在 2026-10-24 枚举到 **58** 个技能目录（含 24 个 `principle-*`）。README 把技能分成「可单独安装」与「需连带安装」两类。多数情况下只需 `/poteto-mode`，其余技能由步骤按需触发。

## 可单独使用（README 列表）

`unslop`, `bro`, `how`, `tdd`, `typescript-best-practices`, `arena`, `swarm`, `interrogate`, `reflect`, `show-me-your-work`, `figure-it-out`, `automate-me`, `correct`, `benchmark-checklist`, `in-your-own-words`, `sharpen`, `statechart`

## 依赖组合（README 表）

| 技能 | 还需安装 |
| --- | --- |
| `teach` | `how`, `why` |
| `why` | `how` |
| `technical-writing` | `unslop` |
| `architect` | `arena`, `how` |
| `blast-radius` | `arena`, `how`, `why`, `unslop` |
| `create-verification-skill` | `maintain-verification-skill` |
| `create-formal-verification-skill` | `maintain-formal-verification-skill`, `statechart` |
| `ketchup` | `bro` |
| `ketchup-video` | `ketchup`, `bro` |
| `poteto-mode` | 全部 `principle-*` 与大部分其它技能 |
| `poteto-help` | 你希望它能介绍的那些技能 |

会 spawn 子代理的技能：若无 `poteto-mode`，则用默认 effort。

## 功能向速查（非 principle）

| 技能 | 何时用（意译） |
| --- | --- |
| `poteto-mode` | 非平凡任务默认入口 |
| `poteto-help` | 新人 / 不知用哪个技能；只在显式调用时跑 |
| `setup-pstack` | 配置各角色模型与 budget |
| `in-your-own-words` | 开工前让代理复述目标与问题 |
| `sharpen` | 把提示改深（不替你做任务） |
| `how` / `why` / `teach` | 机制走读 / 证据溯源 / 合成讲解 |
| `recall` | 从聊天与共享记录重建主题现状 |
| `ketchup` / `ketchup-video` | 自上次消息以来的进展与待决项 |
| `blast-radius` | 小改动的破坏面 + 运行证明 |
| `architect` | 跨函数边界前定调用方/类型/模块形状 |
| `arena` / `swarm` / `interrogate` | 见专题 10 |
| `tdd` / `benchmark-checklist` | 见专题 06 |
| `create-*-verification-skill` / `maintain-*` / `statechart` | 项目级验证与形式化 |
| `unslop` / `bro` / `technical-writing` / `no-comments` | 见专题 09 |
| `reflect` / `correct` / `automate-me` / `figure-it-out` / `show-me-your-work` | 元改进、个人 mode、决策轨迹 |
| `typescript-best-practices` | 落实 type-system-discipline |
| `make-bot-ui` | 带 webhook 的 Grok Bot 页面/仪表盘（含 Tailscale 等） |

## 完整目录名列表（API 枚举）

```
architect arena automate-me benchmark-checklist blast-radius bro correct
create-formal-verification-skill create-verification-skill figure-it-out how
in-your-own-words interrogate ketchup ketchup-video maintain-formal-verification-skill
maintain-verification-skill make-bot-ui no-comments poteto-help poteto-mode
principle-*（24 个，见 05） recall reflect setup-pstack sharpen show-me-your-work
statechart swarm tdd teach technical-writing typescript-best-practices unslop why
```

## 参考链接

- https://github.com/backnotprop/pstack/tree/main/skills  
- https://github.com/backnotprop/pstack#skills  
