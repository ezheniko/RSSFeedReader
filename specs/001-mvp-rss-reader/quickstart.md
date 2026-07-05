# Quickstart: MVP RSS Reader

## Prerequisites

- .NET SDK matching the target project version
- A local browser for manual validation

## Setup

1. Create the backend and frontend projects using the planned ASP.NET Core + Blazor structure.
2. Implement the POST and GET subscription endpoints in the backend.
3. Implement the subscription form and list UI in the frontend.

## Validation Scenarios

### Scenario 1: Add a subscription
1. Start the backend and frontend locally.
2. Open the app in the browser.
3. Enter a sample feed URL and submit it.
4. Confirm the URL appears in the subscription list.

### Scenario 2: Reject empty input
1. Open the app in the browser.
2. Leave the URL field empty and submit.
3. Confirm the app shows a simple validation message and does not add a subscription.

### Scenario 3: Verify session-only behavior
1. Add one or more subscriptions.
2. Restart the app.
3. Confirm the list is reset unless persistence is added later.
