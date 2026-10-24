# 10 · Arena / Swarm / Interrogate

## 概述

三者都是**显式并行**原语，但目的不同：Arena 做同题多候选再嫁接；Swarm 做切片覆盖或竞速后汇总；Interrogate 做多模型对抗评审且**不自动改代码**。

## Arena（`/arena`）

来源：https://github.com/backnotprop/pstack/blob/main/skills/arena/SKILL.md  

阶段：Frame → Fan out → Cross-judge → Pick → Graft → Verify。

- 所有候选同一提示；评分用 3–6 条具体 rubric（候选看不见 rubric）。  
- Runner 模型来自设置文件 `arena runners`；缺省一对 opus + grok。  
- 各候选独立 worktree 或 `/tmp/arena-…`（separate-before-serializing-shared-state）。  
- Cross-judge 只读，尽量选与 parent 不同模型族。  
- Pick 偏向未来维护者易扩展、边界更干净者（Laziness Protocol）。  
- Graft 手工折叠少数优点，禁止机械粘贴；若候选剧烈分叉应重 Frame。

## Swarm（`/swarm`）

来源：https://github.com/backnotprop/pstack/blob/main/skills/swarm/SKILL.md  

阶段：Frame → Fan out → Aggregate → Report。

- 形状：分区切片、同 brief 竞速、或混合；竞速需预先声明 `first pass` / `rank all` / `best-of`。  
- 默认 worker 模型：`swarm workers` 或 `grok-4.7-xhigh-fast`。  
- Cursor 下常用 cloud agent；其它 harness 本地 worktree。  
- 报告状态：`PASS` / `ISSUES` / `BLOCKED`，附证据；测量须记录 SHA 与方法。  
- 主线程返回**一张**汇总表，不粘贴原始 dump。

## Interrogate（`/interrogate`）

来源：https://github.com/backnotprop/pstack/blob/main/skills/interrogate/SKILL.md  

步骤：Scope → Intent → Spawn reviewers → Synthesize → Lead judgment。

- 对抗信号来自**模型多样性**，不是分配人设。  
- 默认 Reviewer A/B：`claude-opus-5-5-xhigh` 与 `grok-4.7-xhigh-fast`（可被设置覆盖）。  
- 只读评审；交付综合裁决，**禁止自动应用修改**。  
- Lead 把发现分为 Act on / Consider / Noted / Dismissed，并附 Agreement Map。  
- 多模型独立提出的问题权重更高。

## 选用建议（本调研归纳，非上游原文）

| 场景 | 优先 |
| --- | --- |
| 设计/实现形状未定 | arena |
| 多包检查、覆盖矩阵、竞速 | swarm |
| 已有 diff/PR 要找盲点 | interrogate |
| 架构边界前多方案 | architect（内部会用 arena/how） |

## 参考链接

- https://github.com/backnotprop/pstack/blob/main/skills/arena/SKILL.md  
- https://github.com/backnotprop/pstack/blob/main/skills/swarm/SKILL.md  
- https://github.com/backnotprop/pstack/blob/main/skills/interrogate/SKILL.md  
