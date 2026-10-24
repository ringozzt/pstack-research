# 13 · 落地清单

## 概述

把仓库文档收成可勾选步骤。执行前确认你的 harness 与模型权限。

## A. 安装

- [ ] 选定通道：skills CLI / Cursor plugin / Claude Code marketplace  
- [ ] 安装后确认 `poteto-mode`（或 `/pstack:poteto-mode`）出现在命令列表  
- [ ] 需要完整体验时另装 `cursor-team-kit`（deslop / control-*）  
- [ ] 读一遍 `docs/guide`（上游/镜像均有）

## B. 配置

- [ ] 运行 `/setup-pstack`，选择 budget，确认各角色 slug 在本 harness 可用  
- [ ] 记下设置文件路径（Cursor / Claude Code / `~/.agents/`）  
- [ ] （可选）接受生成 project-local verification skill 的提议  
- [ ] 团队场景：约定不可逆操作仍须人工确认（与 Autonomy 节一致）

## C. 第一次真实任务

- [ ] 用 `/poteto-mode` 跑一个**小** bug fix 或 investigation（带可观察验证）  
- [ ] 观察 todo 是否拷贝了 playbook 步骤  
- [ ] 要求回复点名用到的原则与证据标签  
- [ ] 需要时单独试 `/interrogate` 审一个已有 PR

## D. 并行与长时

- [ ] 仅在验证路径清晰后启用 arena/swarm  
- [ ] 过夜任务用 autonomous-run / orchestrate，并打开 `show-me-your-work`  
- [ ] Cursor：评估 custom mode + `/loop`；注意费用与分支保护

## E. 定制

- [ ] `/automate-me` 生成个人 `*-mode`（以 pstack 为底座）  
- [ ] `/reflect` 把长任务配方写回技能  
- [ ] `/correct` 把反复纠正提升为结构约束（lint/CI/类型）

## F. 镜像追随者

- [ ] 若跟踪 `backnotprop/pstack`：关注 `Sync upstream … (x.y.z)` 提交  
- [ ] 重大升级后重跑 `/setup-pstack`（默认模型可能变）  
- [ ] 关注 open issues（如 #14 no-comments 行为）

## 参考链接

- https://github.com/backnotprop/pstack#get-started  
- https://github.com/backnotprop/pstack/tree/main/docs/guide  
