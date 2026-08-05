# OpenClaw-Experience

OpenClaw 中使用经验分享。记录真实踩坑过程、根因定位与可复用配置。

## 文档索引

### 多 Agent 编排

| 文档 | 说明 | 状态 |
| :--- | :--- | :--- |
| [OpenClaw 多 Agent 编排经验书](./multi-agent/openclaw-multi-agent-orchestration-guide-v2.md) | orchestrator 驱动多个 specialist subagent 的完整工程经验：后台执行架构、跨 agent 权限的两道门、fan-in 的两种方案、worker 沉默的诊断框架 | **推荐阅读** |
| [初版（存档）](./multi-agent/openclaw-multi-agent-orchestration-guide.md) | 同一份内容的初版排版，保留供对照 | 存档 |

## 这里能解决什么问题

- orchestrator 读不到 specialist 的 session history，报 `visibility is restricted` 或 `agent-to-agent history is disabled`
- 配置文件明明改了，当前会话却还在报旧错误
- 多个 worker 里偏偏有一个不回包，反复催办无效
- 长任务被单次响应窗口打断，做不完也回不来

## 约定

- 所有配置片段默认指向 `~/.openclaw/openclaw.json`
- 报错原文照抄，不做转述，方便直接搜索匹配
