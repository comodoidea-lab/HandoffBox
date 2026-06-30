# Decisions

Record settled decisions and why they were made.

## Decision Log

### 2026-06-30: Treat Koko List as a place-based reminder product

- Status: Accepted
- Decision: Position Koko List as a place-based reminder app, not only a shopping list.
- Rationale: The core value is opening the app at a place and immediately seeing the relevant things to remember there.
- Consequences: Product and UI work should prioritize place context, fast retrieval, and calm task recall over broad list-management or social features.
- Evidence: Unknown / 不明

### 2026-06-30: Build the MVP as a device-first PWA

- Status: Accepted
- Decision: Start with a PWA that stores data on-device first.
- Rationale: The MVP should validate the core behavior before adding accounts, cloud sync, or native geofence notifications.
- Consequences: Local storage and privacy copy matter early; cloud sync, push notifications, and account systems stay out of the first MVP.
- Evidence: Unknown / 不明

### 2026-06-30: Keep maps and place search useful but not blocking

- Status: Accepted
- Decision: Use high-accuracy map and place search capabilities later where they improve setup, while preserving manual registration.
- Rationale: Place registration should become trustworthy, but the app should not depend on network APIs for basic use.
- Consequences: Future map and place provider work should use provider-neutral records and include fallback manual paths.
- Evidence: Unknown / 不明

### 2026-06-30: Prioritize onboarding before deeper main UI polish

- Status: Accepted
- Decision: Emphasize a minimal, clear onboarding experience before spending more effort on detailed main UI refinement.
- Rationale: The product concept is a minimal but useful experience; the first-run flow should make the core behavior obvious without forcing users to explore.
- Consequences: The app should keep guided onboarding short, plain, and action-oriented. The app-internal onboarding copy is separate from future landing page copy.
- Evidence: Code reference `f5b6672` (`feat: add Driver.js onboarding`; link omitted because repository visibility was not publicly confirmed)

### 2026-06-30: Use Driver.js for guided onboarding

- Status: Accepted
- Decision: Use Driver.js for the first guided onboarding implementation.
- Rationale: Driver.js is lightweight, MIT licensed, dependency-free, and fits a static PWA without requiring a framework migration.
- Consequences: The current implementation uses a fixed CDN version. A future PWA hardening pass should decide whether to vendor the Driver.js assets locally for offline reliability.
- Evidence: Code reference `f5b6672` (`feat: add Driver.js onboarding`; link omitted because repository visibility was not publicly confirmed)
