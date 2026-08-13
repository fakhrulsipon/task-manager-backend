# Task Manager — Real-time Project & Task Management Tool

A full-stack task/project management application (Trello-lite + real-time sync) built as a hands-on learning project to master **NestJS, Prisma, PostgreSQL, Redux Toolkit, WebSocket (Socket.io), and Docker/DevOps**.

## 🎯 Project Goals

This project is being built primarily as a **learning exercise**, covering:
- Backend API design with NestJS (Modules, Controllers, Services, DI)
- Database modeling & queries with Prisma ORM + PostgreSQL (Neon)
- Authentication with JWT
- Frontend state management with Redux Toolkit + RTK Query
- Real-time features using WebSocket / Socket.io
- Containerization with Docker & Docker Compose
- CI/CD with GitHub Actions and deployment (Vercel / Railway / Render)

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js, TypeScript, Redux Toolkit (RTK Query) |
| Backend | NestJS, TypeScript |
| Database | PostgreSQL (hosted on Neon) |
| ORM | Prisma |
| Real-time | Socket.io |
| Containerization | Docker, Docker Compose |
| CI/CD | GitHub Actions |
| Deployment | Vercel (frontend), Railway/Render (backend) |

## ✨ Planned Features

- **Auth** — Register/Login with JWT-based authentication
- **Workspaces** — Create and manage project workspaces
- **Tasks** — Create, update, assign, and track tasks (Todo / In Progress / Done)
- **Comments** — Comment on tasks
- **Real-time sync** — Live task updates across users via WebSocket
- **Notifications** — Real-time alerts when assigned a task

## 📁 Project Structure

```
task-manager/
├── backend/          # NestJS API
│   ├── prisma/
│   │   └── schema.prisma
│   ├── src/
│   └── .env
├── frontend/         # Next.js app
│   ├── src/
│   └── .env.local
└── docker-compose.yml
```

## 🗄️ Database Schema (Prisma Models)

- **User** — id, name, email, password, createdAt
- **Workspace** — id, name, ownerId
- **Task** — id, title, description, status, workspaceId, assignedToId
- **Comment** — id, content, taskId, userId

## 🚀 Getting Started

### Prerequisites
- Node.js (v18+)
- npm
- A [Neon](https://neon.tech) PostgreSQL database (or any PostgreSQL instance)
- Docker Desktop (for containerization steps)

### Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file inside `backend/` with your database connection string:

```
DATABASE_URL="postgresql://<user>:<password>@<host>/<dbname>?sslmode=require"
```

Run Prisma migrations to set up the database schema:

```bash
npx prisma migrate dev --name init
```

View your database visually:

```bash
npx prisma studio
```

Start the backend dev server:

```bash
npm run start:dev
```

### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

### Running with Docker (later stage)

```bash
docker-compose up --build
```

## 📚 Learning Log

| Day | Focus |
|---|---|
| 1 | PostgreSQL + Prisma basics, schema design |
| 2 | NestJS fundamentals (Module/Controller/Service, DI) |
| 3 | CRUD API — Workspace & Task endpoints |
| 4 | JWT Auth (register/login, guards) |
| 5 | Next.js basics, connecting to backend API |
| 6 | Redux Toolkit + RTK Query |
| 7 | WebSocket / Socket.io real-time features |
| 8 | Docker — Dockerfile for backend & frontend |
| 9 | Docker Compose — running full stack locally |
| 10 | CI/CD (GitHub Actions) + Deployment |

## 📝 Notes

This is a personal learning project. Scope is intentionally kept minimal (no drag-and-drop, file uploads, or email notifications) to focus on core backend, real-time, and DevOps concepts.

## 📄 License

MIT