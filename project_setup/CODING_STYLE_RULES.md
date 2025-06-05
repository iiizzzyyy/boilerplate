# Windsurf Rules – Coding Style

- **Airbnb JavaScript & TypeScript ESLint** preset; extended with `@next/next`.
- Prettier runs pre‑commit via Husky.
- Functions < 20 lines; early returns over nesting.
- **No `any`**. Create types or use generics.
- Filenames: `kebab-case.ts`; React components: `PascalCase.tsx`.
- One export per file (default + named helpers).
- All public functions have JSDoc.
- Strict null checks.

