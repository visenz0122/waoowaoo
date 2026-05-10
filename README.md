<p align="center">
  <img src="public/banner.png" alt="waoowaoo personal fork" width="600">
</p>

<h1 align="center">waoowaoo Personal Fork</h1>

<p align="center">
  AI 影视生产平台工程化实践：围绕短剧/漫画视频生成链路、Agent 工作流、异步任务与编辑优先体验的个人二次开发版本。
</p>

<p align="center">
  <a href="README_en.md">English</a> ·
  <a href="https://github.com/waooAI/waoowaoo">Original Project</a> ·
  <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY-NC-SA 4.0</a>
</p>

> [!IMPORTANT]
> 这是 `waooAI/waoowaoo` 的个人 fork，用于记录我在实习/项目协作中的工程化理解、功能修复和二次开发实践。<br>
> 本仓库不是 waoowaoo 官方发布渠道，也不代表原团队的商业版本或官方路线图。原项目版权与品牌归原项目维护者所有，本 fork 遵循原仓库的 CC BY-NC-SA 4.0 许可要求：署名、非商业、相同方式共享。

---

## 项目定位

`waoowaoo` 是一个面向 AI 影视/短剧/漫画视频生产的全流程平台。核心链路覆盖：

- 小说/故事输入与剧本结构化分析
- 角色、场景、道具等资产生成与管理
- 分镜、画面描述、旁白与镜头规划
- 图片/视频/配音等 AI provider 调用
- 异步任务、进度事件、失败恢复与前端状态同步
- 时间线编辑与最终视频产出

这个 fork 的重点不是重新发布官方产品，而是沉淀我在真实工程项目里做过的 AI 应用工程实践。

---

## 我的工程化改造重点

我在这个分支里主要围绕以下方向做了修改和验证：

- 修复 edit-first 视频生成链路中的任务可靠性问题
- 优化时间线编辑 Agent 的提示词、上下文组织和回归问题
- 调整导演风格与镜头提示词，使分镜到视频生成的衔接更稳定
- 修复 workspace task polling 与运行时边界问题
- 梳理 Agent/operation/task/worker 之间的职责边界
- 结合本地验证记录补充对异步任务链路的工程理解

这些内容更适合作为 AI 应用工程、Agent workflow、异步任务系统和全栈工程协作的实践样例，而不是作为独立商业产品宣传。

---

## 技术栈

- **框架**: Next.js 15 + React 19
- **数据库**: MySQL + Prisma ORM
- **队列**: Redis + BullMQ
- **样式**: Tailwind CSS v4
- **认证**: NextAuth.js
- **AI 链路**: provider adapter、任务队列、worker、SSE/状态轮询

---

## 本地开发

> 本 fork 面向学习、复盘和作品集展示。若你只想体验官方版本，请优先查看原项目：<br>
> <https://github.com/waooAI/waoowaoo>

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

> 基于开源 AI 影视生产平台 waoowaoo 的个人 fork 与工程化实践，重点参与 edit-first 视频生成、Agent prompt workflow、异步任务轮询、worker runtime 边界与前端状态同步等链路修复；在真实项目中实践 Next.js、Prisma、BullMQ、AI provider adapter 与多阶段内容生成流程。

---

## 来源与许可

- Original project: <https://github.com/waooAI/waoowaoo>
- Fork owner: <https://github.com/visenz0122>
- License: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International

本 fork 保留原项目署名，并标明本仓库包含个人二次开发改动。未经原项目权利方授权，不应将本 fork 用于商业用途或作为官方发布版本分发。
