# Context 变更记录

按时间倒序记录 context 文件的修改。

## 模板
### YYYY-MM-DD `context/<name>.md`
- 变更原因：
- 新增事实：
- 删除事实：
- 影响的 prompt / skill：
- 注意事项：

## 示例
### 2026-03-22 `context/api-conventions.md`
- 变更原因：列表页和表单页反复需要说明分页与错误结构
- 新增事实：补充推荐分页字段、列表响应结构、写接口反馈关注点
- 删除事实：无
- 影响的 prompt / skill：`api-page.md`、`admin-form.md`、`api-page-builder`
- 注意事项：如果仓库实际接口字段不同，应以真实接口为准并同步更新这里
