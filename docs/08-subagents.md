# 08 · 子代理

## 概述

`/poteto-mode` 跑在接收该命令的聊天里：该聊天拥有 playbook、todo 与所有 spawn。仓库另附两个 agent 定义文件。

## `poteto-agent`

路径：[`agents/poteto-agent.md`](https://github.com/backnotprop/pstack/blob/main/agents/poteto-agent.md)

- **用途**：playbook 步骤中的代码委托与 helper；**不要**用它来跑 playbook 本身。  
- **要求**：工作前完整阅读 `poteto-mode` 的 `SKILL.md`（含原则索引）。用 `generalPurpose` 替代会跳过该读取并漂移。  
- **新鲜度**：默认每个新任务用新的 `poteto-agent`；仅在 poteto-mode「Subagents」节列出的严格情形下 resume（本地 checkout、未提交改动、仍在跑的进程等）。  
- `is_background: true`。

## Comment Sicko

路径：[`agents/comment-sicko.md`](https://github.com/backnotprop/pstack/blob/main/agents/comment-sicko.md)

- 只读评论审查者，`subagent_type: "comment-sicko"`。  
- 通常经 [`/no-comments`](https://github.com/backnotprop/pstack/blob/main/skills/no-comments/SKILL.md) 调用，不直接召唤。  
- 镜像同步时会把该文件拷到 `skills/no-comments/references/comment-sicko.md`（见 `MIRROR.md`）。

## 与工作流技能的关系

`how` / `why` / `interrogate` / `reflect` / `swarm` 等会规定自己的 `subagent_type` 与模型多样性；**不要**强行全部改成 `poteto-agent`。

主线程责任：审 diff、自己写摘要，不原样转发子代理说辞；「第二意见」= 同提示换模型。

## 开放问题信号

Issue [#14](https://github.com/backnotprop/pstack/issues/14)（2026-10-23 打开）报告：`no-comments` 在处理外部约束类注释时可能反复拒绝并中止独立工作。属于真实用户反馈，说明 Comment Sicko 工作流仍有边界情况。

## 参考链接

- https://github.com/backnotprop/pstack/tree/main/agents  
- https://github.com/backnotprop/pstack/blob/main/skills/no-comments/SKILL.md  
