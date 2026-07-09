# Morphix AI

A production-ready generative media platform that enables users to create AI-generated images, videos, and face swaps through a modern web application.

Morphix AI combines AI-powered media generation, secure authentication, scalable object storage, and a production-ready infrastructure into a single platform designed for creators and developers.

---

## Features

Users can sign in and:

- Generate AI images from text prompts
- Generate AI videos from text prompts
- Perform AI-powered face swaps
- Manage generated media from a personal gallery
- Download generated assets
- View generation history
- Manage account settings and usage
- Purchase and manage credits _(planned)_

Image and video generation are powered by AI providers through a unified API layer, while face swapping is handled by a self-hosted FaceFusion service. Uploaded assets and generated media are stored in an S3-compatible object store.

---

## Architecture

This repository is a Turborepo monorepo managed with Bun.

| Path                         | Description                                                   |
| ---------------------------- | ------------------------------------------------------------- |
| `apps/frontend`              | Next.js + TypeScript frontend application                     |
| `apps/backend`               | Express API, authentication, AI services, storage integration |
| `packages/db`                | Prisma schema and shared database client                      |
| `packages/ui`                | Shared UI components                                          |
| `packages/types`             | Shared TypeScript types                                       |
| `packages/eslint-config`     | Shared ESLint configuration                                   |
| `packages/typescript-config` | Shared TypeScript configuration                               |

---

## Infrastructure

The development environment consists of the following services.

| Service     | Purpose                       |
| ----------- | ----------------------------- |
| PostgreSQL  | Primary relational database   |
| MinIO       | S3-compatible object storage  |
| FaceFusion  | Self-hosted face swap service |
| Express API | Backend application           |
| Next.js     | Frontend application          |

---

## Technology Stack

### Frontend

- Next.js
- React
- TypeScript
- Tailwind CSS
- shadcn/ui
- Framer Motion

### Backend

- Express
- TypeScript
- Better Auth
- Prisma ORM

### Database

- PostgreSQL

### AI Services

- OpenRouter
- FaceFusion

### Storage

- MinIO (S3 Compatible)

### Infrastructure

- Docker
- Docker Compose
- Turborepo
- Bun

---

## Prerequisites

Before getting started, ensure the following software is installed.

- Docker
- Docker Compose
- Bun ≥ 1.3
- Node.js ≥ 22

---

## Quick Start

### 1. Configure the environment

```bash
cp .env.example .env
```

Configure the required environment variables.

---

### 2. Install dependencies

```bash
bun install
```

---

### 3. Start the development environment

```bash
bun run docker:up
```

---

### 4. Access the application

Frontend

```
http://localhost:3000
```

Backend

```
http://localhost:4000
```

Object Storage Console

```
http://localhost:9001
```

---

## Local Development

Run infrastructure services.

```bash
bun run infra:up
```

Install dependencies.

```bash
bun install
```

Generate the Prisma client.

```bash
bun run db:generate
```

Apply database schema.

```bash
bun run db:push
```

Start the development servers.

```bash
bun run dev
```

---

## Environment Variables

Create a `.env` file and configure the required variables.

```env
DATABASE_URL=

BETTER_AUTH_SECRET=

OPENROUTER_API_KEY=

GOOGLE_CLIENT_ID=

GOOGLE_CLIENT_SECRET=

MINIO_ENDPOINT=

MINIO_ACCESS_KEY=

MINIO_SECRET_KEY=

FACEFUSION_URL=
```

---

## Available Scripts

| Command                | Description                            |
| ---------------------- | -------------------------------------- |
| `bun run dev`          | Start all development servers          |
| `bun run build`        | Build all applications                 |
| `bun run check-types`  | Run TypeScript checks                  |
| `bun run docker:up`    | Build and start the Docker environment |
| `bun run docker:down`  | Stop all containers                    |
| `bun run docker:reset` | Remove containers and volumes          |
| `bun run infra:up`     | Start infrastructure services          |
| `bun run db:generate`  | Generate Prisma client                 |
| `bun run db:push`      | Synchronize schema                     |
| `bun run db:migrate`   | Run database migrations                |
| `bun run db:studio`    | Open Prisma Studio                     |

---

## Project Structure

```text
morphix-ai
├── apps
│   ├── frontend
│   └── backend
│
├── packages
│   ├── db
│   ├── ui
│   ├── types
│   ├── eslint-config
│   └── typescript-config
│
├── docker
├── docs
├── .github
├── docker-compose.yml
├── package.json
├── turbo.json
└── README.md
```

---

## Roadmap

### Version 1

- Authentication
- AI Image Generation
- AI Video Generation
- Face Swap
- Gallery
- User Dashboard

### Version 2

- Credits System
- Payments
- Admin Dashboard
- Usage Analytics
- Team Workspaces

### Version 3

- AI Image Editing
- Background Removal
- Upscaling
- Prompt Templates
- Public API

---

## Documentation

Additional documentation will be available in the `docs` directory.

- Architecture
- API Reference
- Database Design
- Deployment Guide
- Security
- Contributing

---

## License

This project is licensed under the MIT License.
