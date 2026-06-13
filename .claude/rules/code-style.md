---
description: Code style rules for MyBlog frontend, backend, and docs
---

# Code Style

- Keep changes small and focused.
- Prefer editing existing files over creating new ones.
- Use clear names that describe the data or behavior.
- Avoid abbreviations unless they are common in the project.
- Keep functions small and single-purpose.
- Split logic when a function needs multiple responsibilities.
- Prefer early returns over deeply nested conditionals.
- Handle errors explicitly.
- Do not swallow exceptions, ignore failed promises, or hide failed commands.
- Delete commented-out code, placeholder examples, and stale notes.
- Avoid unnecessary comments and docstrings.
- Add comments only when they explain non-obvious decisions.
- Use pnpm for Node tooling. Do not add npm or yarn lockfiles.
- Keep local machine files out of shared config.
- Do not edit generated outputs such as `dist/`, `build/`, `target/`,
  or `node_modules/`.

## Frontend

- Use Vue 3 single-file components with `<script setup lang="ts">`.
- Use PascalCase for Vue component files and component names.
- Keep frontend runtime and build dependencies in `frontend/package.json`.
- Keep shared assets in `frontend/src/assets/`.
- Keep Vue components in `frontend/src/components/`.
- Use TypeScript types for component props, emits, and exported helpers.

## Backend

- Keep Java packages under `com.liu.myblog`.
- Follow Spring Boot conventions for controllers, services, and repositories.
- Use DTOs for request and response objects when endpoint data is not trivial.
- Keep backend configuration in `backend/src/main/resources/`.
- Use Lombok only where it removes boilerplate without hiding behavior.

## Documentation

- Keep Markdown concise and project-specific.
- Prefer current commands and paths from this repository.
- When a directory is only reserved or empty, say so clearly.
