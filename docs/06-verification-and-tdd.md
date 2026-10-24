# 06 · 验证与 TDD

## 概述

pstack 把「证明有效」写成原则与可执行技能，而不是口号。验证层次大致为：行为测试 / 真实 UI 驱动 → 项目本地 verify skill → 形式化（TLA+ 等）→ 基准数字审查。

## 原则锚点

- **prove-it-works**：跑真实功能、读真实值、看真实 diff。  
- **test-behavior-not-implementation**：测用户能观察的行为。  
- **explain-the-number** + **`benchmark-checklist`**：汇报加速/回归前审查限制因素、调参、误差、重复与端到端相关性。  
- **sequence-verifiable-units**：每步可验证再进入下一步。

## `/tdd`（技能摘要）

适用：用户明确要求 TDD/失败测试，或 bug 有**便宜的本地测试靶**。不适用：路径不清、昂贵、偏集成、或未请求时硬造测试。

工作流：理解 bug → 选最窄可执行检查 → **先写失败测试** → 确认因正确原因失败 → 最小修复 → 再跑通。

明确写：**宁可不要新测试，也不要坏测试**（测 mock、锁实现细节、依赖时序/全局态、为小修复上重型基建等）。

来源：https://github.com/backnotprop/pstack/blob/main/skills/tdd/SKILL.md

## 项目级 verification skill

| 技能 | 作用 |
| --- | --- |
| `create-verification-skill` | 为任意语言/平台生成项目本地 verify skill（含 feature map） |
| `maintain-verification-skill` | feature map 漂移时：源码波 + 一次 live pass，至多一个「已证明更正」的 PR |
| `create-formal-verification-skill` | 测试够不到的竞态/重试/状态机/解析器/unsafe：选合适工具证明一条性质并生成可复检技能 |
| `maintain-formal-verification-skill` | 被覆盖代码变更后更新模型/harness/性质并区分「验证漂移」vs「代码 bug」 |
| `statechart` | 从 TLA+ 模型生成 mermaid 状态图供行为所有者查看；也可从约定图生成 TLA+ 骨架或对照审计 |

`/setup-pstack` 结束时会可选提议生成 verification / formal verification 技能。

## Shipping 与绿灯

**Shipping** 剧本强调：CI 绿灯 ≠ 安全。合并前要对栈做独立 per-PR 裁决，且只落地从根开始的连续已验证前缀。

## 参考链接

- https://github.com/backnotprop/pstack/blob/main/skills/tdd/SKILL.md  
- https://github.com/backnotprop/pstack/blob/main/skills/create-verification-skill/SKILL.md  
- https://github.com/backnotprop/pstack/blob/main/skills/statechart/SKILL.md  
- https://github.com/backnotprop/pstack/blob/main/skills/poteto-mode/playbooks/shipping.md  
