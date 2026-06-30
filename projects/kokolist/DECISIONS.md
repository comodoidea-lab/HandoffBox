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
