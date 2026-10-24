# pstack 调研语料

面向中文读者的 **[backnotprop/pstack](https://github.com/backnotprop/pstack)** 研究仓库：来源与镜像关系、哲学与原则、安装与多 harness、`/poteto-mode` 剧本、技能目录、验证与 TDD、多模型编排、子代理、写作去 slop、相邻生态与风险边界。

**一句话结论：** pstack 是一套可安装的 Agent Skills「工程纪律包」——以 `/poteto-mode` 路由到约 23 个剧本，用原则与验证压低 AI slop，并在 Cursor / Claude Code / Codex / Pi / OpenCode 等 harness 上可独立使用（本仓调研的是其独立镜像仓库）。

**整理日期：** 2026-10-24（Asia/Shanghai）  
**原则：** 不编造 stars、日期或未核验引语；数字与路径以 GitHub API / 仓库原文为准；不确定处标明「待核」或给检索入口。

## 调研对象快照（核验于 2026-10-24）

| 项 | 值 |
| --- | --- |
| 仓库 | https://github.com/backnotprop/pstack |
| 上游镜像源 | [`cursor/plugins` 下的 `pstack/`](https://github.com/cursor/plugins/tree/main/pstack) |
| 可见性 / 许可 | 公开 / MIT |
| Stars / Forks | 2687 / 207（API `stargazers_count` / `forks_count`） |
| 语言（GitHub 主语言） | JavaScript |
| 创建时间 | 2026-05-27 10:30（Asia/Shanghai；API `created_at` 为 UTC） |
| 近期同步 | 2026-10-24 09:03（Asia/Shanghai）推送，`plugin.json` 版本 **0.15.32** |
| 默认分支 | `main`（另有 `upstream` 分支，见 `MIRROR.md`） |
| Topics | `agentskills`, `backnotprop`, `pstack`, `pstack-claude`, `skills` |
| 作者署名 | README 自称 [poteto](https://x.com/poteto)；`plugin.json` `author.name` 为 Lauren Tan |
| 相关仓库 | [`backnotprop/bro`](https://github.com/backnotprop/bro)（`/bro` 技能引用） |

> Stars/forks 会变；引用时请复读 API 或仓库页，不要抄本表当永久数字。

## 为何有本仓库

把 pstack 的安装路径、剧本表、原则组、验证哲学与 harness 差异收成**可检索中文专题**，方便对照 Cursor 官方插件树与独立镜像，而不是只收藏一篇英文 README。

## 文档目录（`docs/`）

| # | 文档 | 一句话 |
| --- | --- | --- |
| 00 | [来源与身份](docs/00-source-and-identity.md) | 镜像 vs `cursor/plugins/pstack`、分支同步 |
| 01 | [总览与哲学](docs/01-overview-philosophy.md) | 少而精、fearless parallelism、反 slop |
| 02 | [安装与 harness](docs/02-install-and-harness.md) | `npx skills`、Cursor、Claude Code |
| 03 | [`/poteto-mode` 剧本](docs/03-poteto-mode-playbooks.md) | 23 个 playbook 地图 |
| 04 | [技能目录](docs/04-skills-catalog.md) | 独立技能 vs 依赖组合 |
| 05 | [24 条原则](docs/05-principles.md) | core / architecture / verification / … |
| 06 | [验证与 TDD](docs/06-verification-and-tdd.md) | prove-it-works、tdd、formal verify |
| 07 | [多模型与 setup](docs/07-multi-model-and-setup.md) | `/setup-pstack` 角色映射 |
| 08 | [子代理](docs/08-subagents.md) | poteto-agent、Comment Sicko |
| 09 | [写作与 unslop](docs/09-writing-unslop-docs.md) | unslop / technical-writing / bro |
| 10 | [Arena / Swarm / Interrogate](docs/10-arena-swarm-interrogate.md) | 并行尝试、覆盖、对抗评审 |
| 11 | [Automations · benny](docs/11-automations-benny.md) | Cursor-only 休眠包 |
| 12 | [相邻对比](docs/12-comparison-adjacent.md) | bro、agentskills.io、cursor-team-kit |
| 13 | [落地清单](docs/13-adoption-checklist.md) | 怎么装、怎么试、怎么定制 |
| 14 | [风险与边界](docs/14-risks-and-limits.md) | 自主性、成本、开放 issue |
| 15 | [术语表](docs/15-glossary.md) | 中英对照 |

## 其它文件

| 路径 | 说明 |
| --- | --- |
| [GAP-ANALYSIS.md](GAP-ANALYSIS.md) | 已覆盖 / 缺口 / 下一步 |
| [notes/](notes/) | 带出处的摘录（非完整转载） |

## 怎么读

1. 先弄清镜像关系：`00` → `01`  
2. 要上手：`02` → `13` → `03`  
3. 要理解纪律：`05` → `06` → `09`  
4. 要并行与评审：`07` → `10` → `08`  
5. 要评估引入：`12` → `14`

## 一手入口

- 独立镜像：https://github.com/backnotprop/pstack  
- 上游插件目录：https://github.com/cursor/plugins/tree/main/pstack  
- Cursor plugins 总仓：https://github.com/cursor/plugins  
- Agent Skills 标准：https://agentskills.io  
- skills CLI：https://skills.sh  
- 镜像同步说明：https://github.com/backnotprop/pstack/blob/main/MIRROR.md  
