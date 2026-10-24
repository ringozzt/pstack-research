# 03 · `/poteto-mode` 与 23 个剧本

## 概述

[`/poteto-mode`](https://github.com/backnotprop/pstack/blob/main/skills/poteto-mode/SKILL.md) 是默认入口（`disable-model-invocation: true`，需用户显式调用）。它匹配任务到 playbook，把步骤原样拷进 todo，再按步骤路由其它 skills 与原则。

被调用时会：

1. 匹配 `playbooks/<title>.md` 并打开 todo（跳过的步骤留 `skip: <reason>`）。  
2. 步骤触发时路由 `how` / `why` / `architect` / `arena` / `swarm` / `interrogate` / `unslop` / `tdd` / principles 等。  
3. 按「Writing the reply」写面向消费者与维护者的 unslop 回复。

## 剧本一览（仓库 `skills/poteto-mode/playbooks/`，共 23）

| 剧本文件 | 用途（意译自 README / SKILL） |
| --- | --- |
| `investigation.md` | 只读问题：怎么工作、为何如此、是否确定 |
| `bug-fix.md` | 复现 → 根因 → 带运行时证据的修复 |
| `perf-issue.md` | 对照基线追踪可测的慢 |
| `hillclimb.md` | 对单一指标持续科学改进（假设循环 + 前后测量 + 每接受一胜一提交） |
| `runtime-forensics.md` | 从实时 instrumentation 诊断泄漏、空转等（交付诊断，非修复） |
| `trace-forensics.md` | 解读已捕获的 profile/trace/spindump/heap |
| `feature.md` | 新行为：先定数据形状再实现 |
| `refactoring.md` | 行为保持的结构变更 |
| `prototype.md` | 廉价草图或用实验结算经验分叉（少问人） |
| `visual-parity.md` | 像素级 UI 等价 |
| `authoring-a-skill.md` | 编写/修改 SKILL.md |
| `eval.md` | 盲测技能/提示变更对代理行为的影响 |
| `babysit.md` | 推 PR/栈到可合并：冲突、评论、CI |
| `shipping.md` | 独立验证绿灯栈后自底向上落地 |
| `autonomous-run.md` | 长任务不停直到完成 |
| `orchestrate.md` | 多日、多栈 PR、大批子代理的协调者会话 |
| `autopilot-full.md` | 独立 PR 队列各有 owner，跑到合并；swarm 验证 |
| `autopilot-stack.md` | 建成线性栈供操作者审查落地，不直接 ship |
| `session-pickup.md` | 接手先前代理未完成工作 |
| `pause-safely.md` | 干净挂起以便后续恢复 |
| `multi-phase-plan.md` | 跨阶段或堆叠 PR |
| `worktree-cleanup.md` | 安全清理 worktree / 陈旧 iOS simulator |
| `opening-a-pr.md` | 其它剧本结束时调用：小序提交 + conventional title + briefing body |

## 路由提示（SKILL 内）

- 大迁移、用户离开去睡觉/「回来要能信」→ 常走 **figure-it-out**（即使表面像 Feature）。  
- 项目级多日程序 → **Orchestrate**；单任务谓语完成 → **Autonomous run**。  
- 「check on PR」「get it green」类 → **Babysit**（不要误用 Cursor 内置同名能力）。  
- 不可逆操作始终暂停；可逆工作默认推进（Autonomy 节）。

## 示例提示（README）

```text
/poteto-mode this pr has a subtle bug where the scroll drifts every 750ms even when idle. repro first, then fix and verify.

/poteto-mode i'm going to bed. land the stack even if ci flakes. i want everything merged by morning.
```

## 参考链接

- https://github.com/backnotprop/pstack/blob/main/skills/poteto-mode/SKILL.md  
- https://github.com/backnotprop/pstack/tree/main/skills/poteto-mode/playbooks  
