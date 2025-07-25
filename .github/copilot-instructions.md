# GitHub Copilot Instructions for This Project

## Additional Documentation
- Always read from and write to `.github/copilot-task-plans.md` for keeping track of high-level plans and low-level tasks to be implemented
- Always read from and write to `.github/copilot-notes.md` to track learnings and guidance for future runs

## Project Overview
- This is a Bun project.
- This project is dockerized.

## Development Workflow
- If asked to plan or brainstorm, refrain from writing code. Instead, read from and write to `.github/copilot-task-plans.md` to plan out the high level and low level implementation steps.
- Lint, typecheck, and test should pass before completing the task

## Database Configurations

### PostgreSQL
If PostgreSQL is used in this project:
- Docker Compose should use PostgreSQL v17 image
- Install and use the following packages:
  - `npm:kysely` for query building
  - `npm:pg` for PostgreSQL client

### Redis
If Redis is used in this project:
- Docker Compose should use Redis v8 image
- Install and use the following packages:
  - `npm:bullmq` for queue management
  - `npm:ioredis` for Redis client

## Telegram Bot Implementation
If this project implements a Telegram bot:
- Use `npm:grammy` and its related plugins
- If using grammy, the grammy Bot object should be created as a global object in `src/index.ts`. Do not create a function to get or create this bot object.
- A Composer object representing all of the bot's middleware, should be created in a separate file. The global bot object should only `.use` this composer, and nothing else.
- Avoid the use of slash commands where possible. Prefer @grammyjs/conversations, inline keyboard, or inline queries for interactions.
- **Important**: Grammy sessions MUST NOT be used in this project.
