---
name: api-page-builder
description: 基于现有 UI 规则、API 约定和组件库上下文，实现列表页、详情页、管理页等 API 驱动页面。
---

## 先读
- `.ai/context/repo-facts.md`
- `.ai/context/ui-rules.md`
- `.ai/context/api-conventions.md`
- `.ai/context/component-library.md`
- `.ai/prompts/api-page.md`

## 必要行为
- 先梳理 API 与状态流
- 再规划查询区、列表区、详情区或操作区
- 明确 loading、empty、error、permission denied 状态
- 明确分页、筛选、刷新、跳转与批量操作
- 默认输出使用简体中文

## token 节约原则
- 不要重复解释已有 UI 规则
- 不要重复解释已有 API 约定
- 直接引用 context 中的固定事实

## 标准输出
1. 页面结构规划
2. API 与状态流
3. 查询区 / 列表区 / 操作区设计
4. 边界状态清单
5. 文件变更建议

## 禁止事项
- 不要臆造 API 字段
- 不要省略分页、筛选、错误处理
