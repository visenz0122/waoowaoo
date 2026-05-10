<h1 align="center">waoowaoo Personal Fork</h1>

<p align="center">
  我的 AI 视频生产工程化 fork：围绕 edit-first 生成链路、Agent 工作流、异步任务 runtime、provider adapter 与产品化交付做持续改造。
</p>

<p align="center">
  <a href="README_en.md">English</a> ·
  <a href="https://github.com/waooAI/waoowaoo">Original Project</a> ·
  <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY-NC-SA 4.0</a>
</p>

> [!IMPORTANT]
> 这是我的个人 fork 和作品集仓库。README 的重点是展示我在这个 fork 里沉淀的工程能力，而不是复述 upstream 项目介绍。<br>
> 为避免版权和归属问题，文末保留必要的来源与许可说明：本 fork 不是官方发布渠道，遵循 CC BY-NC-SA 4.0 的署名、非商业、相同方式共享要求。

---

## 我把这个 fork 当作什么来做

我把这个项目当作一个真实 AI 应用工程练习场，而不是只写一个 demo。重点不是“能不能调一次模型出结果”，而是把 AI 视频生成拆成可维护、可观察、可回归的工程链路：

- 从故事、分镜、镜头意图到视频生成的多阶段内容流
- 面向创作工作台的 edit-first 交互，而不是一次性黑盒生成
- Agent prompt workflow 与工具调用上下文的组织
- 图片、视频、配音等 AI provider 的 adapter 边界
- 任务提交、worker 执行、状态轮询、失败可见性与前端刷新
- 本地验证、回归测试、文档和作品集表达

所以这个 fork 在我的简历和主页里会被定位为：**AI 视频生产系统的个人 fork 与工程化实践项目**。

---

## 我在这个 fork 里展示的能力

### 1. Edit-first 视频生成链路

我关注的是让用户在时间线、分镜、镜头意图和生成结果之间来回编辑，而不是只提交一次 prompt。这个方向能体现前端工作台、状态管理、生成任务和结果回写之间的协作。

### 2. Agent workflow 与提示词工程

这个 fork 记录了我围绕时间线编辑 Agent、导演风格、镜头提示词和生成上下文做的调整。重点是让 Agent 产出的内容能进入真实业务链路，而不是停留在聊天窗口里。

### 3. 异步任务与 worker runtime

AI 视频/图片/语音生成天然是长任务。我把这个项目作为学习任务生命周期的样例：提交任务、写入记录、队列分发、worker 执行、轮询/事件同步、失败暴露与回滚边界。

### 4. 全栈工程协作

这个 fork 让我可以展示 Next.js 前端工作台、Prisma 数据层、Redis/BullMQ 队列、AI provider adapter、runtime 边界和测试验证之间如何串起来。这是我现在最想强化的方向：**AI 应用工程，而不是单点模型调用**。

## 主要修改方向

- 修复 edit-first 视频生成链路中的任务可靠性问题
- 优化时间线编辑 Agent 的提示词、上下文组织和回归问题
- 调整导演风格与镜头提示词，使分镜到视频生成的衔接更稳定
- 修复 workspace task polling 与运行时边界问题
- 梳理 Agent / operation / task / worker 的职责边界
- 将 README 和个人主页整理成适合简历、面试和公开作品集的表达

## 技术栈

- **框架**: Next.js 15 + React 19
- **数据库**: MySQL + Prisma ORM
- **队列**: Redis + BullMQ
- **样式**: Tailwind CSS v4
- **认证**: NextAuth.js
- **AI 链路**: provider adapter、任务队列、worker、SSE/状态轮询

---

## 本地开发

### 前提条件

- Node.js 版本以 `.nvmrc` 为准
- Docker Desktop
- 可用的 AI provider API Key

### 启动步骤

```bash
git clone https://github.com/visenz0122/waoowaoo.git
cd waoowaoo

cp .env.example .env
# 编辑 .env，填入需要的 AI API Key 和本地服务配置

npm install
docker compose up mysql redis minio -d
npx prisma db push
npm run dev
```

默认开发入口通常是：

- Web: <http://localhost:3000>
- Docker 组合服务入口可能使用仓库配置中的其他端口，请以 `docker-compose.yml` 和 `.env.example` 为准。

---

## 页面预览

![workspace canvas preview](workspace-canvas-edit-timeline-nodes.png)

![workspace board rendered](workspace-edit-first-board-rendered.png)

---

## 简历描述参考

可以将这个项目概括为：

> 个人 AI 视频生产系统 fork 与工程化实践项目。围绕 edit-first 视频生成、Agent prompt workflow、异步任务轮询、worker runtime 边界、provider adapter 与前端状态同步做功能修复和工程化梳理；使用 Next.js、Prisma、BullMQ、Redis 和多阶段 AI 内容生成链路实践 AI 应用工程。

---

## 来源与许可

- Original project: <https://github.com/waooAI/waoowaoo>
- Fork owner: <https://github.com/visenz0122>
- License: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International

本 fork 只作为个人学习、复盘、简历和作品集展示使用。为遵守原许可要求，这里保留 upstream 来源、许可证链接和非官方说明；未经原项目权利方授权，不应将本 fork 用于商业用途或作为官方发布版本分发。
