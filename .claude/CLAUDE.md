# MyBlog Team Claude Guide

## Project

MyBlog — 个人博客网站，包含 Vue 3 前端与 Spring Boot 后端。

## Stack

- Package manager: pnpm 10.28.2
- Frontend: Vue 3.5, TypeScript 6, Vite 8, vue-tsc
- Backend: Java 21, Spring Boot 3.5.14, Maven Wrapper
- Backend libraries: Spring Web, Spring Session Redis, MySQL Connector/J, Lombok
- Tests: JUnit 5 through `spring-boot-starter-test`
- Data stores: MySQL for business data, Redis for sessions
- Deploy: `deploy/` is reserved for Docker Compose and Nginx config

## Structure

- `.claude/` — Claude Code team guide and project settings
- `.husky/` — Git hooks for commit message checks and lint-staged
- `backend/` — Spring Boot backend project
- `backend/src/main/java/com/liu/myblog/` — backend application code
- `backend/src/main/resources/` — backend configuration and resources
- `backend/src/test/java/com/liu/myblog/` — backend tests
- `frontend/` — Vue 3 + TypeScript + Vite frontend project
- `frontend/src/components/` — Vue components
- `frontend/src/assets/` — frontend assets
- `docs/` — requirements, database design, API docs, and diagrams
- `deploy/` — deployment files such as Docker Compose and Nginx config
- `scripts/` — initialization, migration, and maintenance scripts

## Commands

Run commands from the repository root unless a directory is shown.

- Install root tooling: `pnpm install`
- Install frontend deps: `cd frontend && pnpm install`
- Prepare Git hooks: `pnpm prepare`
- Commit helper: `pnpm commit`
- Staged-file checks: `pnpm lint-staged`
- Frontend dev: `cd frontend && pnpm dev`
- Frontend build and type check: `cd frontend && pnpm build`
- Frontend preview: `cd frontend && pnpm preview`
- Backend dev: `cd backend && ./mvnw spring-boot:run`
- Backend compile: `cd backend && ./mvnw compile`
- Backend test: `cd backend && ./mvnw test`
- Backend package: `cd backend && ./mvnw package`

## Verification

After every change, run the checks for the affected area and report any skipped
checks with the reason.

1. Backend changes: `cd backend && ./mvnw test`
2. Frontend changes: `cd frontend && pnpm build`
3. Markdown/docs changes: `pnpm exec prettier --check <files>`
4. Docs under `docs/`: `pnpm exec markdownlint-cli2 <files>`
5. Hook or commit config changes: stage the files, then run `pnpm lint-staged`

Current gaps: there is no frontend test script and no dedicated frontend lint
script yet. Do not invent commands; add scripts first if the project needs them.

## Conventions

- Keep changes small and focused.
- Prefer editing existing files over creating new ones.
- Prefer simple code and early returns over nested conditionals.
- Avoid unnecessary comments and docstrings.
- Use pnpm only; do not add npm or yarn lockfiles.
- Use the root `package.json` for repository tooling dependencies.
- Use `frontend/package.json` for frontend runtime and build dependencies.
- Keep backend package names under `com.liu.myblog`.
- Put backend config in `backend/src/main/resources/`.
- Use Spring Boot conventions for controllers, services, repositories, and DTOs.
- Use Vue 3 `<script setup lang="ts">` for new single-file components.
- Use PascalCase for Vue component files and component names.
- Keep local machine settings out of shared files.
- Ask before committing to Git.

## Don't

- Do not commit secrets, credentials, or local environment values.
- Do not edit generated outputs such as `dist/`, `build/`, `target/`, or
  `node_modules/`.
- Do not commit `.DS_Store`, IDE workspace files, or personal local settings.
- Do not assume `docs/`, `deploy/`, or `scripts/` are complete when they are
  empty or only placeholders.
- Do not add dependencies or major structure changes without a clear need.
- Do not call work done when verification failed or was skipped without reason.
