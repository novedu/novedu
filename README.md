# 你好，我是 REN 👋

**5 年前端工程师 → AI 应用 / Agent 平台方向**　｜　📍 杭州　｜　📫 731872977@qq.com

> 大多数 AI 应用 demo 止步于一个对话框，我更关心它背后的东西：
> **运行时编排、上下文治理、事件流、可观测性**，以及一个能让人真正看懂
> Agent 在想什么的界面。
>
> 我的定位是 **把大模型能力工程化**——不是"调通 API"，而是让它可靠、可观测、可交付。

*Frontend engineer moving into AI application engineering. I build the runtime,
streaming and observability layer around LLMs, plus the console that makes it debuggable.*

---

## 🎯 我在解决什么问题

| 真实问题 | 我的做法 |
|---|---|
| Agent 是黑盒，出错无法定位 | 把每次规划、工具调用、检索、反思都变成**结构化运行时事件** |
| 多视图状态不同步 | **RuntimeObject 统一投影模型**，四个视图共享同一份状态 |
| 模型能力各异、错误码不统一 | Provider 抽象层 + **能力契约 + 错误归一化** |
| 上下文窗口有限且昂贵 | Context Manager 做 **token 估算与压缩策略** |
| 表单字段状态来源混乱 | **多来源状态决策引擎**，显式建模 Permission > BPM > Rule > Schema |
| AI 应用停在原型、无法交付 | 类型系统 + monorepo + CI，**按可交付标准做** |

---

## 🚀 精选项目

### [Agent-Demo](https://github.com/novedu/Agent-Demo) · AI Agent Runtime 控制台

> 把 Agent 的每一个决策，变成可观测、可解释的事件流。

IDE 级别的运行时控制台。Chat / Graph / Timeline / Inspector 四个视图从同一份运行时状态投影出来，完整呈现 Agent 从规划到评测的全过程。

- **运行时生命周期**：Planner → WorkflowRunner → ToolExecutor → RAG → Memory → Reflection → Evaluator → Answer
- **统一投影模型**：RuntimeObject 让四视图共享状态，消除"时间线显示执行中、对话区显示已完成"这类不一致
- **流式事件**：SSE 推送 15 类运行时事件，含工具失败重试与降级链路
- **工程化**：monorepo（2 app + 3 package）· CI 三阶段 · 12 篇设计文档

`React` `TypeScript` `Node.js` `Zustand` `SSE`

### [spark-workshop](https://github.com/novedu/spark-workshop) · 灵光一闪 AI 创意工坊

> 把「我有个想法」推进到「可以开书」，中间那段最费脑力的结构工程交给 AI 辅助。

AI 驱动的网文写作辅助工具，**接入真实 LLM**（OpenAI 兼容网关，服务端代理）。

- **完整链路**：灵感引爆 → 世界观方案 → 卷纲 → 世界状态 → 前 30 章节奏表 → 正文试写
- **理论诊断引擎**：8 个可解释的理论引擎，检测结果**引用具体字段作为证据**，而非黑盒打分
- **人是决策者**：AI 生成的正文候选必须经作者采纳才写入，失败保留原稿，绝不用 mock 冒充
- **本地优先**：数据存 IndexedDB；世界状态按章节确认写入，后续生成只读已确认事件

`Next.js` `React` `TypeScript` `LLM` `Prompt Engineering` `IndexedDB`

### [enterprise-admin-kit](https://github.com/novedu/enterprise-admin-kit) · 企业级中后台 + LLM 应用控制平面

> Chat 只负责渲染状态，AI 行为全部由 Runtime 层承接。

把 AI 从"写死在页面里的功能"变成"可配置、可调试、可观测的运行时系统"。

- **Provider 抽象**：多模型切换、能力契约、统一错误模型（OpenAI / Claude / Qwen / DeepSeek + Mock）
- **Context 治理**：token 估算与压缩策略
- **RuntimeGuard**：状态机校验、超时、重试、Token 限额、熔断
- **可观测性**：trace 采集、事件时间线、token 监控、延迟统计

`Vue 3` `TypeScript` `Element Plus` `UnoCSS` `RBAC`

### [World-Link-Alpha](https://github.com/novedu/World-Link-Alpha) · 世界观采集与管理工具

> 划词右键，把网页上的「矿石 / 势力 / 地名」直接变成结构化实体。

Chrome Extension（Manifest V3）+ 全栈后端，含完整工程治理。

- **关键数据模型**：`BookEntityUsage` 把「世界级资产」与「书级使用视图」解耦，一份设定服务多本书
- **4 条 CI 流水线**：主流水线 / 校验 / 安全扫描 / 发布门禁
- **13 个测试文件**分层覆盖：契约、功能、E2E 核心链路、权益边界
- **30 篇文档**：PRD、竞品分析、测试策略、指标口径字典，含文档一致性 CI 门禁

`Chrome Extension` `React` `Express` `Prisma` `JWT` `Docker`

### [schemaCode](https://github.com/novedu/schemaCode) · mini-form-engine 低代码表单引擎

> 把「表单长什么样」交给 Schema，把「字段此刻能不能编辑」交给状态决策引擎。

- **多来源状态决策**：显式建模优先级 `Permission > BPM > Rule > Schema`，仲裁产出最终 FieldState
- **依赖图与规则调度**：拓扑排序求值，只重算受影响字段
- **Schema 版本冻结**：历史任务永远打开它创建时那一版
- **数据迁移管线**：Validation → Report → Dry Run → Execution（含 Operation Log）
- **26 个测试文件**；引擎本体零 UI 依赖，UI 通过 ComponentMap 注入

`Vue 3` `TypeScript` `Vite` `Element Plus` `node:test`

---

## 🛠 技术栈

**前端**　`TypeScript` `React` `Vue 3` `Next.js` `Vite` `Pinia` `Zustand` `Element Plus`

**AI 应用**　`Agent / Tool Calling` `RAG` `Prompt Engineering`
`Context / Token 治理` `SSE 流式` `LLM 可观测性`

**后端 & 工程化**　`Node.js` `Express` `Prisma` `monorepo` `CI/CD` `Docker`

---

## 📌 关于我

- **5 年前端开发经验**，专注前端工程化与复杂交互系统
- 关注方向：AI 应用工程、Agent 平台、LLM 可观测性
- 相信模型能力会越来越便宜，**把它变成可靠产品的工程能力不会**
- 目前**在看机会**，欢迎交流 👋

<sub>⭐ 如果我的项目对你有帮助，欢迎 star 或提 issue 交流。</sub>
