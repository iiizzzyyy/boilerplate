# Windsurf Rules – Backend

## Runtime & Frameworks
- **Node.js 20 LTS**, TypeScript strict mode.
- **Supabase Edge Functions** for inbound webhooks (e.g., DrChrono event push).
- **Prisma ORM** pointed at Supabase Postgres; migrations via `prisma migrate deploy`.
- **REST Integrations**:
  - DrChrono: OAuth2 Client Credentials + `/api/v1/` endpoints.
  - HubSpot: Private App Token + batch upsert endpoints.

## Architecture
- Hexagonal (ports & adapters) with `services/`, `adapters/`, `domain/`.
- No Python allowed; all scripts are `.ts`.

## Error & Retry
- Idempotency keys for webhook processing.
- Exponential back‑off (2,4,8,16) for 429/5xx responses up to max 5 attempts.

## Env Vars
```
DRCHRONO_CLIENT_ID=
DRCHRONO_CLIENT_SECRET=
HUBSPOT_PRIVATE_TOKEN=
DATABASE_URL=
```
All managed in Vercel Project → *Environment Variables* GUI.

## Logging & Observability
- Use `pino` logger; stream to Vercel Log Drains.
- Each request/context includes `requestId`.

## Security
- Strip PHI before persisting to logs.
- Validate all external payloads against Zod schemas in `adapters/validators`.
