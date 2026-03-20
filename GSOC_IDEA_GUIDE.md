# Open Food Facts Explorer - GSoC Idea Guide (Pranjal)

This guide helps you submit a strong, realistic idea between March 16 and March 31.
It is tailored to the Open Food Facts Explorer roadmap, mentor expectations, and your current contribution status.

## 1) What mentors actually need from your idea

Your proposal is not just a feature wishlist. Mentors usually select candidates who show:

- Clear user problem and why it matters.
- A scoped implementation plan that fits about 175 hours.
- Measurable outcomes (KPI-style, not vague statements).
- Technical feasibility with current stack (SvelteKit, TypeScript, OFF APIs, OFF JS SDK, webcomponents).
- Proof you can execute (past contributions, communication, iteration plan).

If your proposal can answer "what problem is solved, for whom, by when, and how success is measured", it is already stronger than most submissions.

## 2) Recommended project idea (high value + realistic)

## Title

Mobile-First Feature Parity for Explorer through Shared Data Layer and Reusable OFF Components

## Problem

Explorer already has strong foundations (SvelteKit, editing, search, Folksonomy integration), but some high-value flows from the main website are still inconsistent or fragmented, especially on mobile where most traffic comes from.

Developers also spend effort wiring API calls in multiple places. This slows feature delivery and increases maintenance risk.

## Why this idea is strong

- Directly aligned with the roadmap: more OFF JS SDK reuse and more webcomponents reuse.
- Solves a real user problem: better mobile usability and clearer product understanding workflows.
- Solves a real engineering problem: backend/frontend decoupling through a shared data access layer.
- Has visible demo value: users and mentors can immediately see progress.

## Core objectives

1. Build a unified data access layer for selected critical product/search endpoints using openfoodfacts-nodejs patterns.
2. Integrate reusable webcomponents for targeted sections where it accelerates parity and consistency.
3. Improve two to three high-impact mobile flows from discovery to product understanding/editing.
4. Deliver performance and accessibility improvements for the implemented screens.

## 3) Scope for 175 hours (realistic)

## In scope

- Data layer module for selected features (not all APIs at once).
- 2 to 3 user-facing flows end-to-end (desktop + mobile responsive).
- Reusable components integration in those flows.
- Documentation and migration notes for future contributors.

## Out of scope

- Full parity with the legacy website in one cycle.
- Rebuilding every page or every endpoint.
- Major visual redesign unrelated to usability outcomes.

## 4) Deliverables and KPI

## Deliverable A: Shared data access layer

- Typed service wrappers for selected endpoints.
- Unified error handling and fallback strategy.
- Reduced duplicated request logic across targeted screens.

KPI suggestions:

- At least 30% reduction of duplicated API call logic in targeted modules.
- Zero regression in existing targeted flows after migration.

## Deliverable B: Mobile-first parity improvements on key flows

Candidate flows:

- Search to product page flow.
- Product page key knowledge panel readability and interaction.
- Basic edit flow for selected fields.

KPI suggestions:

- Lighthouse mobile performance for targeted pages improved by 10 to 20 points (or maintains high score while adding features).
- Accessibility checks pass for new UI interactions.
- Reduced user steps for at least one core action (for example, open product details from search).

## Deliverable C: Reusable components adoption

- Integrate OFF webcomponents where relevant in scoped flows.
- Document integration boundaries and customization approach.

KPI suggestions:

- At least 2 reused components integrated in production-grade flows.
- Documented guidelines for adding another component with low friction.

## Deliverable D: Contributor-ready docs

- Architecture doc of data layer and integration strategy.
- Migration checklist for future parity tasks.
- PR-ready demos, screenshots, and benchmark summary.

## 5) Timeline (example)

## Community bonding / pre-coding

- Finalize exact scope with mentor.
- Freeze endpoint list and target flows.
- Define baseline metrics (performance, UX steps, code duplication markers).

## Phase 1 (Weeks 1 to 3)

- Implement shared data layer for first feature set.
- Add tests/checks where practical and establish usage pattern.
- Ship first migration PR.

## Phase 2 (Weeks 4 to 6)

- Migrate second and third target flows.
- Integrate reusable components.
- Ensure responsive behavior and a11y correctness.

## Midterm milestone

- Working end-to-end first major flow in production quality.
- One merged PR demonstrating migration pattern.

## Phase 3 (Weeks 7 to 9)

- Performance tuning and cleanup.
- Documentation and migration guide.
- Buffer for review iterations and bug fixes.

## Final milestone

- 2 to 3 polished flows, measurable KPI report, and reusable patterns for future contributors.

## 6) Risks and mitigation

- API inconsistency risk: isolate adapters in one layer and avoid UI coupling.
- Scope creep risk: lock out-of-scope list early with mentors.
- External API instability in dev environments: validate UI behavior with expected failure handling and mocked states where needed.

## 7) Proposal text you can adapt directly

Use this as your base and personalize details with your merged PRs.

Description:

I propose to improve Open Food Facts Explorer by implementing a mobile-first feature parity track focused on reusable architecture. The project will introduce a shared typed data access layer for selected product and search features, integrate reusable OFF webcomponents in high-impact flows, and improve key user journeys (search to product understanding and basic editing) with measurable accessibility and performance gains.

Expected outcomes:

- Reduced duplicated API integration logic in targeted areas.
- 2 to 3 critical flows with improved mobile usability and consistency.
- Reuse of OFF webcomponents and alignment with Explorer roadmap.
- Clear architecture and migration documentation to accelerate future parity work.

Project information:

- Repository: https://github.com/openfoodfacts/openfoodfacts-explorer
- Related repositories: https://github.com/openfoodfacts/openfoodfacts-nodejs and https://github.com/openfoodfacts/openfoodfacts-webcomponents
- Slack channel: #off-explorer
- Potential mentor: VaiTon
- Duration: approximately 175 hours
- Skills: TypeScript, Svelte/SvelteKit, HTTP API integration
- Difficulty: Medium

## 8) What to do between now and March 31

1. Select your final scoped flows (max 3).
2. Collect your contribution evidence links (PRs, issues, commits).
3. Create one short architecture diagram (data layer and component boundaries).
4. Write baseline metrics and target KPIs.
5. Share draft in #off-explorer for mentor feedback before final submission.

## 9) Fork-only Git workflow (safe)

This repository already has:

- origin -> your fork
- upstream -> official Open Food Facts repository

To always push only to your fork, use these checks:

1. Confirm remotes:
   git remote -v
2. Push explicitly to origin:
   git push origin <your-branch>
3. Never run:
   git push upstream <your-branch>
4. Open PR from your fork branch to upstream main on GitHub UI.

Optional safety command (prevents accidental plain git push):

- git config remote.pushDefault origin

## 10) Suggested branch and commit naming

- Branch: docs/gsoc-idea-guide
- Commit: docs: add practical GSoC idea and submission guide

This makes your work easy for mentors to review and shows communication quality.
