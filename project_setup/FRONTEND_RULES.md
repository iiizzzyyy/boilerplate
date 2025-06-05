# Windsurf Rules – Frontend

## Tech Stack
- **Framework**: Next.js 14+ (App Router).  
- **Language**: TypeScript (`"strict": true`).  
- **Styling**: Tailwind CSS + Shadcn/ui component library.  
- **Data**: TanStack Query for async server‑state, React Context for client state.  
- **Forms & Validation**: React Hook Form + Zod.  

## Conventions
1. Use **PascalCase** filenames for React components (e.g. `UserCard.tsx`).  
2. Each component file exports **one default component + named helper sub‑components**.  
3. Keep component trees shallow; where parent needs data, lift the query to the highest server component then pass via props.  
4. Collocate component‑specific styles in the same folder using Tailwind classes or `component.module.css` when absolutely necessary.  

## Data Fetching
- **Server Components**: prefer for read‑heavy pages; wrap `prisma` calls in `cache(...)`.  
- **Client Components**: only when interaction/state is required; hydrate using `useQuery()` with an initial `dehydrate` payload.  
- **Error Handling**: show a Suspense fallback + `ErrorBoundary` around every page boundary.

## Forms
- Register fields with `register` and compose Zod validation via `zodResolver`.  
- Use *optimistic UI* patterns: update TanStack cache first, roll back on error.

## Accessibility & UX
- **Focus trapping** in modals.  
- Semantic HTML tags.  
- Colour contrast AA minimum.

## File Layout
```
/app
  └─ (routes)
/components
  └─ ui/  ← Shadcn clones
  └─ shared/
```

## Testing
- **React Testing Library** for component logic.  
- Use Storybook stories as test fixtures.  
