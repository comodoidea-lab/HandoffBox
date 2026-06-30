# Next Actions

## Current Status

The project has a clickable PWA prototype based on the Serene Utility visual direction.

The current documented prototype supports the main place list, registered places, add-place flow, empty state, sample local data, checklist editing, basic location matching, PWA manifest, service worker, local persistence, app shortcuts, locally vendored Driver.js onboarding, post-registration preview onboarding, and subtle item-add feedback.

## Next Concrete Actions

1. Start Phase 1 foundation cleanup by separating app state, storage, location matching, and UI rendering into smaller modules.
2. Replace prototype `localStorage` persistence with IndexedDB while preserving the existing user-facing behavior.
3. Add local export/import for backup before any account or cloud sync work.
4. Keep manual place registration usable without Google Maps or network APIs.

## Blockers

- Public deployment status: Unknown / 不明
- Production Google Maps / Places API setup: Unknown / 不明
- Repository visibility and public evidence links: Unknown / 不明

## Approval Needed

- Ask before adding paid APIs, deployment changes, account/cloud sync, analytics, or any feature that changes the privacy model.
