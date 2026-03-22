# Prompt 变更记录

按时间倒序记录 prompt 模板的修改。

## 模板
### YYYY-MM-DD `prompts/<name>.md`
- 变更原因：
- 变更内容：
- 影响场景：
- 依赖的 context：
- 注意事项：

## 示例
### 2026-03-22 `prompts/admin-form.md`
- 变更原因：中后台表单任务重复出现，原模板缺少权限与默认值输入位
- 变更内容：补充 `permissions`、`default_values`，强化字段联动和提交后行为约束
- 影响场景：后台页面、抽屉表单、弹窗表单
- 依赖的 context：`ui-rules.md`、`api-conventions.md`、`component-library.md`
- 注意事项：旧调用方式如果没有传权限信息，至少要明确是否存在禁用或只读逻辑
