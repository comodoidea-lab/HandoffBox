# Journal

Public-safe work log for Koko List.

## 2026-06-30

- Created the initial public-safe HandoffBox ledger for Koko List.
- Summarized the product as a device-first PWA for place-based reminders.
- Recorded the MVP scope, current prototype status, and next foundation cleanup actions.
- Added Driver.js onboarding to the PWA so first-time users get a short guided introduction.
- Confirmed the guide can be started automatically on first use and reopened from settings.
- Added a post-place-registration onboarding preview that shows temporary example tasks and shortcuts without saving them as user data.
- Added a small add-item microinteraction so newly added list items feel immediately acknowledged.
- Adjusted first-run empty-state copy toward generic place registration instead of assuming the current location is the place to save.
- Vendored Driver.js 1.6.0 assets locally and included them in the PWA cache so onboarding no longer depends on CDN delivery.
- Started Phase 1 foundation cleanup by splitting storage, state, location matching, static data, DOM helpers, onboarding definitions, and view rendering into smaller modules.
- Added IndexedDB-backed app state persistence with localStorage fallback and legacy localStorage migration.
- Added local JSON backup export/import from the settings screen so users can save and restore on-device data before any account or cloud sync work.
- Evidence: Unknown / 不明
- Code reference: `f5b6672` (`feat: add Driver.js onboarding`; link omitted because repository visibility was not publicly confirmed)
- Code reference: `04e7dac` (`feat: add post-place onboarding preview`; link omitted because repository visibility was not publicly confirmed)
- Code reference: `f745528` (`copy: make first-run place registration wording generic`; link omitted because repository visibility was not publicly confirmed)
- Code reference: `192a78e` (`chore: vendor Driver.js assets`; link omitted because repository visibility was not publicly confirmed)
- Code reference: `f4472e5` (`refactor: split core storage state and location logic`; link omitted because repository visibility was not publicly confirmed)
- Code reference: `3eec958` (`refactor: extract view rendering module`; link omitted because repository visibility was not publicly confirmed)
- Code reference: `c1497c1` (`feat: persist app state with IndexedDB fallback`; link omitted because repository visibility was not publicly confirmed)
- Code reference: `8f7929e` (`feat: add local backup import export`; link omitted because repository visibility was not publicly confirmed)

## 2026-07-01

- Continued Phase 1 foundation cleanup by moving app-level state mutation actions into a dedicated action module.
- Added arrival-state handling so the app distinguishes between location permission, location availability, matching a registered place, and being outside registered place ranges.
- Added a localhost/check-mode development location simulator for testing arrival and out-of-range behavior without physically moving devices.
- Kept Google Maps and Places API integration out of the critical path for the current core check; current matching uses browser location coordinates against stored place coordinates.
- Evidence: Unknown / 不明
- Code reference: `872d569` (`refactor: extract app action mutations`; link omitted because repository visibility was not publicly confirmed)

## Notes For Future Agents

- Keep detailed implementation work in the code repository.
- Keep HandoffBox entries concise and public-safe.
- Use `Unknown / 不明` instead of guessing deployment, approval, repository visibility, or verification state.
