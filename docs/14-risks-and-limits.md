# 14 · 风险与边界

## 概述

pstack 强化代理自主与并行，因此风险面主要在**权限、成本、错误自信、Cursor 专有依赖**，而不是传统 CVE 列表。以下为文档与公开 issue 可支撑的边界，不做恐吓式夸大。

## 自主性与不可逆操作

`poteto-mode` Autonomy：可逆工作与部分外部动作默认推进；**force-push 共享分支、部署、删数据、对客消息**等须暂停。用户说 “going to bed / fully autonomous” 会放宽会话覆盖——操作者需清楚自己在授多大权。

## 成本与配额

Arena / Swarm / Interrogate / Autopilot 会倍数放大子代理调用。仓库不提供统一价目；引入前应在自己的账单与速率限制下做小规模试验。本调研**无自测费用数据**。

## Harness 能力落差

- 无子代理工具时退化为串行，fearless parallelism 名存实亡。  
- Cloud agent、Bugbot、Automations、`/loop` 等为 Cursor（或子集）能力；镜像虽改写中性路径，行为仍可能弱一档。  
- `deslop` / `control-ui` / `control-cli` 不在包内。

## 验证不足时的危险

原则要求 prove-it-works，但代理仍可能「自信地」跳步。Shipping 剧本强调绿灯≠安全；团队流程上仍应保留人类抽检，尤其是 autopilot-full。

## 公开问题（轻量跟踪）

调研时 `open_issues_count` = 2：

| 编号 | 类型 | 标题摘要 | 打开时间（UTC） |
| --- | --- | --- | --- |
| [#14](https://github.com/backnotprop/pstack/issues/14) | Issue | no-comments：未决外部约束可导致反复拒绝并中止独立工作 | 2026-10-23 |
| [#15](https://github.com/backnotprop/pstack/pull/15) | PR | poteto-mode：orchestrate 支持显式 frontier `--base` | 2026-10-23 |

## 许可证与归属

MIT。使用与再分发遵循许可证；引用原则/技能时建议链回具体 `SKILL.md`，避免断章。

## 外部营销数字

LinkedIn 等处可能出现「一周一万次内部使用」类陈述。那是作者社交媒体表述，**不是**本仓库 API 字段；本语料不把它写成仓库事实。若需引用，单独标注来源与日期。

## 参考链接

- https://github.com/backnotprop/pstack/blob/main/skills/poteto-mode/SKILL.md（Autonomy / Harness）  
- https://github.com/backnotprop/pstack/issues  
- https://github.com/backnotprop/pstack/blob/main/LICENSE  
