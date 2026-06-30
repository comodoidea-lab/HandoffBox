# Next Actions

## Current Status

The project has a clickable PWA prototype based on the Serene Utility visual direction.

The current documented prototype supports the main place list, registered places, add-place flow, empty state, sample local data, checklist editing, basic location matching, arrival-state handling, PWA manifest, service worker, IndexedDB-backed local persistence with fallback storage, app shortcuts, locally vendored Driver.js onboarding, post-registration preview onboarding, subtle item-add feedback, local JSON backup export/import, and a localhost-only location simulator for development verification.

## Next Concrete Actions

1. Use the development location simulator to test arrival matching, out-of-range behavior, and manual place selection across representative place data.
2. Continue separating event handling from `app.js` so UI events, state mutations, and location orchestration remain easy to test.
3. Add a small compatibility check for backup import/export across future schema versions.
4. Keep manual place registration usable without Google Maps or network APIs.
5. Defer account/cloud sync until the privacy model and user need are explicitly approved.

## Blockers

- Public deployment status: Unknown / 不明
- Production Google Maps / Places API setup: Unknown / 不明
- Repository visibility and public evidence links: Unknown / 不明

## Approval Needed

- Ask before adding paid APIs, deployment changes, account/cloud sync, analytics, or any feature that changes the privacy model.
