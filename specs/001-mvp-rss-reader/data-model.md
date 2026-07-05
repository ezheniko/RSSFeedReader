# Data Model: MVP RSS Reader

## Entities

### Subscription
- Id: unique identifier for the subscription
- Url: string containing the feed URL entered by the user
- CreatedAt: timestamp for when the subscription was added

### SubscriptionList
- Subscriptions: ordered collection of Subscription objects currently visible to the user

## Validation Rules

- Url must be present and not whitespace-only.
- Url should be stored as provided by the user for the MVP.
- The list is transient and exists only for the current session.

## Relationships

- A SubscriptionList contains zero or more Subscription records.
- No other entities are required for the MVP.
