# ReAct / Agent Prompt 更新模板

你要更新一个 ReAct 风格 agent 的 prompt 或循环逻辑。

## 在开始前先读取
- `.ai/context/repo-facts.md`
- `.ai/context/provider-conventions.md`
- `AGENTS.md`
- 当前 prompt 文件
- 当前 parser 文件
- 当前 tool registry 文件

## 任务输入
{{task_input}}

## 可选补充约束
{{extra_constraints}}

## 强约束
- 最终答案语法只能保留一种
- tool call 语法必须保持 parser 可解析
- 如果 prompt 格式改了，必须明确指出 parser 是否要同步调整
- 如果 provider 行为改了，必须对齐 `.ai/context/provider-conventions.md`
- 如果存在旧格式兼容负担，必须明确迁移策略
- 默认输出使用简体中文

## 输出格式
1. 当前漂移点
2. 建议的新 prompt
3. parser 影响分析
4. tool 调用影响分析
5. 变更风险
6. 需要更新的文档与 changelog

## 编写任务输入时建议至少包含
- 当前 prompt / parser / tools / provider 文件位置
- 当前语法事实
- 想要的目标改动
- 是否要求兼容旧格式
- 当前最担心的漂移点

## 禁止事项
- 不要同时保留多种 finish 语法
- 不要只改 prompt 不分析 parser
