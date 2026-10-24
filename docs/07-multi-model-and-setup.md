# 07 · 多模型与 `/setup-pstack`

## 概述

pstack 默认按**角色**选模型：代码委托偏快代码模型，判断与散文偏强推理模型；arena / architect / interrogate 使用**模型列表面板**以保留多样性。`/setup-pstack` 检测当前会话可传给子代理的 slug，写入 always-applied（或等价）规则。

## 默认角色映射（setup-pstack SKILL 模板，budget: large / xhigh）

| 角色 | 默认 slug（原文） |
| --- | --- |
| feature, refactoring | `grok-4.7-xhigh-fast` |
| bug-fix / perf-issue / hillclimb | `grok-4.7-xhigh-fast` |
| judgment and prose | `claude-opus-5-5-xhigh` |
| hardest tasks | `claude-opus-5-5-xhigh` |
| how explorer / why investigators / reflect tooling / swarm workers | `grok-4.7-xhigh-fast` |
| how explainer / why synthesizer / reflect judgment… | `claude-opus-5-5-xhigh` |
| arena runners / architect runners / interrogate reviewers | 两模型列表（opus + grok） |
| arena cross-judge pool | 两模型列表（挑与 parent 不同族） |

别名 `inherit-parent` / `auto`：该角色跟父聊天模型（省略子代理 `model`）。

## Budget 档位

| 标签 | 目标 effort |
| --- | --- |
| unlimited | max |
| large | xhigh（与技能默认一致） |
| medium | high |
| small | medium |

Grok slug 最高到 `xhigh`；`unlimited` 下 Grok 仍落在 `xhigh`。重跑时：与默认不同的角色族会被保留；默认变更后旧规则仍钉死旧值——需删行或删文件再跑 setup。

## poteto-mode 侧策略摘要

- 默认后台 spawn；代码难度分级；最难变更走 strongest judgment 模型。  
- 验证类保持在 `swarm workers` 模型/速度。  
- 调整时只改 effort 与是否 `-fast`，**保持角色声明的模型族**，以免多样面板塌缩。  
- 子代理工具拒收 slug 时回退并说明，不要连环猜 slug。

## 参考链接

- https://github.com/backnotprop/pstack/blob/main/skills/setup-pstack/SKILL.md  
- https://github.com/backnotprop/pstack/blob/main/skills/poteto-mode/SKILL.md（Subagents / Harness）  
