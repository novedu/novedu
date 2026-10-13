# REN

**Frontend Engineer → AI Application Engineering**

`LLM Application`　`Agent Runtime`　`Streaming UI`　`Enterprise AI`

5 年企业级前端开发经验（**ERP / OA** 等复杂业务系统），近一年聚焦 AI 应用工程。
做的事是把大模型能力接进真实业务——**运行时编排、流式交互、上下文治理、可观测性**，
而不只是调通一个 API。

📍 杭州　·　📫 731872977@qq.com
🎯 目标岗位：AI 应用工程师 · AI 前端工程师 · Agent 平台前端

---

## 5 年前端经验在 AI 应用里的作用

| 过去积累 | 在 AI 应用中的对应价值 |
|---|---|
| **ERP / OA 复杂业务系统** | 企业 AI 应用要嵌入审批流、权限体系、多角色视图——这是我一直在做的场景 |
| **复杂业务状态管理** | Agent 是多阶段长时运行任务，前端要处理流式事件、部分失败、重试、取消，状态复杂度远高于传统 CRUD |
| **前端工程化** | 类型系统、monorepo、CI、可观测性——决定 AI 应用停在原型，还是能交付 |
| **AI 应用工程（近一年）** | Agent Runtime 编排、Tool Calling、RAG、Prompt 工程、流式 UI |

## 我在做什么

| 方向 | 具体做的事 |
|---|---|
| **LLM Application** | 把模型能力做成有状态、可恢复的交互产品，而不是一次性问答 |
| **Agent Runtime** | 设计 Planner / Tool / RAG / Memory / Reflection / Evaluation 的编排与生命周期 |
| **Streaming UI** | SSE 事件流 → 前端状态机，让多个视图共享同一份运行时状态 |
| **Enterprise AI** | Provider 抽象、上下文治理、权限体系、可观测性 |

---

## 核心项目

### [agent-studio](https://github.com/novedu/agent-studio) · AI Agent Runtime 控制台

> 把 Agent 的规划、工具调用与反思过程，变成可观测、可解释的事件流。

运行时控制台。Chat / Graph / Timeline / Inspector 四个视图从**同一份运行时状态**投影出来，
呈现 Agent 从规划到评测的执行过程。

**运行时链路**

```text
Planner → WorkflowRunner → ToolExecutor → RAG → Memory → Reflection → Evaluator → Final Answer
```

**技术要点**

- **Agent Runtime** — 各阶段解耦、独立可观测；任务创建 / 查询 / 取消 / 重试
- **Tool Calling** — ToolRegistry 注册 + ToolExecutor 执行，含工具失败重试与降级链路
- **SSE Streaming** — 15 类运行时事件推送，前端状态机驱动多视图同步
- **RuntimeObject** — 统一投影模型，避免"时间线显示执行中、对话区显示已完成"的状态不一致
- **Observability** — trace / latency / token 三类指标

**实现边界（如实说明）**

- LLM 层支持接入任意 OpenAI 兼容模型（`OPENAI_API_KEY` / `OPENAI_BASE_URL`，含 tool calls 解析）；
  未配置时使用 Mock Provider，保证离线可演示
- RAG 当前为**内置示例知识库 + 关键词检索**，用于跑通链路；向量检索为下一步计划

`TypeScript` `React` `Node.js` `Agent Runtime` `SSE Streaming` `Tool Calling` `RAG` `Observability`

---

### [spark-workshop](https://github.com/novedu/spark-workshop) · 灵光一闪 AI 创意工坊

> 把「我有个想法」推进到「可以开书」，中间那段最费脑力的结构工程交给 AI 辅助。

**真实接入 LLM 的项目**：9 个服务端代理路由 + 完整 Prompt 模板库，通过 OpenAI 兼容网关调用模型，
API Key 只留在服务端。从一句话灵感出发，生成 3 个世界观方向，进入可编辑大纲，
再用理论引擎检测发现故事可能崩盘的地方。

- **服务端代理** — 前端不接触 API Key；支持 `LLM_USE_MOCK` 本地开发模式
- **理论诊断引擎** — 8 个可解释引擎，诊断结果引用具体字段作为证据，而非黑盒打分
- **人是决策者** — AI 生成的正文候选必须经作者采纳才写入；生成失败保留原稿，不用 mock 冒充

`Next.js` `React` `TypeScript` `LLM` `Prompt Engineering` `IndexedDB`

---

### [enterprise-admin-kit](https://github.com/novedu/enterprise-admin-kit) · 企业中后台 + AI Runtime

> Chat 只负责渲染状态，AI 行为由 Runtime 层承接。

面向 ERP / OA 类系统的中后台框架，加一层 LLM 运行时控制平面。
把 AI 从「写死在页面里的功能」变成「可配置、可调试的运行时模块」。

**分层架构**

```text
Chat UI → useChatRuntime → ChatRuntime → EventBus
        → Provider → Context Manager → Prompt Engine
        → Knowledge (RAG) → Observability
```

**技术要点**

- **LLM Runtime** — ChatRuntime 编排内核 + EventBus 事件驱动生命周期
- **Prompt** — 模板注册表、变量注入、渲染预览
- **RBAC** — 路由 / 菜单 / 按钮 / 字段四级权限控制
- **治理能力** — Context Manager 的 token 估算与压缩；RuntimeGuard 的超时、重试、熔断

**实现边界（如实说明）**

- Provider 层是**架构设计 + Mock / Stub 实现**（已定义能力契约与统一错误模型），
  **尚未接入真实模型**；真实 LLM 接入在 spark-workshop 与 agent-studio 中验证
- Knowledge 层为关键词检索的示例知识库

`Vue3` `TypeScript` `RBAC` `LLM Runtime` `Prompt` `Knowledge`

---

## 其他项目

- **[schemaCode](https://github.com/novedu/schemaCode)** — 企业级低代码表单运行时：多来源字段状态决策（`Permission > BPM > Rule > Schema`）/ 依赖图与规则调度 / Schema 版本冻结与数据迁移，含 OA 演示应用。**架构能力项目，与 AI 无关**　`Vue3` `TypeScript`
- **[World-Link-Alpha](https://github.com/novedu/World-Link-Alpha)** — Chrome 扩展 + 全栈后端的产品化探索：4 条 CI 流水线 / 13 个测试 / 30 篇产品文档。AI 辅助端点为本地启发式实现　`Chrome MV3` `Express` `Prisma`

---

## 技术栈

**前端**　`TypeScript` `React` `Vue 3` `Next.js` `Vite` `Pinia` `Zustand`

**AI 应用**　`Agent / Tool Calling` `RAG` `Prompt Engineering` `Context / Token 治理` `SSE Streaming` `LLM 可观测性`

**后端 & 工程化**　`Node.js` `Express` `Prisma` `monorepo` `CI/CD` `Docker`

---

## 关于我

- **5 年企业级前端开发经验**（ERP / OA 方向），转型 AI Application Engineering
- 关注方向：Agent Runtime、Streaming UI、LLM 可观测性
- 目标岗位：AI 应用工程师 · AI 前端工程师 · Agent 平台前端
- 目前在看机会，欢迎交流
