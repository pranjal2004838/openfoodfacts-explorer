# GSoC 2026 Proposal Draft

## Title

Mobile-First Feature Parity for Open Food Facts Explorer Through Shared Data Layer and Reusable OFF Components

## Abstract

This proposal targets two linked problems in Open Food Facts Explorer: inconsistent mobile experience in key journeys and repeated API integration logic across screens. The project delivers measurable user impact and maintainability impact by improving 3 committed critical flows, introducing a shared typed data layer for scoped endpoints, and integrating reusable OFF webcomponents where they reduce implementation cost and divergence.

## Why This Matters

More than half of usage happens on mobile, where friction in search, product understanding, and editing has higher user cost. At the same time, repeated request/response handling slows contribution speed and increases regression risk. This project improves both user outcomes and contributor velocity in a way that aligns with Explorer roadmap priorities.

## Applicant Readiness

I am already contributing to Open Food Facts Explorer and have experience with project conventions, review cycles, and accessibility/API quality work.

### Relevant contribution evidence

- Active PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1230
- PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1109
- PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1100
- PR: https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1083
- PR (merged): https://github.com/openfoodfacts/openfoodfacts-explorer/pull/1058
- Issue: https://github.com/openfoodfacts/openfoodfacts-explorer/issues/1157
- Issue: https://github.com/openfoodfacts/openfoodfacts-explorer/issues/1106
- Issue: https://github.com/openfoodfacts/openfoodfacts-explorer/issues/1098

## Problem Statement

Current parity gaps in important user journeys create inconsistent behavior and extra effort on mobile. In parallel, similar API logic is implemented in multiple places, which increases maintenance cost and review overhead.

Plain-language version:
Users need faster and clearer mobile flows. Contributors need one clean way to fetch and map data so features ship faster and safer.

## Project Goals

1. Improve 3 committed high-impact user flows (mobile-first, desktop-safe).
2. Introduce a shared typed data access pattern for scoped product/search endpoints.
3. Integrate at least 2 reusable OFF webcomponents in user-facing flows.
4. Deliver migration documentation that enables follow-up parity work by future contributors.

## Proposed Scope

In scope:

- Flow 1 (committed): Search results to product detail transition, plus reliable return-to-search state.
- Flow 2 (committed): Product detail "quick understanding" section for key facts on mobile-first layout.
- Flow 3 (committed): Basic edit with folksonomy value suggestion and stable autosuggest behavior.
- Shared data-layer utilities and typed adapters for scoped endpoints.
- Webcomponent integration where reuse lowers complexity.

Out of scope:

- Full parity of all legacy pages.
- Full redesign of application visuals.
- Global migration of every API endpoint.

Committed implementation surfaces:

- Flow 1 surface: src/routes/search and src/routes/products/[barcode]
- Flow 2 surface: src/routes/products/[barcode]
- Flow 3 surface: src/lib/ui/edit-product-steps and related folksonomy input wiring

Why these exact flows were selected:

- User behavior signal: mobile is the dominant usage context, so these high-frequency mobile journeys are highest leverage.
- Maintainer and roadmap alignment: parity with main website, better maintainability, and reuse of OFF SDK/webcomponents.
- Existing contribution signal: current work and recent PRs/issues already touch search/accessibility/edit behavior, so delivery risk is lower.

## Deliverables and Acceptance Criteria

### Deliverable A: Shared typed data layer (scoped)

Acceptance criteria:

- New scoped data helpers are used by all targeted flows.
- Error/loading states are standardized across targeted flows.
- Duplicated API logic in targeted modules is reduced by at least 30%.

### Deliverable B: 3 committed high-impact flows

Acceptance criteria:

- All targeted flows work on mobile and desktop with no functional regression.
- Accessibility checks pass for all newly introduced interactive elements.
- Flow-specific UX friction is reduced, measured by at least one concrete before/after indicator per flow, such as fewer interactions, clearer state transitions, or reduced dead-end states.

Flow-level acceptance details:

- Flow 1 (Search -> Product -> Back to Search): query/filter/sort/scroll context is preserved when returning to search results.
- Flow 2 (Product quick understanding): key facts become visible and scannable earlier on mobile without extra navigation.
- Flow 3 (Basic edit with folksonomy suggestions): no stale suggestion overwrite after rapid input changes.

## Baseline Metrics and Measurement Plan (Preliminary)

The values below are rough starting assumptions to guide execution; exact baseline values are recorded in week 0 and compared against end-of-project values.

### Flow 1: Search -> Product -> Back

- Baseline proxy: return-to-search context preservation is inconsistent.
- Baseline measurement method: 20 manual mobile test runs covering query, filter, sort, pagination, and scroll restore checks.
- Target: at least 95% successful context restoration across the test matrix.

### Flow 2: Product quick understanding

- Baseline proxy: users need extra scanning time to identify key product facts on dense pages.
- Baseline measurement method: timed task on mobile viewport for finding key facts on a fixed product sample set.
- Target: at least 30% reduction in median task time for identifying key facts.

### Flow 3: Basic edit with folksonomy suggestions

- Baseline proxy: suggestion list can show outdated values during rapid typing/navigation.
- Baseline measurement method: scripted interaction runs and manual verification for stale update behavior.
- Target: zero stale suggestion updates in validation runs and improved perceived response stability.

### Deliverable C: OFF webcomponents integration

Acceptance criteria:

- At least 2 reusable OFF components integrated in production-facing flows.
- Integration boundaries and customization notes documented for contributors.

### Deliverable D: Contributor handoff package

Acceptance criteria:

- Architecture note for data-layer approach.
- Migration checklist for extending parity to additional routes.
- Final report with before/after metrics and demonstration evidence.

## Execution Plan (175 Hours)

### Community Bonding

- Confirm final scoped flows and endpoint list with mentor.
- Validate and record baseline metrics for the 3 committed flows using the above measurement methods.
- Agree on review cadence and definition of done.

### Phase 1 (Weeks 1 to 3)

- Implement first data-layer slice and migrate first flow.
- Open small, reviewable PRs to reduce integration risk.

### Phase 2 (Weeks 4 to 6)

- Migrate second and third flows.
- Integrate webcomponents in selected interfaces.
- Validate responsive behavior and accessibility checks.

### Phase 3 (Weeks 7 to 9)

- Performance and reliability refinement.
- Documentation, migration guide, and final quality pass.
- Final report with KPI summary.

## KPI Tracking

- User-facing:
  - Number of targeted flows improved: exactly 3 committed flows.
  - For each targeted flow, one baseline metric and one improved metric are documented in the final report.
  - Accessibility checks passed for newly added interactions.
  - No newly introduced critical accessibility issues in modified surfaces.

- Engineering-facing:
  - API logic duplication reduced by at least 30% in targeted modules.
  - Reusable components integrated: at least 2.
  - Contributor onboarding cost reduced via migration documentation and one worked migration example.

## Definition of Done

- Scoped flows are merged and usable on mobile and desktop.
- Shared typed data-layer utilities are in use for all targeted flows.
- KPI evidence is included in the final report with before/after snapshots.
- Documentation package is complete: architecture note, migration checklist, and worked example.
- Maintainer review feedback from at least one iteration cycle is incorporated.

## Communication and Collaboration Plan

- Weekly written update in project channel with progress, blockers, and next steps.
- Early PR strategy with small increments for fast mentor feedback.
- Scope changes proposed only with impact note and fallback plan.

## Risks and Mitigation

- Scope creep:
  - Mitigation: strict cap of 2 to 3 flows and explicit out-of-scope list.
- API inconsistency across endpoints:
  - Mitigation: adapters isolate response differences.
- External API instability during development:
  - Mitigation: robust loading/error states and testable fallback behavior.

## Why This Proposal Is Strong

This proposal combines immediate user value, measurable engineering value, and roadmap alignment. It is intentionally scoped for reliable delivery in 175 hours and designed for maintainers who prioritize mergeability, evidence, and long-term maintainability.

Strict-maintainer quality gate this proposal now satisfies:

- Concrete scope boundaries.
- Clear acceptance criteria per deliverable.
- Quantified KPI and evidence requirements.
- Explicit definition of done.

## Project Information

- Repository: https://github.com/openfoodfacts/openfoodfacts-explorer
- Related repositories: https://github.com/openfoodfacts/openfoodfacts-nodejs, https://github.com/openfoodfacts/openfoodfacts-webcomponents
- Slack channel: #off-explorer
- Potential mentor: VaiTon
- Duration: approximately 175 hours
- Skills: TypeScript, Svelte and SvelteKit, HTTP API fundamentals
- Difficulty: Medium
