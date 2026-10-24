# 01 · 总览与哲学

## 概述

pstack 自称是作者日常在 Cursor 用来「高质量交付」的同一套 skills：**目标不是最大化产出行数，而是用更少、更高质量的代码推进工作**。README 把「AI 写太多 slop」当作要正面解决的问题，并用原则、剧本、验证与写作规范约束代理行为。

## 核心主张（来自 README，意译 + 锚定原文）

1. **Go deep first.** 吞吐若没有质量，不是追求目标。  
2. **Less, higher quality.** 与「二十人 slop 工厂」式堆代码相对。  
3. **Fearless parallelism.** 当单个代理的产出可验证、可信时，才敢并行多个 `/poteto-mode` 代理。  
4. **Multi-model.** 不同前沿模型长短不同；默认把代码委托与判断/散文拆到不同模型族，并由 `/setup-pstack` 可配。  
5. **Skills as portable procedures.** 内容是标准 [Agent Skills](https://agentskills.io) 文件夹（`SKILL.md`），可跨 harness 安装。

## 使用心智模型

```
用户任务
   → /poteto-mode（或个别技能）
      → 匹配 playbook，把步骤写入 todo
      → 按步骤调用 how / architect / tdd / unslop / principles…
      → 子代理（poteto-agent 等）执行切片
      → 用真实产物验证（prove-it-works）
      → 以 unslop 风格回复（面向消费者与维护者）
```

README 明确：**默认不迷信「规划技能」**——作者认为 Cursor 自带 plan mode 已够用，且「最好的规格是代码」；需要计划时可由 `/poteto-mode` 覆盖，但不是默认。

## 未随包附带、但会提到的能力

`poteto-mode` 会引用但不捆绑：

- `/deslop`、`control-cli`、`control-ui` → 来自 **`cursor-team-kit`** 插件  
- `/create-skill` → Cursor 内置  
- Cursor 内置 `/autopilot` → 在 poteto-mode 内，PR 状态类请求改走 **babysit** 剧本

完整集合需自行另装 `cursor-team-kit`（见相邻对比文档）。

## 参考链接

- README（镜像）：https://github.com/backnotprop/pstack/blob/main/README.md  
- Agent Skills：https://agentskills.io  
- 上游插件列表中的 pstack 行：https://github.com/cursor/plugins  
