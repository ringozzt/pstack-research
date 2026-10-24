# 15 · 术语表

| 术语 | 说明 |
| --- | --- |
| Agent Skills | 开放格式：目录 + `SKILL.md`（元数据与指令），见 agentskills.io |
| pstack | 本调研对象；skills + principles + agents +（可选）automations |
| poteto / poteto-mode | 作者 persona 与默认高阶路由技能 |
| playbook | poteto-mode 下的任务剧本（`playbooks/*.md`） |
| principle-* | 24 条可单独引用的原则技能 |
| harness | 承载技能的代理产品（Cursor、Claude Code、Codex、Pi、OpenCode…） |
| standalone mirror | `backnotprop/pstack` 相对 `cursor/plugins/pstack` 的独立同步副本 |
| upstream / main | 镜像仓库分支：纯上游 vs 上游+本地中性化编辑 |
| unslop | 去除 AI 写作痕迹的技能与文风规范 |
| arena | 同题多候选 → 选 base → 嫁接 |
| swarm | 多 worker 覆盖/竞速 → 单报告 |
| interrogate | 多模型对抗评审 → 综合裁决（不自动改码） |
| poteto-agent | 委托子代理类型，须先读满 poteto-mode |
| Comment Sicko | 只读注释审查子代理 |
| benny | Cursor-only 的 Slack 问题 triage/复现 automation 包 |
| setup-pstack | 写入每角色模型映射与 budget 的技能 |
| prove-it-works | 对照真实产物验证的原则 |
| cursor-team-kit | 提供 deslop/control-* 等、被 pstack 引用但不捆绑的插件 |
| bro | backnotprop/bro；白话复述相关技能包 |
| fearless parallelism | README 用语：在可验证前提下并行多代理 |
| figure-it-out | 无现成剧本时设计严谨可审计剧本的技能 |
| shipping / babysit | 绿灯栈独立验证落地 / 推 PR 至可合并 |
