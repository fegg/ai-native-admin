# Provider 约定

## 目标
统一模型调用、provider 选择、env 优先级和语法约束，避免 prompt 与实现漂移。

## 必须维护的信息
- 默认 provider：
- 默认 base URL：
- 默认模型：
- env key：
- env 优先级：
- 浏览器 / 服务端调用边界：
- 是否允许 fallback：

## 对 ReAct / agent 类任务的特别要求
- 最终答案语法只能有一种
- tool call 语法必须唯一且可解析
- 如果 prompt 格式变化，必须同步检查 parser

## 推荐补齐内容
- provider 初始化入口文件
- parser 或 loop 主入口文件
- 是否允许前端直连模型
- 模型切换时是否影响 tool 使用方式

## 禁止事项
- 不要在这里写未实现的 fallback 策略
- 不要让文档和代码各自描述不同的 provider 规则
