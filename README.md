# AI Native Blueprint

这个目录不是一套泛化的 AI 工程概念库，而是一套围绕提示词工程落地的最小核心资产。

目标只有 4 个：

1. 沉淀高频任务的 Prompt 模板
2. 用 `SKILL` 压缩重复上下文，节约 token
3. 用 `context` 固化稳定背景，减少每次重复描述
4. 用 `changelog` 记录模板和 skill 的演进追溯

它基于你最近最典型的两类真实仓库场景整理：

- 产品端页面开发：中后台表单、列表页、详情页、仓库协作指南
- Agent / LLM 开发：prompt、parser、provider 约定容易漂移的代码仓库

## 核心目录

- `./prompts/`
  - 直接给 Codex 使用的任务模板
  - 只保留目标、变量位、强约束、输出格式
- `./skills/`
  - 固定高频流程，压缩重复 prompt
  - 重点不是“解释原理”，而是减少每次重复输入
- `./context/`
  - 存稳定事实，例如 UI 规则、API 约定、组件库、provider 约定、仓库事实
  - 这些内容应尽量长期稳定，避免写一次性需求
- `./request-templates/`
  - 每类高频任务对应一份“需求输入模板”
  - 每次需求直接复制并填写
- `./changelog/`
  - 记录 prompt、skill、context 的每次修改
  - 重点是为什么改、影响什么场景、是否影响旧调用方式
- `AGENTS.md`
  - 只做入口索引
  - 告诉 Codex 先读哪些 context、常用哪些 prompt、什么时候优先触发 skill

## 使用方式

1. 先把 `./context/` 填成当前仓库的真实事实
2. 再根据高频任务直接使用 `./prompts/`
3. 当同类任务重复 2 到 3 次以后，把重复说明压进 `./skills/`
4. 每次修改 prompt、skill、context 时，补一条 `./changelog/`

## 输入方式

不推荐作者手工维护一长串散变量。对于产品研发，尤其是 API 和表单类需求，变化最大的通常是任务描述本身，而不是规则骨架。

因此这套模板默认改成两段输入：

- `{{task_input}}`
  - 用来写这次需求的自由格式输入稿
- `{{extra_constraints}}`
  - 用来写额外约束，通常可留空

也就是说，稳定规则放在 `./context/` 和 `SKILL`，每次变化的需求内容只需要写一份“任务输入稿”。

推荐方式不是临时手写，而是直接引用 `./request-templates/` 下的模板来填写。

这个蓝图已经提供一个简单 CLI 样板：[ai-prompt.example.sh](/Users/lulin/codex/ai-native-blueprint/scripts/ai-prompt.example.sh)

常用方式：

```sh
./scripts/ai-prompt.sh list
./scripts/ai-prompt.sh brief admin-form
./scripts/ai-prompt.sh init admin-form --output ./requests/admin-form.md
./scripts/ai-prompt.sh vars admin-form
./scripts/ai-prompt.sh render admin-form --input ./request.md
./scripts/ai-prompt.sh run admin-form --input ./request.md
```

它会做几件事：

- `list`：列出所有 Prompt 模板
- `brief`：查看当前 Prompt 推荐的需求输入模板
- `init`：复制一份需求输入模板到本地文件
- `vars`：列出某个模板需要的变量
- `show`：直接查看模板原文
- `render`：把变量渲染进模板
- `run`：渲染后直接调用 `codex exec`

如果传了 `--input ./request.md`，CLI 会自动把文件内容填进 `{{task_input}}`。这样写作者只需要维护一份需求输入稿，不需要去记一堆变量名。

## Prompt 设计原则

- 模板只保留变量位和强约束，不重复背景解释
- 能放进 `context` 的内容，不写进用户 prompt
- 能放进 `skill` 的固定流程，不写进每次任务描述
- 输出格式要固定，减少模型发散
- 默认语言使用简体中文

## Token 节约原则

- 用户输入尽量只传业务变量，不重复仓库规则
- 仓库规则写进 `./context/`
- 高频流程写进 `./skills/`
- `AGENTS.md` 只做入口，不堆积长说明
- `changelog` 只做追溯，不承载新知识

## 推荐起步顺序

1. 先补齐 `./context/repo-facts.md`
2. 再补齐 `./context/ui-rules.md`、`./context/api-conventions.md`
3. 使用现成的 `admin-form.md`、`api-page.md`、`repo-guide.md`
4. 当某类任务稳定高频后，再启用对应 `SKILL.md`
5. 每次调整模板时，把变更写入 `changelog/`

## 关于其他目录

这个蓝图中可能还保留了一些更宽的实验性目录或旧草案，它们不是当前主路径。当前默认主路径只有：

- `./prompts/`
- `./skills/`
- `./context/`
- `./request-templates/`
- `./changelog/`
- `AGENTS.md`
