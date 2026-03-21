# GSoC 2026 Proposal Draft (One Page)

## Project Title

Mobile-First Feature Parity for Open Food Facts Explorer via Shared Data Layer and Reusable OFF Components

## Applicant Profile

I am an active contributor to Open Food Facts Explorer with recent work in accessibility, API safety, and UX behavior improvements. I have already worked in the project workflow (issues, PRs, review iteration), and I want to deliver a scoped, high-impact project aligned with Explorer priorities.

### Relevant contributions (exact links)

- Active PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1230
- PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1109
- PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1100
- PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1083
- PR (merged): https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1058
- Issue: https://github.com/openfoodfacts/openfoodfacts-explorer/issues/1157
- Issue: https://github.com/openfoodfacts/openfoodfacts-explorer/issues/1106
- Issue: https://github.com/openfoodfacts/openfoodfacts-explorer/issues/1098

## Problem Statement

Explorer is the next-generation frontend, but some critical user journeys still need parity and consistency with the standard Open Food Facts website, especially on mobile (the majority usage context). In parallel, similar API logic is repeated across screens, which slows development and increases maintenance burden.

In simple terms: users need smoother mobile flows, and contributors need cleaner architecture so features can ship faster.

## Proposed Solution

I propose a scoped parity track that combines user-facing improvements and architecture improvements:

1. Build a shared, typed data-access layer for selected product/search flows to reduce duplicated API logic.
2. Improve 2 to 3 high-impact mobile-first user flows end-to-end.
3. Reuse OFF webcomponents where they provide faster, consistent delivery.
4. Deliver clear migration documentation so future contributors can extend the same pattern.

This directly supports Explorer goals: frontend/backend decoupling, maintainability, faster feature iteration, and better mobile usability.

## Expected Outcomes and KPI

- 2 to 3 critical user flows improved for mobile and desktop.
- At least 30% reduction of duplicated API-call logic in targeted modules.
- At least 2 OFF reusable webcomponents integrated in production-facing flows.
- Accessibility validation passed for new interactions in scoped pages.
- Performance on targeted mobile pages improved or maintained while adding functionality.
- Contributor migration guide published for future parity extensions.

## Scope

In scope:

- Product/search-related parity work on selected flows only.
- Shared typed data-access abstraction for scoped endpoints.
- Component reuse and integration documentation.

Out of scope:

- Full-site parity in one cycle.
- Full redesign of all pages.
- Migrating every endpoint in the application.

## 175-Hour Implementation Plan

Community bonding:

- Finalize exact scoped flows/endpoints with mentors.
- Baseline current UX and code metrics.

Phase 1 (Weeks 1 to 3):

- Implement first data-layer slice and migrate first flow.
- Open incremental PRs early for feedback.

Phase 2 (Weeks 4 to 6):

- Migrate second and third flows.
- Integrate OFF webcomponents in scoped interfaces.
- Validate responsive and accessibility behavior.

Phase 3 (Weeks 7 to 9):

- Performance tuning, cleanup, and bug fixes.
- Final documentation, before/after metrics, and handoff artifacts.

## Risks and Mitigation

- Scope creep: enforce 2 to 3 flow cap and explicit out-of-scope list.
- API variability: isolate mapping/adapters in the data layer.
- External API instability in dev: validate loading/error states and fallback UX.

## Why this project is high value

This work adds immediate user value (better mobile journeys), long-term engineering value (less duplicated logic and cleaner architecture), and ecosystem value (greater reuse of OFF SDK and webcomponents). It is practical, measurable, and aligned with OFF priorities.

## Project Information

- Repository: https://github.com/openfoodfacts/openfoodfacts-explorer
- Related repositories: https://github.com/openfoodfacts/openfoodfacts-nodejs, https://github.com/openfoodfacts/openfoodfacts-webcomponents
- Slack channel: #off-explorer
- Potential mentor: VaiTon
- Project duration: approximately 175 hours
- Skills required: TypeScript, Svelte/SvelteKit, HTTP APIs
- Difficulty: Medium
