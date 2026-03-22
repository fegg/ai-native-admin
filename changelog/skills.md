# Skill 变更记录

按时间倒序记录 skill 的修改。

## 模板
### YYYY-MM-DD `skills/<name>/SKILL.md`
- 变更原因：
- 变更内容：
- token 节约点：
- 影响场景：
- 注意事项：

## 示例
### 2026-03-22 `skills/admin-form-builder/SKILL.md`
- 变更原因：同类表单任务重复出现，用户 prompt 中反复描述相同 UI 和 API 规则
- 变更内容：把字段梳理、组件映射、状态覆盖、输出格式固化到 skill
- token 节约点：用户只需提供业务字段和接口变量，不再重复解释共享组件、异常态和输出结构
- 影响场景：中后台 create/edit/view 表单
- 注意事项：仓库如果尚未统一组件库，需要先补 `component-library.md`
