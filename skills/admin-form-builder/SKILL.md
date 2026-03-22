---
name: admin-form-builder
description: 构建遵循仓库组件系统、design token 和截图验收规则的中后台 create/edit/view 表单页面。
---

## 先读
- `.ai/context/repo-facts.md`
- `.ai/context/ui-rules.md`
- `.ai/context/api-conventions.md`
- `.ai/context/component-library.md`
- `.ai/prompts/admin-form.md`
- `AGENTS.md`

## 输入
- 表单功能名
- 路由与容器类型
- API 契约
- 字段定义
- 权限信息
- 默认值来源

## 必要行为
- 先梳理字段，再映射组件，再补交互和状态
- 实现 create、edit、view 三种模式
- 使用共享表单组件
- 覆盖 loading、validation error、submit success、backend error 状态
- 产出字段映射表和截图清单
- 如果上下文缺少关键字段，先列缺口，不要臆造
- 默认输出使用简体中文

## Token 节约原则
- 不要在每次任务里重复解释已有 UI 规则
- 不要在每次任务里重复解释 API 约定
- 对固定字段模式直接引用组件库和表单规则

## 标准输出
1. 实现计划
2. 字段与组件映射
3. 页面状态覆盖
4. 文件变更建议
5. 测试与截图项

## 禁止事项
- 在共享控件已存在时使用原始表单控件
- 随意引入新的视觉 token
- 省略只读、必填、联动、禁用条件
