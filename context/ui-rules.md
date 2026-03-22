# UI 规则

## 页面层级
- 后台表单默认需要考虑 `create` / `edit` / `view`
- API 驱动页面默认需要考虑 `loading` / `empty` / `error` / `permission denied`

## 组件复用
- 优先复用现有组件系统
- 原始 HTML 表单控件只在没有共享组件时使用
- 新 UI 模式出现时，应优先判断是否可沉淀为组件或 prompt 模板

## 表单类任务最少要补齐的信息
- 字段的必填、只读、默认值
- 字段联动和禁用条件
- 提交前校验与提交后反馈
- 详情回填失败和权限不足时的表现

## 样式约束
- 优先使用现有 design token、CSS 变量、Tailwind 语义类
- 不要随意新增颜色、字号、间距体系
- 不要为了单一页面破坏全局样式约定

## 截图与验收意识
- 表单页至少要考虑 create、edit、view、validation-error、submit-success
- 列表页至少要考虑 loading、empty、error、filled

## 默认输出习惯
- 默认使用简体中文描述 UI 方案
- 组件名、类名、代码符号保留原始英文

## 使用边界
- 这里记录的是长期稳定的 UI 约定，不写一次性需求
- 如果某条规则只适用于单个业务页面，应放回具体 prompt，而不是写在这里
