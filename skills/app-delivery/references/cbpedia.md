# CBPedia project profile

Snapshot derived from the sibling `cbpedia` repository on October 1, 2026. Locate that repository from the user's target/workspace and read its current `AGENTS.md` before acting. Current code and workflow files resolve stale README and planning claims.

## Architecture and invariants

React 19, TypeScript, Vite, Zustand, and an existing ITIS procedure API. Use current helpers in `src/api/procedures.ts` instead of adding ad hoc fetch calls in feature components. Preserve loading/error behavior and normalize backend payloads at the shared boundary.

The reader coordinates canon navigation, passage rendering, and context/history. Respect shared store semantics and current atomic navigation/request ordering. Inspect current code for delayed updates and positioning logic; older documented navigation sequences may be superseded.

Semantic verse IDs are distinct from chapter/verse numbers. The documented encoding is `bookNo * 10,000,000 + chapNo * 10,000 + verseNo * 10 + 5`, with Genesis 1:1 represented by `10010015`. Validate response semantics before interpreting IDs; API testing records identify section-title rows ending in zero.

Follow current CSS naming and theme tokens, reader split properties, localStorage keys, and localization conventions. The agent rules specify global CSS and no Tailwind; historical UI documents mention other styling libraries. Prefer current instructions and dependencies.

Auth, guest access, and profile persistence evolved across sessions. Inspect current implementation and live contract evidence; do not copy historical token-persistence claims as current truth. A rejected server profile save must not appear successful solely because local state updated.

## Validation and documentation

From the repository root, verify available scripts and use those relevant to the change:

```bash
npm run typecheck
npm run lint
npm run test
npm run build
```

For reader/state changes, cover the actual navigation trigger, passage readiness, target highlight, repeated requests, and mobile panel behavior as relevant. API harness history is in `docs/test_completed_tasks.md`; locate current harness code before trying live sweeps. Do not initiate broad live API sweeps without task relevance and appropriate access.

`AGENTS.md` requires work-log updates in `docs/work_log.md` and matching entries in `src/features/changelog/ChangelogPage.tsx`, using US Eastern dates and dated entry headings. Save exact user prompts to `docs/session_prompts.md` when requested. Keep proposed diagrams distinct from implemented diagrams.

## Release context

`.github/workflows/ci.yml` configures lint, tests, and build on `main`/`release1` push and PR events. Its deployment job runs for `refs/heads/release1` and uploads the built `dist` through FTP using configured secrets. Inspect event conditions before publishing changes: a qualifying `release1` event can deploy. Do not include secret values in release records.
