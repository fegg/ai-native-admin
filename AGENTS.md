# 仓库协作入口

本仓库的 AI 资产以提示词工程为核心，默认语言为简体中文。

优先读取：
- `./context/repo-facts.md`
- `./context/ui-rules.md`
- `./context/api-conventions.md`
- `./context/component-library.md`
- `./context/provider-conventions.md`

高频任务优先使用：
- `./prompts/admin-form.md`
- `./prompts/repo-guide.md`
- `./prompts/api-page.md`
- `./prompts/react-agent.md`

如果任务已经重复出现，优先触发对应 skill，而不是重新写长 prompt：
- `./skills/admin-form-builder/SKILL.md`
- `./skills/repo-guide-writer/SKILL.md`
- `./skills/api-page-builder/SKILL.md`
- `./skills/react-agent-prompt-updater/SKILL.md`

使用原则：
- 先引用 `context/`，再执行 `prompt/`
- `skill` 用来压缩重复上下文，减少 token
- `changelog/` 只记录变更追溯，不承载额外知识
- 不要在用户 prompt 中重复输入已经存在于 `./context/` 和 `./skills/` 的内容
