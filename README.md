# REN

**Frontend Engineer → AI Application / Agent Platform Engineering**

`LLM Application`　`Agent Runtime`　`Streaming UI`　`Enterprise AI`

5 年前端工程经验。现在做的事是把大模型能力**工程化**——
不是调通一个 API，而是让它在真实产品里**可靠、可观测、可交付**。

📍 杭州　·　📫 731872977@qq.com

---

## 我在做什么

| 方向 | 具体做的事 |
|---|---|
| **LLM Application** | 把模型能力做成有状态、可恢复、可交付的产品，而不是一次性问答 |
| **Agent Runtime** | 设计 Planner / Tool / RAG / Memory / Reflection / Evaluation 的编排与生命周期 |
| **Streaming UI** | SSE 事件流 → 前端状态机，让多个视图共享同一份运行时状态 |
| **Enterprise AI** | Provider 抽象、上下文治理、权限体系、可观测性——让 AI 能真正进企业系统 |

---

## 核心项目

### [agent-studio](https://github.com/novedu/agent-studio) · AI Agent Runtime 控制台

> 把 Agent 的每一个决策，变成可观测、可解释的事件流。

IDE 级别的运行时控制台。Chat / Graph / Timeline / Inspector 四个视图
从**同一份运行时状态**投影出来，完整呈现 Agent 从规划到评测的全过程。

**运行时链路**

```text
Planner → WorkflowRunner → ToolExecutor → RAG → Memory → Reflection → Evaluator → Final Answer
```

**技术要点**

- **Agent Runtime** — 各阶段解耦、独立可观测；任务创建 / 查询 / 取消 / 重试
- **Tool Calling** — ToolRegistry 注册 + ToolExecutor 执行，工具失败重试与降级链路
- **RAG** — 文档分块、检索召回、引用溯源，结果作为上下文回灌
- **SSE Streaming** — 15 类运行时事件实时推送，前端状态机驱动多视图同步
- **Observability** — trace / latency / token 三类指标贯穿全链路
- **RuntimeObject** — 统一投影模型，消除"时间线显示执行中、对话区显示已完成"这类不一致

`TypeScript` `React` `Node.js` `Agent Runtime` `SSE Streaming` `Tool Calling` `RAG` `Observability`

---

### [enterprise-admin-kit](https://github.com/novedu/enterprise-admin-kit) · Enterprise AI Platform

> Chat 只负责渲染状态，AI 行为全部由 Runtime 层承接。

企业级中后台 + LLM 应用控制平面。把 AI 从「写死在页面里的功能」
变成「可配置、可调试、可观测的运行时系统」。

**分层架构**

```text
Chat UI → useChatRuntime → ChatRuntime → EventBus
        → Provider → Context Manager → Prompt Engine
        → Knowledge (RAG) → Observability
```

**技术要点**

- **LLM Runtime** — ChatRuntime 编排内核 + EventBus 事件驱动生命周期
- **Prompt** — 模板注册表、变量注入、渲染预览
- **Knowledge** — 文档分块、关键词检索、引用展示，作为 RAG 知识层
- **RBAC** — 路由 / 菜单 / 按钮 / 字段四级权限控制
- **Provider 抽象** — 多模型切换、能力契约、统一错误模型（OpenAI / Claude / Qwen / DeepSeek）
- **治理能力** — Context Manager 的 token 估算与压缩；RuntimeGuard 的超时、重试、熔断

`Vue3` `TypeScript` `Enterprise AI Platform` `RBAC` `LLM Runtime` `Prompt` `Knowledge`

---

## 其他探索

### [spark-workshop](https://github.com/novedu/spark-workshop) · 灵光一闪 AI 创意工坊

> 把「我有个想法」推进到「可以开书」，中间那段最费脑力的结构工程交给 AI 辅助。

**唯一接入真实 LLM 的项目**（OpenAI 兼容网关，服务端代理）。从一句话灵感出发，
生成 3 个世界观方向，进入可编辑大纲，再用理论引擎检测发现故事可能崩盘的地方。

- **完整链路** — 灵感引爆 → 世界观方案 → 卷纲 → 世界状态 → 前 30 章节奏表 → 正文试写
- **理论诊断引擎** — 8 个可解释引擎，诊断结果**引用具体字段作为证据**，而非黑盒打分
- **人是决策者** — AI 生成的正文候选必须经作者采纳才写入；失败保留原稿，绝不用 mock 冒充

`Next.js` `React` `TypeScript` `LLM` `Prompt Engineering` `IndexedDB`

---

## 技术栈

**前端**　`TypeScript` `React` `Vue 3` `Next.js` `Vite` `Pinia` `Zustand`

**AI 应用**　`Agent / Tool Calling` `RAG` `Prompt Engineering`
`Context / Token 治理` `SSE Streaming` `LLM Observability`

**后端 & 工程化**　`Node.js` `Express` `Prisma` `monorepo` `CI/CD` `Docker`

---

## 关于我

- **5 年前端开发经验**，转型 AI Application / Agent Platform Engineering
- 相信模型能力会越来越便宜，**把它变成可靠产品的工程能力不会**
- 关注方向：Agent Runtime、Streaming UI、LLM 可观测性
- 目前在看机会，欢迎交流
