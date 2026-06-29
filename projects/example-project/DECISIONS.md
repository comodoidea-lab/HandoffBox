# Decisions

Record settled decisions and why they were made.

## Decision Log

### 2026-06-29: Use a public-safe ledger format

- Status: Accepted
- Decision: Keep project context in four public-safe files: `PROJECT.md`,
  `NEXT.md`, `JOURNAL.md`, and `DECISIONS.md`.
- Rationale: A consistent format lets AI agents resume work by reading a URL.
- Consequences: Sensitive details must stay out of HandoffBox.
