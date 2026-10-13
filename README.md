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
| AI 应用停在原型、无法交付 | 类型系统 + monorepo + CI，**按可交付标准做** |

---

## 🚀 精选项目

### [Agent-Demo](https://github.com/novedu/Agent-Demo) · AI Agent Runtime 控制台

> 把 Agent 的每一个决策，变成可观测、可解释的事件流。

一个 IDE 级别的运行时控制台。Chat / Graph / Timeline / Inspector 四个视图
从同一份运行时状态投影出来，完整呈现 Agent 从规划到评测的全过程。

**核心设计**

- **运行时生命周期**：Planner → WorkflowRunner → ToolExecutor → RAG → Memory
  → Reflection → Evaluator → Final Answer，各阶段解耦、独立可观测
- **统一投影模型**：定义 RuntimeObject，四个视图不再各自维护状态，
  从根上消除"时间线显示还在执行、对话区已显示完成"这类不一致
- **流式事件系统**：基于 SSE 推送 15 类运行时事件
  （`plan_update` / `tool_start` / `rag_retrieve` / `reflection` / `evaluation_complete` …）
- **可靠性链路**：工具调用失败重试与降级，支持任务取消与重试；
  完整演示 Tool Error → Retry → Reflection → Success
- **可观测性**：trace、latency、token 三类指标贯穿全链路

**工程化**　monorepo（2 app + 3 package）｜ CI 三阶段（lint / test / build）｜
12 篇设计文档 ｜ MIT

`React` `TypeScript` `Node.js` `Zustand` `SSE` `npm workspaces`

---

### [enterprise-admin-kit](https://github.com/novedu/enterprise-admin-kit) · 企业级中后台 + LLM 应用控制平面

> Chat 只负责渲染状态，AI 行为全部由 Runtime 层承接。

把 AI 从"写死在页面里的功能"变成"可配置、可调试、可观测的运行时系统"。

**AI Runtime 分层**

```text
Chat UI → useChatRuntime → ChatRuntime → EventBus
        → Provider → Context Manager → Prompt Engine
        → Knowledge (RAG) → Observability
```

- **Provider 抽象**：多模型切换，能力契约与统一错误模型
  （OpenAI / Claude / Qwen / DeepSeek，附 Mock Provider 支持离线运行）
- **Context 治理**：token 估算与压缩策略，让上下文成本可控
- **Prompt 引擎**：模板注册表 + 变量注入 + 渲染预览
- **知识层**：文档分块、检索召回、引用溯源
- **RuntimeGuard**：状态机校验、超时、重试、Token 限额、熔断
- **可观测性**：trace 采集、事件时间线、token 监控、延迟统计

**工程化**　RBAC 四级权限（路由 / 菜单 / 按钮 / 字段）｜ schema 驱动表单 ｜
Axios 重试与错误拦截 ｜ 双语 i18n ｜ MIT

`Vue 3` `TypeScript` `Element Plus` `UnoCSS` `Pinia`

---

## 🛠 技术栈

**前端**　`TypeScript` `React` `Vue 3` `Vite` `Pinia` `Zustand` `Element Plus` `UnoCSS`

**AI 应用**　`Agent / Tool Calling` `RAG` `Prompt Engineering`
`Context / Token 治理` `SSE 流式` `LLM 可观测性`

**工程化**　`monorepo` `CI/CD` `ESLint / Prettier` `Type-safe API`

---

## 📌 关于我

- **5 年前端开发经验**，专注前端工程化与复杂交互系统
- 关注方向：AI 应用工程、Agent 平台、LLM 可观测性
- 相信模型能力会越来越便宜，**把它变成可靠产品的工程能力不会**
- 目前**在看机会**，欢迎交流 👋

<sub>⭐ 如果我的项目对你有帮助，欢迎 star 或提 issue 交流。</sub>
