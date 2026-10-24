# 12 · 相邻项目与标准

## 概述

只列**可核实的公开链接**。不比较未读过的私有包，不编造 stars 排名故事。

## Agent Skills 标准

- 站点：https://agentskills.io  
- 要点：技能 = 含 `SKILL.md` 的文件夹；渐进披露（先 name/description，匹配后再读全文）；跨产品复用。  
- pstack README 明确按此格式组织，并用 [skills.sh](https://skills.sh) CLI 安装。

## `backnotprop/bro`

- https://github.com/backnotprop/bro  
- 描述：Useful skills.  
- API 快照（2026-10-24）：约 **142** stars、**3** forks；创建于 2026-04-22（UTC）。  
- pstack 的 `/bro` 技能引用该仓库；ketchup 依赖 bro。

## Cursor 官方插件邻域（`cursor/plugins` 市场表公开行）

来源：https://github.com/cursor/plugins README 插件表（调研时可见行，非完整生态审计）。

| 名称 | 关系（据公开描述） |
| --- | --- |
| **pstack** | Lauren Tan；本调研对象 |
| **cursor-team-kit** | 提供 `deslop`、`control-cli`、`control-ui` 等；pstack 引用但不捆绑 |
| **dyl-stack** | 声明建立在 pstack 之上的个人 agent style |
| **orchestrate** / **ralph-loop** / **thermos** 等 | 其它编排或审查向插件；能力重叠需各自读 README，本仓不展开 |

## 安装通道对比（事实层）

| 通道 | 典型命令 / 入口 |
| --- | --- |
| 独立镜像 + skills CLI | `npx skills add backnotprop/pstack` |
| Cursor 插件 | `/add-plugin pstack` |
| Claude Code marketplace | `cursor/plugins` → `pstack@cursor-plugins` |

## 参考链接

- https://agentskills.io  
- https://skills.sh  
- https://github.com/backnotprop/bro  
- https://github.com/cursor/plugins  
