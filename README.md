# OpenClaw-Experience

![OpenClaw多Agent编排经验：派工、收包、权限与沉默排查](docs/assets/showcase/cover.png)

让长任务在后台执行，并把多个 worker 的结果可靠收回来。这里收录真实排查过程和两种 fan-in 路径。

**这是2026-04-03整理的案例记录。** 原文未固定所有适用版本；配置与权限行为需在自己的部署版本中验证，不能把示意图当作已替你修改配置。

[推荐正文](multi-agent/openclaw-multi-agent-orchestration-guide-v2.md) · [图文素材](docs/assets/showcase/README.md) · [初版存档](multi-agent/openclaw-multi-agent-orchestration-guide.md)

## 先看整个收包链路

![先看整个收包链路，流程示意而非运行截图](docs/assets/showcase/workflow.png)

direct collect 与消息回传是不同架构；跨会话读取涉及可见性和 agent-to-agent 两层权限。完整条件与报错原文保留在正文中。

[查看全部图片与来源](docs/assets/showcase/README.md)

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

## 更多项目

[A800 动量回测](https://github.com/wongzijie/stock_database) · [Spark Memory 设计](https://github.com/wongzijie/spark-memory) · [Snapshot 截图工具](https://github.com/wongzijie/Snapshot) · [Buffett Archive 本地检索](https://github.com/wongzijie/buffett-archive) · [相册快送](https://github.com/wongzijie/album-send)
