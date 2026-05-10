<h1 align="center">waoowaoo Personal Fork</h1>

<p align="center">
  My AI video production engineering fork: edit-first generation, Agent workflows, async task runtime, provider adapters, and product-grade delivery practice.
</p>

<p align="center">
  <a href="README.md">中文文档</a> ·
  <a href="https://github.com/waooAI/waoowaoo">Original Project</a> ·
  <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY-NC-SA 4.0</a>
</p>

> [!IMPORTANT]
> This is my personal fork and portfolio repository. The README focuses on the engineering work I practice in this fork, instead of retelling the upstream product introduction.<br>
> To avoid attribution and licensing issues, the source and license notice remain at the bottom: this fork is not an official release channel and follows CC BY-NC-SA 4.0 attribution, non-commercial, and share-alike requirements.

---

## How I Use This Fork

I use this project as a real AI application engineering workspace, not as a single-model demo. My focus is not "can one prompt call generate something", but whether the generation flow can be maintained, observed, tested, and explained:

- Multi-stage content flow from story, storyboard, shot intent, and video generation
- Edit-first creation UX instead of one-shot black-box generation
- Agent prompt workflow and tool context organization
- Provider adapter boundaries for image, video, and voice generation
- Task submission, worker execution, status polling, failure visibility, and frontend refresh
- Local verification, regression testing, documentation, and portfolio presentation

In my resume and GitHub profile, I position this repository as: **a personal fork and engineering practice project for an AI video production system**.

---

## What This Fork Demonstrates

### 1. Edit-first video generation

I focus on letting users move between timeline, storyboard, shot intent, and generated results, instead of submitting one prompt and waiting for a black-box result. This shows frontend workspace design, generation state management, task execution, and result writeback working together.

### 2. Agent workflow and prompt engineering

This fork records refinements around timeline-editing agents, director style, shot prompts, and generation context. The goal is to make Agent output usable inside the real product workflow, not only inside a chat window.

### 3. Async task and worker runtime

AI video, image, and voice generation are long-running tasks. I use this project to practice task lifecycle design: task submission, record creation, queue dispatch, worker execution, polling/event sync, failure visibility, and rollback boundaries.

### 4. Full-stack engineering coordination

This fork demonstrates how a Next.js workspace, Prisma data layer, Redis/BullMQ queues, AI provider adapters, runtime boundaries, and verification checks fit together. This is the direction I am currently building toward: **AI application engineering, not isolated model calls**.

## Main Work Areas

- Reliability fixes for edit-first video generation
- Prompt and context refinements for timeline editing agents
- Director-style prompt adjustments for smoother storyboard-to-video generation
- Workspace task polling and runtime boundary fixes
- Agent / operation / task / worker responsibility boundaries
- README and profile positioning for resume, interview, and portfolio use

---

## Tech Stack

- **Framework**: Next.js 15 + React 19
- **Database**: MySQL + Prisma ORM
- **Queue**: Redis + BullMQ
- **Styling**: Tailwind CSS v4
- **Auth**: NextAuth.js
- **AI Runtime**: provider adapters, task queue, workers, SSE / status polling

---

## Local Development

### Requirements

- Node.js version from `.nvmrc`
- Docker Desktop
- AI provider API keys

### Start Locally

```bash
git clone https://github.com/visenz0122/waoowaoo.git
cd waoowaoo

cp .env.example .env
# Edit .env and add the required AI API keys and local service config.

npm install
docker compose up mysql redis minio -d
npx prisma db push
npm run dev
```

The usual local development entry is:

- Web: <http://localhost:3000>
- Docker service ports may vary based on `docker-compose.yml` and `.env.example`.

---

## Preview

![workspace canvas preview](workspace-canvas-edit-timeline-nodes.png)

![workspace board rendered](workspace-edit-first-board-rendered.png)

---

## Resume Summary

Suggested summary:

> Personal AI video production system fork and engineering practice project. Worked on edit-first video generation, Agent prompt workflows, async task polling, worker runtime boundaries, provider adapters, and frontend state synchronization across a multi-stage AI content generation pipeline using Next.js, Prisma, BullMQ, Redis, and AI provider integrations.

---

## Attribution and License

- Original project: <https://github.com/waooAI/waoowaoo>
- Fork owner: <https://github.com/visenz0122>
- License: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International

This fork preserves attribution to the upstream project and marks personal modifications clearly. Without explicit permission from the original rights holders, this fork should not be used commercially or distributed as an official release.
