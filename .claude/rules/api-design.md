---
description: API design rules for MyBlog Spring Boot endpoints
paths:
  - "backend/src/main/java/com/liu/myblog/**/*.java"
  - "docs/**/*api*.md"
  - "docs/**/*API*.md"
---

# API Design

- Design APIs around blog domain concepts:
  users, articles, categories, tags, comments, and sessions.
- Keep controllers thin.
- Controllers should validate input, delegate to services, and return responses.
- Put business rules in services.
- Put persistence concerns in repositories.
- Put transport shapes in DTOs.
- Validate request data at the boundary with Spring validation or checks.
- Use consistent JSON response shapes before adding many routes.
- Use `GET` for reads, `POST` for creation, `PUT` or `PATCH` for updates,
  and `DELETE` for deletion.
- Return `201` for creation, `400` for malformed requests, `401` for
  unauthenticated access, `403` for unauthorized access, and `404` for
  missing resources.
- Do not expose stack traces, SQL details, tokens, passwords, or local values.
- Do not log sensitive data.
- Keep session behavior compatible with Spring Session Redis.
- Document new public endpoints in `docs/` when API docs exist for that area.
