# Tasks: MVP RSS Reader

**Input**: Design documents from `/specs/001-mvp-rss-reader/`

**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Tests**: Tests are optional for this MVP; the tasks below focus on build and manual validation because the feature spec did not require a formal test suite.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Create the initial backend and frontend structure for the MVP.

- [ ] T001 Create backend and frontend project folders per implementation plan
- [ ] T002 Initialize ASP.NET Core Web API and Blazor WebAssembly projects with the required dependencies
- [ ] T003 [P] Configure build and run settings for local development and basic routing

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Establish the shared API contract, shared models, and configuration needed by all stories.

- [ ] T004 Create the in-memory subscription model in backend/src/Models/Subscription.cs
- [ ] T005 Create the subscription service in backend/src/Services/SubscriptionService.cs
- [ ] T006 Implement the subscription API endpoints in backend/src/Controllers/SubscriptionsController.cs
- [ ] T007 Configure frontend API client and base URL handling in frontend/src/Services/SubscriptionApiClient.cs
- [ ] T008 Add basic validation and error handling for empty submissions in backend and frontend

**Checkpoint**: Foundation ready - user story implementation can now begin

---

## Phase 3: User Story 1 - Add a feed subscription (Priority: P1) 🎯 MVP

**Goal**: Allow a user to enter a feed URL and add it to the current session’s subscription list.

**Independent Test**: A user can add a subscription and see it immediately appear in the list.

### Implementation for User Story 1

- [ ] T009 [P] [US1] Create the subscription form component in frontend/src/Components/SubscriptionForm.razor
- [ ] T010 [P] [US1] Create the subscription list display component in frontend/src/Components/SubscriptionList.razor
- [ ] T011 [US1] Implement the add-subscription UI flow in frontend/src/Pages/Subscriptions.razor
- [ ] T012 [US1] Wire the frontend form to the backend POST /api/subscriptions endpoint
- [ ] T013 [US1] Refresh the displayed list after a successful add operation

**Checkpoint**: User Story 1 should be fully functional and testable independently

---

## Phase 4: User Story 2 - Review the subscription list (Priority: P1)

**Goal**: Show the user the complete list of subscriptions they have added for the current session.

**Independent Test**: A user can view all added subscriptions in a simple list.

### Implementation for User Story 2

- [ ] T014 [P] [US2] Implement the GET /api/subscriptions endpoint to return the current subscription collection
- [ ] T015 [US2] Load the subscription list from the backend when the page initializes
- [ ] T016 [US2] Render the subscription list in a simple, clear format in the frontend UI

**Checkpoint**: User Story 2 should also work independently

---

## Phase 5: User Story 3 - Keep the experience intentionally simple (Priority: P2)

**Goal**: Ensure the MVP remains focused on simple subscription management without introducing richer feed features.

**Independent Test**: The app supports the add-and-list workflow without requiring feed parsing, persistence, or additional setup.

### Implementation for User Story 3

- [ ] T017 [US3] Add user-facing validation messaging for empty input in frontend/src/Pages/Subscriptions.razor
- [ ] T018 [US3] Document the MVP scope and validation expectations in the project documentation
- [ ] T019 [US3] Verify the app remains in-memory-only and does not imply unsupported feed features

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Final verification and cleanup for the MVP.

- [ ] T020 [P] Run build verification for the backend and frontend projects
- [ ] T021 [P] Validate the add-subscription and list-subscription workflow manually in the browser
- [ ] T022 Review configuration, routing, and local port setup for the frontend/backend connection
- [ ] T023 Update the quickstart notes if the validation flow changed during implementation
