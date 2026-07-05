# Research: MVP RSS Reader

## Decision

Use a simple backend/frontend split with an in-memory subscription list for the MVP. The backend will expose a minimal API for adding and listing subscriptions, and the frontend will render the form and list.

## Rationale

This choice aligns with the project goals and stack notes while keeping the MVP small and easy to validate. It also preserves a clear path for future enhancements without introducing persistence or feed processing early.

## Alternatives considered

- Single-project implementation: rejected because the stated stack and project goals point to a clear backend/frontend separation.
- Persistence-first implementation: rejected because the MVP explicitly requires in-memory-only behavior and a simple proof-of-concept.
- Feed-fetching implementation: rejected because the MVP scope is limited to adding and displaying subscriptions only.
