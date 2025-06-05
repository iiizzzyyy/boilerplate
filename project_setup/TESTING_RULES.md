# Windsurf Rules – Testing

## Unit
- **Jest** + `ts-jest` preset.
- 90% line coverage enforced in CI (`jest --coverage --maxWorkers=50%`).

## Component
- **React Testing Library**; mock TanStack Query with `QueryClientProvider`.
- Snapshot only for primitive presentational components.

## Integration
- **Prisma** runs against `postgres:15-alpine` in Docker; use transactional rollbacks per test.

## End‑to‑End
- **Playwright** headless Chromium in CI; smoke test critical flows.

## Continuous Integration
- GitHub Actions: `lint → test → type‑check → build`.
- Tests must pass before Vercel deploy.

