<p align="center">
  <img src="public/banner.png" alt="waoowaoo personal fork" width="600">
</p>

<h1 align="center">waoowaoo Personal Fork</h1>

<p align="center">
  Engineering practice around an AI video production platform: agent workflows, edit-first generation, async tasks, worker runtime boundaries, and full-stack product delivery.
</p>

<p align="center">
  <a href="README.md">中文文档</a> ·
  <a href="https://github.com/waooAI/waoowaoo">Original Project</a> ·
  <a href="https://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY-NC-SA 4.0</a>
</p>

> [!IMPORTANT]
> This repository is my personal fork of `waooAI/waoowaoo`. It is used as an engineering portfolio and learning record for internship/project work, including fixes, workflow refinements, and AI application engineering practice.<br>
> This fork is not the official waoowaoo release channel and does not represent the original team's commercial product or roadmap. Original copyright and branding belong to the upstream maintainers. This fork follows the original CC BY-NC-SA 4.0 license: attribution, non-commercial use, and share-alike distribution.

---

## Project Context

`waoowaoo` is an AI film / short drama / comic-video production platform. The core workflow includes:

- Story and script analysis
- Character, scene, and prop asset generation
- Storyboard, narration, visual prompt, and shot planning
- AI provider calls for image, video, and voice generation
- Async task processing, progress events, recovery, and frontend sync
- Timeline editing and final video production

This fork is focused on recording practical engineering work in a real AI application system, not on republishing the official product.

---

## My Engineering Focus

This branch records work around:

- Reliability fixes for edit-first video generation
- Prompt and context refinements for timeline editing agents
- Director-style prompt adjustments for smoother storyboard-to-video generation
- Workspace task polling and runtime boundary fixes
- Agent / operation / task / worker responsibility boundaries
- Local verification notes for async generation flows

The repository is best understood as a portfolio sample for AI application engineering, agent workflows, async task systems, and full-stack collaboration.

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

> This fork is intended for study, review, and portfolio display. For the official project, see:<br>
> <https://github.com/waooAI/waoowaoo>

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

> Personal fork and engineering practice based on the open-source AI video production platform waoowaoo. Worked on edit-first video generation, agent prompt workflows, async task polling, worker runtime boundaries, and frontend state synchronization across a multi-stage AI content generation pipeline using Next.js, Prisma, BullMQ, and AI provider adapters.

---

## Attribution and License

- Original project: <https://github.com/waooAI/waoowaoo>
- Fork owner: <https://github.com/visenz0122>
- License: Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International

This fork preserves attribution to the upstream project and marks personal modifications clearly. Without explicit permission from the original rights holders, this fork should not be used commercially or distributed as an official release.
