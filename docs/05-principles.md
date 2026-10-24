# 05 · 24 条原则

## 概述

原则是 24 个短技能（`skills/principle-<kebab>/SKILL.md`）。`poteto-mode` 在任务开始时读取内联索引；独立文件供其它技能按名引用。应用某原则时应读对应 leaf 全文，并在回复中点名影响了哪次决策。

下列 **rule** 句摘自 README 原则表（英文原文压缩为中文说明时保持语义，专名保留）。

## Core

| 原则 | 规则要点 |
| --- | --- |
| laziness-protocol | 偏向删除与能解决问题的最小变更 |
| foundational-thinking | 写逻辑前先定核心类型与数据结构、脚手架顺序、并发共享物 |
| redesign-from-first-principles | 像需求从第一天就是根基一样重设计，而不是外挂 |
| attack-the-premise | 共享同一前提的多次修复都失败同一门禁时，先写下并直接检验前提 |
| subtract-before-you-add | 先去掉死重与冗余，再在更简单基底上构建 |
| minimize-reader-load | 减少问题到答案之间的层数与读者脑中的隐状态 |
| outcome-oriented-execution | 有阶段边界的重写/迁移：收敛到目标架构，不保留一次性兼容态 |
| experience-first | 用户体验优先于实现方便；少而精的打磨功能 |
| exhaust-the-design-space | 提交前做 2–3 个竞品原型并排比较 |
| build-the-lever | 非平凡工作：做可复跑的工具（codemod/脚本/生成器/技能）而非手搓 |

## Architecture

| 原则 | 规则要点 |
| --- | --- |
| model-the-domain | 用结构（状态机、类型模型、表/注册表等）编码领域，而非散落条件 |
| boundary-discipline | 守卫集中在系统边界；内部信任类型；业务逻辑偏纯函数 |
| type-system-discipline | 非法状态不可表示、语义原语 branding、边界解析、穷尽变体、权威 schema |
| make-operations-idempotent | 无论部分先验运行如何，收敛到同一终态 |
| migrate-callers-then-delete-legacy-apis | 同一波迁移调用方并删除旧 API |
| separate-before-serializing-shared-state | 先消除共享；仅当单一写者是真不变量时再结构上串行化 |

## Verification

| 原则 | 规则要点 |
| --- | --- |
| prove-it-works | 完成前对照真实产物验证，不是代理自报或「能编译」 |
| fix-root-causes | 追到系统第一次出错的地方；守卫仅在合法状态时才算修复 |
| sequence-verifiable-units | 多步工作拆成每步可验证；提交/PR 顺序能向评审自证 |
| test-behavior-not-implementation | 断言用户可观察行为 |
| explain-the-number | 信任/汇报数字前找出限制因素，排除测错对象 |

## Delegation / Meta

| 原则 | 规则要点 |
| --- | --- |
| guard-the-context-window | 大块给子代理；主线程留摘要 |
| never-block-on-the-human | 可逆工作先做再呈现；不可逆才确认 |
| encode-lessons-in-structure | 重复指令应落成 lint/元数据/运行时检查/脚本，而不是更多散文 |

## 参考链接

- https://github.com/backnotprop/pstack#principles  
- 例：https://github.com/backnotprop/pstack/tree/main/skills/principle-prove-it-works  
