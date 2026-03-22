# GSoC 2026 Proposal Draft (Maintainer Review Version)

## Project Title

Mobile-First Feature Parity for Open Food Facts Explorer through a Shared Data Layer and Reusable OFF Components

## Executive Summary

Open Food Facts Explorer is the long-term modern frontend for Open Food Facts. To accelerate adoption and reduce maintenance cost, I propose a focused project that improves 2 to 3 high-impact mobile user flows while introducing a reusable, typed data-access pattern for selected product/search features. The project is intentionally scoped for approximately 175 hours, with measurable outcomes, incremental pull requests, and clear handoff documentation for future contributors.

## Why This Matters Now

- Mobile is the dominant usage context, so friction in core flows has high user impact.
- Similar API integration logic is repeated across screens, slowing feature delivery.
- Explorer roadmap priorities already emphasize reuse of OFF SDK and OFF webcomponents.

In practical terms: this project improves user experience immediately and reduces long-term engineering drag.

## Applicant Readiness (Contribution Evidence)

I have already contributed to Explorer in accessibility, reliability, and UX behavior improvements.

- Active PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1230
- PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1109
- PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1100
- PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1083
- PR (merged): https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1058
- Issue: https://github.com/openfoodfacts/openfoodfacts-explorer/issues/1157
- Issue: https://github.com/openfoodfacts/openfoodfacts-explorer/issues/1106
- Issue: https://github.com/openfoodfacts/openfoodfacts-explorer/issues/1098

## Problem Statement

Explorer needs stronger parity with key experiences from the standard Open Food Facts website, especially on mobile. At the same time, repeated API wiring across components increases cognitive load and maintenance overhead.

Primary problem:

- Users encounter avoidable friction in key product/search journeys.

Secondary problem:

- Contributors duplicate API logic instead of reusing a consistent pattern.

## Proposed Solution

Deliver a scoped parity track combining architecture and UX improvements:

1. Implement a shared, typed data-access layer for selected product/search endpoints.
2. Improve 2 to 3 high-value mobile-first user flows end-to-end.
3. Integrate OFF webcomponents where they speed delivery and increase consistency.
4. Publish migration and extension guidance for future parity work.

## Scope

In scope:

- Selected product/search flows only (maximum 3).
- Shared data-access abstraction in targeted modules.
- Reusable component integration and documentation.

Out of scope:

- Full-site parity in one GSoC cycle.
- Global redesign unrelated to scoped flows.
- Full migration of all API consumers.

## Deliverables and Acceptance Criteria

### D1: Shared Data Layer for Scoped Endpoints

- Typed wrappers and response mapping for selected APIs.
- Standardized error/loading handling in migrated flows.

Acceptance:

- Duplicated API-call logic reduced by at least 30% in targeted modules.
- No functional regressions in migrated flows.

### D2: Mobile-First Parity for 2 to 3 Core Flows

Candidate flows:

- Search to product transition.
- Product understanding via key panels.
- Basic edit path for selected fields.

Acceptance:

- Improved interaction clarity and reduced user friction in scoped flows.
- Accessibility validation passed for new interactions.
- Mobile performance on targeted pages improved or maintained.

### D3: OFF Webcomponents Adoption

- Integrate at least 2 reusable OFF webcomponents in user-facing pages.

Acceptance:

- Components are production-usable in scoped flows.
- Clear integration guidance is documented.

### D4: Contributor Handoff Pack

- Architecture note, migration checklist, and before/after summary.

Acceptance:

- Another contributor can extend one additional flow using the published pattern.

## Timeline (Approximately 175 Hours)

Community Bonding:

- Confirm final scope with mentor.
- Freeze target flows and baseline metrics.

Weeks 1 to 3:

- Build first slice of shared data layer.
- Migrate first flow and open incremental PRs.

Weeks 4 to 6:

- Migrate second and third flows.
- Integrate reusable webcomponents.
- Validate responsive and accessibility behavior.

Weeks 7 to 9:

- Performance and robustness pass.
- Documentation and handoff completion.
- Final metric report and polish.

## Risk Management

- Scope creep: cap scope at 2 to 3 flows and maintain explicit out-of-scope list.
- API variability: isolate endpoint differences in adapters.
- External API instability in development: validate loading and error states with resilient UI behavior.

## Communication and Delivery Style

- Frequent incremental PRs instead of one large drop.
- Early mentor checkpoints for scope confirmation.
- Transparent progress tracking and decision logs.

## Expected Impact

- Better mobile usability in the most visible product/search journeys.
- Cleaner, more maintainable integration pattern for contributors.
- Faster future parity work through reuse of OFF SDK and webcomponents.

## Project Information

- Repository: https://github.com/openfoodfacts/openfoodfacts-explorer
- Related repositories: https://github.com/openfoodfacts/openfoodfacts-nodejs, https://github.com/openfoodfacts/openfoodfacts-webcomponents
- Slack channel: #off-explorer
- Potential mentor: VaiTon
- Project duration: approximately 175 hours
- Skills required: TypeScript, Svelte/SvelteKit, HTTP API integration
- Difficulty: Medium
