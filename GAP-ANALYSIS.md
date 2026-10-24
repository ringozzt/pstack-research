# 缺口分析（GAP-ANALYSIS）

**语料：** pstack 中文调研（本仓库）  
**基线日期：** 2026-10-24（Asia/Shanghai）  
**方法：** 对照 `backnotprop/pstack` README、`MIRROR.md`、`plugin.json`、关键 `SKILL.md`、GitHub API（仓库元数据 / 近期 commits / open issues），以及公开的 Agent Skills 标准页；不声称穷尽每一份 playbook 逐步细则。

## 已覆盖

| 区块 | 内容 |
| --- | --- |
| 身份 | 独立镜像 vs `cursor/plugins/pstack`、`upstream`/`main` 同步流程 |
| 元数据 | MIT、stars/forks 快照、创建与近期同步时间、版本 0.15.32 |
| 哲学 | 少而精、fearless parallelism、多模型、反 AI slop |
| 安装 | `npx skills add`、Cursor `/add-plugin`、Claude Code marketplace |
| 核心 | `/poteto-mode` 与 23 playbook 索引 |
| 技能 | ~58 个 skills/ 目录名；独立技能与依赖表 |
| 原则 | 24 条分组摘要 |
| 验证 | TDD、prove-it-works、verification / formal verification 技能链 |
| 编排 | setup-pstack 角色、arena/swarm/interrogate |
| 子代理 | poteto-agent、comment-sicko |
| 自动化 | benny 休眠包（Cursor-only） |
| 相邻 | bro、agentskills.io、cursor-team-kit、dyl-stack（仅公开链接） |
| 风险 | 自主性、成本、开放 issue #14 / PR #15 |

## 已知缺口

| 缺口 | 说明 | 建议 |
| --- | --- | --- |
| 逐 playbook 逐步翻译 | 仅索引与摘要，未全文中文化 | 按使用频率挑 5 个深写 |
| harness 实测矩阵 | 未在本机跑 Claude Code / Codex / Pi 全套安装 | 补 `docs/harness-matrix.md` 实测笔记 |
| 与上游 diff 清单 | 未逐文件 diff `upstream` vs `main` | 同步后跑 `git diff upstream main --stat` |
| benny 实机联调 | 未接 Slack / Cursor automations | 有环境再写操作笔记 |
| 成本与 token 账本 | 无自测账单 | 禁止编造；有账单后再记 digests |
| 社区二次封装 | 仅见公开 `dyl-stack` 等插件表一行 | 跟踪 cursor/plugins 市场表 |
| 中文二创教程 | 未系统归档第三方博客 | digests 摘录 + 核实链接 |
| 原则 leaf 全文 | 只摘要 rule 句 | 需要时链到各 `principle-*/SKILL.md` |

## 建议的下一批评题

1. 精读 `orchestrate` / `autopilot-full` / `shipping` 三篇 playbook（长任务与落地）  
2. `/create-verification-skill` 生成物结构与项目适配模板  
3. Claude Code 前缀命令映射表（`docs/harness/claude-code.md`）中文化速查  
4. no-comments / Comment Sicko 与 issue #14 的后续修复跟踪  
5. 与 `cursor-team-kit`（`deslop` / `control-cli` / `control-ui`）的组合用法  
6. `automate-me` 如何从 transcript 生成个人 `*-mode`

## 刻意不做的事

- 不编造 GitHub stars、未公开内部用量、未核验引语  
- 不把 LinkedIn / 营销帖的数字写成仓库事实（可作「外部讨论」单独标注）  
- 不在本阶段创建 GitHub remote、推送或定时任务（由父流程处理）  
