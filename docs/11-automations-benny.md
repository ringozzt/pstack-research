# 11 · Automations · benny

## 概述

pstack 附带休眠的 **[benny](https://github.com/backnotprop/pstack/tree/main/automations/benny)** 自动化包。它**不是** slash skill，依赖 **Cursor Automations**，因此文档标明 **Cursor-only**。

## 做什么

据包内 README：两条 automation——

1. 对 Slack 问题报告做 **triage**；  
2. 对确认的 bug **复现**，并可能准备小型 draft fix（强调真实 UI 证据）。

## 安装概要（README）

1. 让 Cursor 阅读 [`FOR_AGENTS.md`](https://github.com/backnotprop/pstack/blob/main/automations/benny/FOR_AGENTS.md)，指定目标仓库。  
2. Setup 将整个目录合并到目标仓库 `.cursor/automations/benny/`（保留目标独有文件，冲突需审查）。  
3. 在目标 `.cursor/settings.json` 启用 pstack 插件以共享依赖。  
4. 用户配置放在拷贝包外（如 `.cursor/benny/`），参照 `templates/configuration.example.yaml` 与 feature-map 示例。  
5. 提交无密钥配置后，再在编辑器中审阅/启用 automation，并用无害测试报告验证回复留在原线程。

## 与日常 skills 的边界

- benny 文件不出现在 `/` 技能列表。  
- 需要 Slack + Cursor automations 环境；本调研未做实机联调。  
- 安全上：密钥与频道配置必须留在包外，且勿把秘密提交进 git。

## 参考链接

- https://github.com/backnotprop/pstack/tree/main/automations/benny  
- https://github.com/backnotprop/pstack/blob/main/automations/benny/README.md  
- https://github.com/backnotprop/pstack/blob/main/automations/benny/FOR_AGENTS.md  
