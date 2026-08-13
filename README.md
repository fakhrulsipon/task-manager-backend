# Task Manager Backend

Backend database layer for a task manager application. This project currently contains a Prisma schema, PostgreSQL datasource configuration, and the initial database migration for users, workspaces, tasks, and comments.

## Tech Stack

- Node.js
- Prisma ORM 7
- PostgreSQL

## Project Structure

```text
.
+-- prisma/
|   +-- migrations/
|   |   +-- 20260812150332_init/
|   |       +-- migration.sql
|   +-- schema.prisma
+-- prisma.config.ts
+-- package.json
+-- package-lock.json
```

## Getting Started

Install dependencies:

```bash
npm install
```

Create a `.env` file in the project root and add your PostgreSQL connection string:

```env
DATABASE_URL="postgresql://USER:PASSWORD@HOST:PORT/DATABASE"
```

Apply the existing migrations:

```bash
npx prisma migrate dev
```

Generate the Prisma client:

```bash
npx prisma generate
```

The generated Prisma client is written to:

```text
generated/prisma
```

## Database Models

The schema defines four main models:

- `User`: stores user identity, email, password, and creation time.
- `Workspace`: groups tasks and belongs to one owner.
- `Task`: belongs to a workspace and can optionally be assigned to a user.
- `Comment`: belongs to a task and is authored by a user.

Task statuses currently use a string field with this intended set:

```text
todo | in-progress | done
```

## Useful Prisma Commands

Open Prisma Studio:

```bash
npx prisma studio
```

Create a new migration after editing the schema:

```bash
npx prisma migrate dev --name migration_name
```

Validate the Prisma schema:

```bash
npx prisma validate
```

Format the Prisma schema:

```bash
npx prisma format
```

## Notes

- `.env` is ignored by Git and should not be committed.
- The datasource URL is loaded from `DATABASE_URL` in `prisma.config.ts`.
- There are no application server entry points or API routes in this backend yet.
