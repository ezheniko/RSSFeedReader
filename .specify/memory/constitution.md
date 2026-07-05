# RSS Feed Reader Constitution
<!--
Sync Impact Report
- Version change: 0.0.0 → 1.0.0
- Modified principles: none (initial constitution)
- Added sections: Security Requirements, Development Workflow
- Removed sections: none
- Templates requiring updates: ✅ .specify/templates/plan-template.md, ✅ .specify/templates/spec-template.md, ✅ .specify/templates/tasks-template.md
-->

## Core Principles

### I. MVP-First Scope Discipline
The MVP MUST deliver only the add-subscription and list-subscriptions workflow. Any feature that adds feed fetching, persistence, removal, polling, or richer content handling MUST wait until the core experience works end to end and is explicitly approved. This keeps the project small, testable, and aligned with the proof-of-concept goal.

### II. Defensive Input and Data Handling
The application MUST treat feed URLs and any external feed content as untrusted input. User-supplied values MUST be accepted only in the narrowest form needed, and future feed rendering MUST avoid unsafe content execution. Network and parsing failures MUST produce explicit, non-throwing user-visible errors. This protects the app from malformed input, brittle behavior, and security issues.

### III. Maintainable Separation of Concerns
Backend and frontend responsibilities MUST remain explicit: API work belongs in the server, UI state and rendering belong in the client, and shared rules MUST be documented rather than duplicated. New code MUST use clear names, small focused components, and straightforward state flow. This keeps the project understandable as it grows beyond the MVP.

### IV. Quality Through Verification
Every user-visible change MUST be verified by a build or test step and by a direct manual check of the relevant workflow before it is considered complete. The project MUST keep configuration, routes, and port setup consistent, and any cleanup required for the Blazor template MUST be completed before feature work proceeds. This prevents regressions and avoids wasted debugging time.

### V. Evolution-Friendly Design
The implementation MUST prefer simple, extensible structures that support future additions such as persistence, feed refresh, and richer error handling without a rewrite. Configuration, interfaces, and data models MUST be explicit enough that later extensions can be added safely. This preserves the architecture chosen for ASP.NET Core + Blazor while keeping the MVP lean.

## Security Requirements
The project MUST follow basic secure-by-default practices for a local demo application:
- User-supplied URLs and any future feed content MUST be handled defensively and never trusted implicitly.
- Network and parsing code MUST fail gracefully and avoid exposing stack traces or secrets to users.
- Future rendering of feed content MUST use safe rendering practices rather than raw HTML execution.
- Configuration values, including API base URLs and CORS origins, MUST be explicit and verified before testing.

## Development Workflow
All work MUST follow the MVP-first delivery path:
- Implement the add-subscription and list-subscriptions flow before introducing feed fetching or persistence.
- Complete foundational cleanup and configuration checks before feature implementation begins.
- Keep documentation, route setup, and build verification aligned with the current scope.
- Before merging or considering work complete, verify the relevant user flow in the running app and record any follow-up work for later phases.

## Governance
This constitution supersedes ad hoc implementation choices for this repository. Any change to the principles, constraints, or workflow MUST be documented as an amendment, reviewed against the current MVP goals, and approved before being applied to active work. Changes that alter scope, security expectations, or verification requirements MUST include a clear migration note when existing work depends on the previous rule.

All pull requests and feature work MUST demonstrate compliance with these principles by showing the relevant verification steps, scope fit, and any tradeoffs made.

**Version**: 1.0.0 | **Ratified**: 2026-07-05 | **Last Amended**: 2026-07-05
