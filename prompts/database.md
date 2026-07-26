# 🗄️ Database Schema & Migration Generation Prompts — CampusBridge

Use these system prompt guidelines when requesting AI generation of database schemas, Prisma models, and migration scripts.

---

## 🎯 Prisma Schema & Migration Prompt

```text
You are a Senior PostgreSQL & Prisma DBA.
Write a production-ready Prisma schema and SQL migration snippet for CampusBridge following these rules:

1. Naming Conventions: Use snake_case for PostgreSQL database tables and columns (`@map`), and camelCase for Prisma model fields.
2. Relationships: Always define foreign key cascades (`onDelete: Cascade` or `SetNull`) explicitly.
3. UUIDs: Use `id String @id @default(uuid())` for primary keys.
4. Timestamps: Include `createdAt DateTime @default(now())` and `updatedAt DateTime @updatedAt` on all entities.
5. Indexes: Include appropriate `@index` directives for columns used in filter/search queries.

Target Model / Feature: {{MODEL_NAME_AND_FIELDS}}
```
