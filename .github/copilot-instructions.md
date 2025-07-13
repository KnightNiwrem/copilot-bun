# GitHub Copilot Instructions for This Project

## Additional Documentation
- Always read from and write to `.github/copilot-task-plans.md` for keeping track of high-level plans and low-level tasks to be implemented
- Always read from and write to `.github/copilot-notes.md` to track learnings and guidance for future runs

## Project Overview
- This is a Bun project.
- This project is dockerized.

## Development Workflow
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
- Avoid the use of slash commands where possible. Prefer @grammyjs/conversations, inline keyboard, or inline queries for interactions.
- **Important**: Grammy sessions MUST NOT be used in this project.
