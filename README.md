# REN

📫 731872977@qq.com

**Frontend Engineer → AI Application / Agent Platform Engineering**

`LLM Application`　`Agent Runtime`　`Streaming UI`　`Enterprise AI`

5 年前端工程经验，长期参与企业级 ERP、OA、业务管理系统开发。  
目前关注 AI 应用工程方向，探索如何将大模型能力融入真实产品：

不仅是调用模型 API，而是关注 AI 产品中的交互体验、运行状态管理、上下文治理以及系统集成。



---

## 我在做什么

| 方向 | 关注点 |
| --- | --- |
| **LLM Application** | 将模型能力封装为可交互、可维护的应用，而不是一次性的问答 Demo |
| **Agent Runtime** | 探索任务编排、工具调用、上下文管理以及 Agent 生命周期管理 |
| **Streaming UI** | SSE 事件流驱动前端状态管理，实现实时、可解释的 AI 交互体验 |
| **Enterprise AI** | 将 AI 能力结合企业系统中的权限、数据和业务流程 |

---

## 核心项目

## [agent-studio](https://github.com/novedu/agent-studio) · AI Agent Runtime 控制台

> 一个面向 Agent 应用开发的运行时控制台，用于观察和理解 Agent 执行过程。

通过统一运行状态模型，将 Chat、Graph、Timeline、Inspector 等多个视图连接起来，让 Agent 的执行过程更加透明。

### 运行时链路

```text
Planner
   ↓
Workflow Runner
   ↓
Tool Executor
   ↓
Context Manager
   ↓
Memory / Knowledge Retrieval
   ↓
Response Generation
   ↓
Evaluation
```

### 技术实践

- **Agent Runtime**
  - 设计任务执行流程，拆分 Planner、Tool、Runtime 等核心模块
  - 支持任务状态管理、执行过程追踪

- **Tool Calling**
  - 通过 Tool Registry 管理工具能力
  - 支持工具执行、异常处理以及结果回传

- **SSE Streaming**
  - 服务端推送运行事件
  - 前端通过状态管理同步展示 Agent 执行过程

- **Runtime State Model**
  - 设计统一运行状态模型
  - 避免聊天窗口、时间线、执行图之间的数据状态不一致

- **Observability**
  - 记录执行过程、耗时、事件轨迹
  - 辅助调试 Agent 行为

`TypeScript` `React` `Node.js` `SSE` `Agent Runtime` `Tool Calling` `RAG`

---

## [enterprise-admin-kit](https://github.com/novedu/enterprise-admin-kit) · Enterprise AI Platform

> 企业级中后台 + AI 应用控制平台探索。

将 AI 能力从页面中的单次调用抽离，通过 Runtime 层统一管理模型调用、上下文处理和业务能力。

### 分层设计

```text
Chat UI
   ↓
Chat Runtime
   ↓
Event Bus
   ↓
Provider
   ↓
Context Manager
   ↓
Prompt Engine
   ↓
Knowledge Layer
   ↓
Observability
```

### 技术实践

- **LLM Runtime**
  - 通过 Runtime 层管理 AI 对话生命周期
  - 使用事件驱动方式解耦 UI 与 AI 逻辑

- **Prompt Management**
  - 支持 Prompt 模板管理
  - 统一变量注入和调用流程

- **Knowledge Layer**
  - 探索文档切分、检索和知识引用展示

- **Provider 抽象**
  - 设计统一模型调用接口
  - 支持 OpenAI Compatible API 扩展

- **Enterprise Capability**
  - 结合企业系统经验设计 RBAC 权限模型
  - 支持路由、菜单、按钮、字段级权限控制

`Vue3` `TypeScript` `Enterprise AI` `RBAC` `LLM Runtime` `Prompt`

---

## 其他探索

## [spark-workshop](https://github.com/novedu/spark-workshop) · LLM 创意辅助应用

> 一个探索真实 LLM 应用流程的项目。

通过 OpenAI Compatible API，将大模型能力应用于创意生成和内容辅助流程。

### 技术实践

- **完整 AI Workflow**
  - 灵感输入
  - 方向生成
  - 内容规划
  - 编辑优化

- **LLM Integration**
  - 接入真实模型服务
  - 处理模型请求、响应以及错误情况

- **Human-in-the-loop**
  - AI 生成结果由用户确认后进入下一阶段
  - 保留人工决策流程

`Next.js` `React` `TypeScript` `LLM` `Prompt Engineering`

---

## 技术栈

**Frontend**

`TypeScript` `React` `Vue3` `Next.js` `Vite` `Pinia` `Zustand`

**AI Application**

`Agent` `Tool Calling` `RAG`  
`Prompt Engineering` `Context Management`  
`SSE Streaming` `LLM Application`

**Engineering**

`Node.js` `Express` `monorepo` `CI/CD` `Docker`

---

## 关于我

- **5 年前端开发经验**，主要参与企业级 ERP、OA、业务管理系统开发
- 正在探索 AI Application / Agent Platform Engineering 方向
- 关注方向：
  - Agent Runtime
  - AI 交互体验
  - Streaming UI
  - 企业 AI 应用

