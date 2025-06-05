# Windsurf Rules – Project Management

## Linear Workflow
1. Every coding session begins with `linear list_issues project:<Dr‑Chrono Integration>`; sync into Cascade context.
2. Branch naming: `iss-{linear_id}/{slug}`.
3. Commits are **imperative** (`fix`, `add`, `refactor`), start with Linear ID.
4. After pushing, open PR and attach Linear issue; mark status **In Review**.
5. `PLANNING.md` is the single‑source‑of‑truth. Update on every scope change.

## Meeting Cadence
- **Daily async stand‑up** thread in Linear comments.
- **Weekly demo**: deploy preview to Vercel, link in comment.

## Definition of Done
- All acceptance criteria satisfied.
- Unit & integration tests ≥ 90% lines.
- Deployed to **production** environment without errors.
