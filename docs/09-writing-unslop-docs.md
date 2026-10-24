# 09 · 写作、unslop 与文档

## 概述

pstack 把「去掉 AI 腔」做成可引用规则编号的技能，并要求代理**起草时就写干净**，而不是写完再打扫。

## `/unslop`

来源：https://github.com/backnotprop/pstack/blob/main/skills/unslop/SKILL.md  

稳定规则 id（部分，便于其它技能引用）：

| 类 | 例 |
| --- | --- |
| Content | 空泛 -ing 短语；模糊归因（Experts believe…） |
| Language | AI 词表（delve、tapestry、pivotal…）；假范围 from X to Y |
| Style | 禁用 em dash；少用冒号作句中连接；少加粗；标题用 sentence case；禁装饰 emoji |
| Communication | chatbot 套话、谄媚语气 |
| Filler / Jargon | in order to；抽象隐喻名词（substrate、north star、flywheel…） |
| Plain speech | 说机制与数字而非「手感」；主动语态；整句带冠词 |

## poteto-mode「Writing the reply」

- 短陈述句；无长破折号；冒号不作句中拐杖。  
- 面向**消费者**与**维护者**说明影响，再谈实现。  
- 不编造链接/引用；每条断言同句带证据或标签（measured / inferred / guess）。

## 其它相关技能

| 技能 | 作用 |
| --- | --- |
| `technical-writing` | Diátaxis + Google developer style + STE + Global English 分层文档标准（依赖 unslop） |
| `bro` | 把上一条消息改成白话（引用 [`backnotprop/bro`](https://github.com/backnotprop/bro)） |
| `no-comments` | 评审前剥注释；spawn Comment Sicko；对声称约束提供编码建议 |
| `ketchup` | 用白话 + 小图总结待决项（依赖 bro） |

提交前若装了 `cursor-team-kit`，还会走 `/deslop`；未安装则自行重读 diff 去 slop。

## 参考链接

- https://github.com/backnotprop/pstack/blob/main/skills/unslop/SKILL.md  
- https://github.com/backnotprop/pstack/blob/main/skills/technical-writing/SKILL.md  
- https://github.com/backnotprop/bro  
