---
name: repo-guide-writer
description: 根据仓库事实、命令、组件系统、样式系统和验收流程生成或更新 AGENTS.md，且不臆造仓库中不存在的细节。
---

## 先读
- `.ai/context/repo-facts.md`
- `.ai/context/ui-rules.md`
- `.ai/context/component-library.md`
- `package.json`
- 现有 `AGENTS.md`
- `README.md`

## 必要输出
- 基于当前仓库事实的 `AGENTS.md`
- 唯一默认包管理器
- 只包含真实脚本的命令章节
- 如果仓库面向 UI，必须有 UI 验收章节
- 默认文档语言使用简体中文

## 必须包含
- 组件来源
- 样式来源
- `dev/build/lint/test/e2e` 命令真相
- 适用时的截图验收方式
- 优先读取哪些 context
- 哪些高频任务优先触发哪些 skill

## Token 节约原则
- 不在 `AGENTS.md` 重复写长篇方法论
- 把稳定规则指向 `.ai/context/`
- 把高频流程指向 `.ai/skills/`

## 禁止事项
- 臆造命令
- 臆造组件名称
- 不经适配直接复制脚手架 README 文案
