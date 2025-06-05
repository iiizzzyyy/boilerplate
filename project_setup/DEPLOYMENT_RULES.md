# Windsurf Rules – Deployment

## Platform
- **Vercel** for front‑end & serverless functions.
- **Supabase**: database + storage; Prisma migrations run in Vercel build step.

## Environments
| Vercel Env | Git Branch | Supabase Project |
|------------|-----------|------------------|
| Production | main      | prod            |
| Preview    | every PR  | staging         |

## Build Commands
```
"build": "next build && prisma generate"
```
Edge Functions are auto‑deployed under `/api`.

## Secrets
- Use Vercel **Environment Variables** UI; never commit `.env`.
- Rotate tokens every 90 days; store rotation runbook in `/runbooks/`.

## Rollback
- Use Vercel “Re‑deploy previous” if health checks fail.
