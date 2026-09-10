# ArchGuard Evals

与 Agent 框架解耦的版本化评估数据集、评分器、回归比较和安全测试仓库。

## 当前状态

阶段 0 `v0.1.0-foundation` 正在远端收口。本仓库在阶段 6 `v0.7.0-evals` 使用 Python 正式启用；阶段 4 起只积累脱敏、版本化案例。运行器、数据集、评分器和首个评估基线尚未实现，也不参与线上核心请求。

## 职责

- 维护任务成功、工具选择、参数、引用、误报、成本和延迟评估。
- 覆盖提示注入、越权、敏感信息泄漏和无限循环等安全场景。
- 对模型、Prompt、工具或规则变更生成可复现的候选与基线报告。
- 将脱敏后的生产失败转化为版本化回归用例。

## 非职责

- 不实现生产 Agent、Platform、Scanner 或 MCP Gateway。
- 不包含真实客户源码、个人数据、Token 或未经脱敏的生产记录。
- 不通过放宽评分、删除失败样例或隐藏波动来制造通过结果。
- 不把主观 LLM 判断作为确定性规则的替代。

## 依赖与契约

- 通过公开、版本化的工具与输出 Schema 评估候选系统。
- 数据集与评分器避免绑定单一模型供应商或 Agent 框架。
- 跨仓库架构与工程规范以 [archguard-docs](https://github.com/AI-ArchGuard/archguard-docs) 为准。

## 本地验证

当前基线可执行：

```bash
git diff --check
git status --short
```

Python 运行器尚未选型。选型和依赖经记录后，README 将补充唯一的完整评估命令；当前不得假定 `pytest` 已可用。

## 许可证

本仓库采用 [Apache License 2.0](LICENSE)。
