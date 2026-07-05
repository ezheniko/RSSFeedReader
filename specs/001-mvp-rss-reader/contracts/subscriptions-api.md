# Subscription API Contract

## Endpoint: POST /api/subscriptions

### Purpose
Adds a new subscription to the in-memory list.

### Request Body
```json
{
  "url": "https://example.com/feed.xml"
}
```

### Success Response
- Status: 200 OK
- Body:
```json
{
  "id": "guid",
  "url": "https://example.com/feed.xml",
  "createdAt": "2026-07-05T00:00:00Z"
}
```

### Validation Error Response
- Status: 400 Bad Request
- Body:
```json
{
  "error": "A valid URL is required."
}
```

## Endpoint: GET /api/subscriptions

### Purpose
Returns all subscriptions currently stored in memory.

### Success Response
- Status: 200 OK
- Body:
```json
[
  {
    "id": "guid",
    "url": "https://example.com/feed.xml",
    "createdAt": "2026-07-05T00:00:00Z"
  }
]
```
