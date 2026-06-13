---
description: Testing and verification rules for MyBlog
paths:
  - "backend/src/test/**/*.java"
  - "backend/src/main/java/com/liu/myblog/**/*.java"
  - "frontend/src/**/*.test.ts"
  - "frontend/src/**/*.spec.ts"
  - "frontend/src/**/*.test.vue"
  - "frontend/src/**/*.spec.vue"
---

# Testing

- Test behavior and user-visible outcomes.
- Do not test private implementation details when a public path is available.
- Name tests after the behavior they prove.
- Add a regression test for every bug fix when a suitable test layer exists.
- Prefer real code paths over mocks.
- Mock only external systems or slow infrastructure.
- Keep tests deterministic.
- Do not rely on test order, wall-clock timing, or machine-local state.
- For backend changes, run `cd backend && ./mvnw test`.
- For frontend changes, run `cd frontend && pnpm build`.
- The frontend build includes `vue-tsc -b` and Vite build.
- For Markdown changes, run `pnpm exec prettier --check <files>`.
- For docs under `docs/`, also run `pnpm exec markdownlint-cli2 <files>`.
- If a verification command is skipped, report the reason clearly.
- Do not invent missing scripts.
- There is currently no frontend test script or dedicated frontend lint script.
