---
name: react-agent-prompt-updater
description: 更新 ReAct 风格 agent prompt 和运行循环，同时保持 parser、tool call、provider 约定一致。
---

## 先读
- `.ai/context/repo-facts.md`
- `.ai/context/provider-conventions.md`
- `.ai/prompts/react-agent.md`
- 当前 prompt 文件
- 当前 parser 文件
- 当前 tools 文件
- 当前 provider 文件
- `AGENTS.md`

## 必要行为
- 检测 prompt / parser 漂移
- 保持最终答案语法唯一
- 任何语法变化都同步分析 parser、tools、provider 影响
- 如果外部 prompt 或文档依赖旧语法，必须输出迁移说明
- 默认输出使用简体中文

## Token 节约原则
- 不重复解释 provider 约定，直接引用 `.ai/context/provider-conventions.md`
- 不重复讲 ReAct 原理，直接聚焦语法、漂移点、迁移成本

## 标准输出
1. 当前漂移点
2. 新 prompt 建议
3. parser 影响
4. tool call 影响
5. provider 影响
6. changelog 更新建议

## 禁止事项
- 同时保留多种最终答案语法
- 只改 prompt，不分析 parser 与 provider
