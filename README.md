# HayPaComer database

The database of **HayPaComer**, the smart fridge that answers "what can I cook right now with what is actually at home?". Work happens here and goes straight to `main`; the history up to version 1.1.0 comes from the monorepo [Juansit-0/HayPaComer](https://github.com/Juansit-0/HayPaComer), with each commit kept under its original author.

Live: https://haypacomer.jenilarper.dev (API docs at [/docs](https://haypacomer.jenilarper.dev/docs)).

## What is here

- `migrations/`: the Flyway migrations that build the schema (relational data in PostgreSQL, AI state in Redis);
- `docs/database.md`: data model and ER diagram;
- `docker-compose.yml` and `.env.example`: PostgreSQL 18 and Redis 8 for local development.

The backend keeps its own copy in `adapter-persistence/src/main/resources/db/migration`; Flyway runs it automatically at application startup, so this folder is the reference copy. The backend README (Build) explains how to use this compose file with it.

## Try it

```bash
cp .env.example .env
docker compose up -d
```

Then point any SQL client at `127.0.0.1:5432` (the port in `.env`).
